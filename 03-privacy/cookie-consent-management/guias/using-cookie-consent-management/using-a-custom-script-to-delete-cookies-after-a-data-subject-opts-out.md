---
title: "Using a custom script to delete cookies after a data subject opts out"
slug: "using-a-custom-script-to-delete-cookies-after-a-data-subject-opts-out"
updated: 2026-04-27T10:22:59Z
published: 2026-04-27T10:22:59Z
canonical: "helpcenter.securiti.ai/using-a-custom-script-to-delete-cookies-after-a-data-subject-opts-out"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using a custom script to delete cookies after a data subject opts out

Securiti lets you use a custom script to delete cookies, `localStorage` items, and `sessionStorage` items when a data subject opts out of one or more consent categories. This script uses the Securiti SDK for cookie classifications and provides a starting point for building your own deletion logic.

## Prerequisites

To successfully set up custom cookie deletion, you must have:

- The Securiti script tag installed with the banner loading correctly.
- Consent categories configured.
- Access to your site’s HTML templates.
- An understanding of how cookies behave across domains, subdomains, and paths.

> [!WARNING]
> Important
> 
> Insert the custom deletion logic only after the Securiti SDK has fully loaded.

## Key considerations

A custom script cannot always delete cookies. Several technical factors may prevent successful deletion even when the script attempts it:

| Reason | Description |
| --- | --- |
| Cookie domain mismatch | The cookie’s domain does not match the current page’s domain, so the browser does not allow the script to delete it. |
| Cookie path mismatch | The cookie’s path does not match the current page’s path, which prevents the browser from applying the deletion attempt. |
| HttpOnly flag | The `HttpOnly` flag prevents JavaScript from accessing or deleting the cookie. |
| Secure flag without HTTPS | The Secure flag requires the site to load over HTTPS for deletion attempts to work. |
| Third party cookies | Browser restrictions may block deletion of third party cookies, even when the script attempts it. |
| Storage type mismatch | Storage type names differ, such as `session_storage_item` or `session_storage`, which prevents the script from recognizing and deleting the cookie. |
| Browser privacy settings | Browser privacy settings may block manipulation of third party or cross site storage. |
| Pixel or beacon-dropped cookies | Image beacons or pixels may drop cookies before the page refreshes, making them unavailable for deletion. |
| Additional tracker attributes | Tracker attributes may include domain, path, or storage rules that prevent deletion under the script’s logic. |

> [!WARNING]
> Important
> 
> - You must validate your implementation and update the deletion logic to ensure it works correctly in your environment.
> - Configure your website logic to respect consent preferences and ensure that cookies, localStorage items, or sessionStorage items are not recreated after being deleted. These items can reappear if your website triggers them again before the data subject revisits the activity or updates their consent choices.

## Understanding the process

1. The Securiti Cookie Consent SDK classifies cookies and assigns each cookie to a category.
2. The data subject changes their consent preferences.
3. The SDK dispatches a consent event containing the latest consent statuses.
4. Your script receives this event and identifies categories where consent was declined.
5. The script retrieves all cookies in those cookie categories using the SDK method `getCookiesByCategory()`.
6. The script loops through each item and deletes it based on its type.
7. You adjust the deletion logic as needed to ensure cookies are removed from your domain.

## SDK Method: `getCookiesByCategory()`

Use this method to retrieve all cookies associated with a specific cookie category.

### Example

```javascript
SecuritiSDK.onReady(function(sdk) {
    const cookies = sdk.getCookiesByCategory("advertisement");
    console.log(cookies);
});
```

### Example output (trimmed)

```json
{
  "advertisement": [
    {
      "name": "cookie1",
      "category": "advertisement",
      "baseCategory": "advertisement",
      "url": "example.com",
      "type": "http_cookie"
    },
    {
      "name": "cookie2",
      "category": "advertisement",
      "baseCategory": "advertisement",
      "url": "ads.example.com",
      "type": "session_storage"
    }
  ]
}
```

Use the `name`, `type`, and `url` fields to determine how each cookie should be deleted, since these values tell you the cookie’s identifier, storage mechanism, and the domain or path where the deletion logic must be applied.

## Run the cookie deletion script

The example script listens for the SDK:

```javascript
single_upload_consent_given
```

This event fires when a data subject **manually updates** their consent using the cookie banner or preference center. To run the cookie deletion script for more cases, such as page load, implicit consent, or GPC, you can replace it with:

```javascript
consent_given
```

You must make sure to test your implementation if you change the event type.

## Add the script to your domain

Place the script **at the end of the** `&lt;body&gt;` **element**, after the Securiti SDK has loaded.

### Full example script

Use this script as a starting point, and adjust it as needed to match your domain, subdomain, and path requirements.

> [!WARNING]
> Important
> 
> Securiti does not offer native cookie deletion in the Cookie Consent Management module because cookie removal depends on browser behavior, domain and path configurations, and other technical factors. Instead, you can use the example script below as a customizable method to handle deletion on your domain.

```xml
<script>
  // Helper method: Get domains and paths for cookie deletion
  function getCookieDomainsAndPaths(cookieUrl) {
      var domains = [window.location.hostname, '.' + window.location.hostname];
      var paths = ['/', window.location.pathname];

      // Add current directory path
      var currentDir = window.location.pathname.substring(0, window.location.pathname.lastIndexOf('/') + 1);
      if(currentDir !== '/') {
          paths.push(currentDir);
      }

      // If cookie has a specific domain/URL, add it to deletion attempts
      if(cookieUrl) {
          try {
              var urlObj = new URL('http://' + cookieUrl.replace(/^https?:\/\//, ''));
              domains.push(urlObj.hostname);
              domains.push('.' + urlObj.hostname);
          } catch(e) {
              domains.push(cookieUrl);
              domains.push('.' + cookieUrl);
          }
      }

      return { domains: domains, paths: paths };
  }

  // Method 1: Delete HTTP cookie with specific domains and paths
  function deleteHttpCookie(cookieName, domains, paths) {
      domains.forEach(function(domain) {
          paths.forEach(function(path) {
              var normalizedPath = path.endsWith('/') ? path : path + '/';

              // Delete with domain and path
              document.cookie = cookieName + '=; max-age=0; path=' + normalizedPath + '; domain=' + domain + ';';
              document.cookie = cookieName + '=; max-age=0; path=' + path + '; domain=' + domain + ';';

              // Delete without domain specification
              document.cookie = cookieName + '=; max-age=0; path=' + normalizedPath + ';';
              document.cookie = cookieName + '=; max-age=0; path=' + path + ';';
          });
      });
  }

  // Method 2: Delete localStorage item
  function deleteLocalStorageItem(itemName) {
      try {
          localStorage.removeItem(itemName);
      } catch(e) {}
  }

  // Method 3: Delete sessionStorage item
  function deleteSessionStorageItem(itemName) {
      try {
          sessionStorage.removeItem(itemName);
      } catch(e) {}
  }

  // Main listener using single_upload_consent_given
  window.addEventListener('message', function(ev) {
      if(ev.data.message === 'single_upload_consent_given' && ev.data.consentStatuses) {
          window.SecuritiSDK.onReady(function(sdk) {
              Object.keys(ev.data.consentStatuses).forEach(function(categoryName) {
                  if(!ev.data.consentStatuses[categoryName]) {
                      var categoryData = sdk.getCookiesByCategory(categoryName);
                      if(categoryData && categoryData[categoryName]) {
                          categoryData[categoryName].forEach(function(item) {
                              if(item.name) {
                                  switch(item.type) {
                                      case 'http_cookie':
                                      case 'cookie':
                                          var domainsAndPaths = getCookieDomainsAndPaths(item.url);
                                          deleteHttpCookie(item.name, domainsAndPaths.domains, domainsAndPaths.paths);
                                          break;
                                      case 'localstorage':
                                      case 'local_storage':
                                          deleteLocalStorageItem(item.name);
                                          break;
                                      case 'sessionstorage':
                                      case 'session_storage':
                                          deleteSessionStorageItem(item.name);
                                          break;
                                      default:
                                          // Extend this logic to handle additional types if needed
                                          break;
                                  }
                              }
                          });
                      }
                  }
              });
          });
      }
  });
</script>
```

> [!CAUTION]
> Caution
> 
> You may need to update the script in the following situations:
> 
> - Your cookies use custom paths or subdomains.
> - Your cookies use nonstandard storage types.
> - You detect additional item types, such as image beacons.
> - You want to execute deletion on `consent_given` instead of manual consent only.
> - You want to add success checks to verify whether an item is deleted.

## Testing your implementation

Follow the steps below to thoroughly test your implementation and verify that cookie behavior aligns with the updated consent preferences:

1. Open your web browser’s developer tools and navigate to the section that displays cookies.
2. Review and note all existing cookies before updating consent.
3. Submit new consent preferences through the cookie banner.
4. Observe which cookies were removed and which ones remain.
5. Update your deletion logic if any cookies persist unexpectedly.

> [!NOTE]
> **Note**
> 
> If a cookie appears as `HttpOnly`, JavaScript cannot delete it. This is expected behavior.

## FAQs

****Can Securiti delete cookies automatically?****

No. Deletion depends on many web browser-level factors. We provide a script you can customize.

****Can this script delete HTTP-only cookies?****

No. Web browsers do not allow JavaScript to delete HttpOnly cookies.

### 

No. It deletes cookies, `localStorage` items, and `sessionStorage` items. Trackers like image beacons are blocked by autoblocking but not deleted by this script.

### 

Yes. You must adjust it to match your website’s domains, paths, and cookie behavior.

## Next steps

- Test the script on your development environment.
- Enhance domain and path rules as needed.
- Collaborate with your engineering team to validate deletion behavior.
- To help understanding the cookie classifications, see [Understanding how Securiti categorizes cookies and trackers](/v1/docs/understanding-how-securiti-categorizes-cookies-and-trackers).
