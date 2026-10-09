---
title: "React Native SDK integration and implementation guide"
slug: "react-native-sdk-integration-and-implementation-guide"
updated: 2026-07-21T11:08:04Z
published: 2026-07-21T11:08:04Z
canonical: "helpcenter.securiti.ai/react-native-sdk-integration-and-implementation-guide"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# React Native SDK integration and implementation guide

This integration and implementation guide for the React Native SDK covers installation, configuration, and usage of all available methods.

> [!NOTE]
> **Note**
> 
> The SDK name and APIs may change.

## Installation steps

1. Navigate to your **application** folder in the terminal.
2. Run: `npm i react-native-nitro-modules`.
3. Run: `npm i securiti-consent-sdk@latest`.
4. Ensure `node_modules/securiti-consent-sdk` exists.

### Android installation

In your app's `android/app/build.gradle` file, add the following line **above the dependencies block**:

```groovy
repositories {      
   google()      
   mavenCentral()      
   maven {          
      url 'https://cdn-prod.securiti.ai/consent/maven'      
   }  
}
```

### iOS installation

In your project's **iOS** folder, run the following command:

```plaintext
pod install
```

## Methods

### 1. `initialize(options)`

Initializes the Consent SDK with configuration options. Must be called before using any other SDK methods.

**Parameters**

| Parameter | Type | Require | Description |
| --- | --- | --- | --- |
| `options` | `CmpSDKOptions` | Yes | Configuration options for the SDK |

**CmpSDKOptions**

| Options | Type | Required | Description |
| --- | --- | --- | --- |
| `appURL` | string | Yes | Base URL for the Securiti application |
| `cdnURL` | string | Yes | URL for the Securiti CDN resources |
| `tenantID` | string | Yes | Your tenant identifier from Securiti |
| `appID` | boolean | Yes | Your application identifier from Securiti |
| `testingMode` | `LoggerLevel` | Yes | Enable testing mode |
| `loggerLevel` | number | Yes | Log level: “DEBUG”, “INFO”, “WARNING”, “ERROR” |
| `consentsCheckInterval` | string | Yes | Time in seconds between consent checks |
| `subjectId` | string | No | User identifier for consent tracking |
| `languageCode` | string | No | Language code for UI elements such as “en” |
| `locationCode` | string | No | Location code for regional compliance such as “US” |

**Return Value**

void

**Example**

```javascript
import { initialize, LoggerLevel, ModeValues } from 'securiti-consent-sdk';
const options = {
  appURL: 'your APP Url',
  cdnURL: 'Your CDN Url',
  tenantID: 'your-tenant-id',
  appID: 'your-app-id',
  testingMode: false,
  loggerLevel: LoggerLevel.DEBUG,
  consentsCheckInterval: 60,
  subjectId: 'user-123',
  languageCode: 'en',
  locationCode: 'US'
};
initialize(options);
```

### 2. `getConsentByPurposeId(purposeId) `

Retrieves the consent status for a specific Purpose by its ID.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `purposeId` | number | The unique identifier of the purpose |

**Return Value**

`Promise&lt;ConsentStatus&gt;`

**ConsentStatus Values:**

- `granted`
- `declined`
- `not_determined`
- `withdrawn`

**Example**

```javascript
import { getConsentByPurposeId, ConsentStatusValues } from 'securiti-consent-sdk';
getConsentByPurposeId(12345)
  .then((status) => {
    if (status === ConsentStatusValues.GRANTED) {
      // Consent is granted
    }
  });
```

### 3. `getConsentByPermissionId(permissionId)`

Retrieves the consent status for a specific app permission by its ID.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `permissionId` | string | The unique identifier of the permission |

**Return Value**

`Promise&lt;ConsentStatus&gt;`

**ConsentStatus Values**

`Promise&lt;ConsentStatus&gt;`

**Example**

```javascript
import { getConsentByPermissionId, ConsentStatusValues } from 'securiti-consent-sdk';
getConsentByPermissionId('location')
  .then((status) => {
    if (status === ConsentStatusValues.GRANTED) {
      // Permission consent is granted
    }
  });
```

### 4. `getPermissions()`

Retrieves all available app permissions defined in the consent configuration.

**Return Value**

`Promise&lt;AppPermission[]&gt;`

**AppPermission Properties**

| Property | Type | Description |
| --- | --- | --- |
| `id` | number | The numeric identifier |
| `name` | string | The permission name |
| `permissionId` | string | The permission identifier string |
| `description` | string | Localized permission descriptions |
| `group` | string | The permission group name |
| `groupId` | number | The permission group identifier |
| `consentStatus` | string | The current consent status |
| `nameMap` | string | Localized permission names |
| `isSettingsPromptEnabled` | boolean | Whether settings prompt is enabled |

**Example**

```javascript
import { getPermissions, ConsentStatusValues } from 'securiti-consent-sdk';
getPermissions()
  .then((permissions) => {
    const grantedPermissions = permissions.filter(
      permission => permission.consentStatus === ConsentStatusValues.GRANTED
    );
  });
```

### 5. `getPurposes()`

Retrieves all available purposes defined in the consent configuration.

**Return Value**

`Promise&lt;Purpose[]&gt;`

**Purpose Properties**

| Property | Type | Description |
| --- | --- | --- |
| `purposeId` | number | The unique identifier for the purpose |
| `purposeName` | string | Localized purpose names |
| `purposeDescription` | string | Localized purpose descriptions |
| `sdks` | `SDK[]` | SDKs associated with this purpose |
| `consentStatus` | string | The current consent status |
| `disableOptOut` | boolean | Whether opt-out is disabled |
| `optOutText` | string | Localized opt-out text |
| `hideDetails` | boolean | Whether details should be hidden in the UI |
| `isGADMapped` | boolean | Whether mapped to Google Ads (Android) |
| `gadDescription` | string | Localized Google Ads description (Android) |
| `isATTMapped` | boolean | Whether mapped to App Tracking Transparency (iOS) |
| `attDescription` | string | Localized App Tacking Transparency Message (iOS) |

**Example**

```javascript
import { getPurposes, ConsentStatusValues } from 'securiti-consent-sdk';
getPurposes()
  .then((purposes) => {
    const grantedPurposes = purposes.filter(
      purpose => purpose.consentStatus === ConsentStatusValues.GRANTED
    );
  });
```

### 6. `getSdksInPurpose(purposeId)`

Retrieves all SDKs associated with a specific purpose.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `purposeId` | number | The unique identifier of the purpose |

**Return Value**

`Promise&lt;SDK[]&gt;`

**SDK Properties**

| Property | Type | Description |
| --- | --- | --- |
| `sdkId` | number | The unique identifier for the SDK |
| `namespaceId` | string | The namespace identifier string |
| `sdkName` | string | Localized SDK names |
| `sdkDescription` | string | Localized SDK descriptions |
| `vendor` | string | The vendor or provider of the SDK |
| `logoBase64` | string | Base64-encoded logo image |
| `website` | string | The SDK vendor’s website URL |
| `matchedBy` | `string[]` | How the SDK was matched in the application |
| `collectingData` | boolean | Whether the SDK is collecting data |

**Example**

```javascript
import { getSdksInPurpose } from 'securiti-consent-sdk';
getSdksInPurpose(12345)
  .then((sdks) => {
    // Use SDKs
  });
```

### 7. `setPurposeConsent(purpose, consent)`

Sets the consent status for a specific purpose.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `purpose` | Purpose | The purpose object to set consent for |
| `consent` | string | The consent status to set |

**ConsentStatus Values:**

- `granted`
- `declined`
- `not_determined`

> [!NOTE]
> **Note**
> 
> The `not_determined` consent status value is recorded only for iOS consent records. This status is not applicable to the Android consent records.
- `withdrawn`

**Return Value**

`boolean`

**Example**

```javascript
import { setPurposeConsent, getPurposes, ConsentStatusValues } from 'securiti-consent-sdk';
getPurposes()
  .then((purposes) => {
    const analyticsPurpose = purposes.find(p => p.purposeId === 12345);
    if (analyticsPurpose) {
      const success = setPurposeConsent(analyticsPurpose, ConsentStatusValues.GRANTED);
    }
  });
```

### 8. `setPermissionConsent(appPermission, consent)`

Sets the consent status for a specific app permission.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `appPermission` | `AppPermission` | The permission object to set consent for |
| `consent` | string | The consent status to set |

**ConsentStatus Values**

Same as above.

**Return Value**

`boolean`

**Example**

```javascript
import { setPermissionConsent, getPermissions, ConsentStatusValues } from 'securiti-consent-sdk';
getPermissions()
  .then((permissions) => {
    const locationPermission = permissions.find(p => p.permissionId === 'location');
    if (locationPermission) {
      const success = setPermissionConsent(locationPermission, ConsentStatusValues.GRANTED);
    }
  });
```

### 9. `resetConsents()`

Resets all consents to their default state.

**Parameters**

None

**Return Value**

`void`

**Example**

```javascript
import { resetConsents } from 'securiti-consent-sdk';
resetConsents();
```

### 10. `isReady(callback)`

Checks if the React Native SDK is ready to use (asynchronous version).

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `callback` | (status: boolean) => void | Callback function that receives the ready status |

**Return Value**

`void`

**Example**

```javascript
import { isReady, presentConsentBanner } from 'securiti-consent-sdk';
isReady((isReady) => {
  if (isReady) {
    presentConsentBanner();
  }
});
```

### 11. `getBannerConfig()`

Retrieves the banner configuration.

**Return Value**

`Promise&lt;BannerConfig | null&gt;`

**BannerConfig Properties**

See [Types and Properties](/latest/docs/react-native-sdk-integration-and-implementation-guide#types-and-properties2) section.

**Example**

```javascript
import { getBannerConfig } from 'securiti-consent-sdk';
getBannerConfig()
  .then((config) => {
    if (config) {
      // Use config
    }
  });
```

### 12. `options()`

Retrieves the current SDK configuration options.

**Return Value**

`CmpSDKOptions | null`

**Example**

```javascript
import { options } from 'securiti-consent-sdk';
const currentOptions = options();
```

### 13. `getSettingsPrompt()`

Retrieves the settings prompt configuration.

**Return Value**

`Promise&lt;SettingsPrompt | null&gt;`

**SettingsPrompt Properties**

See T[ypes and Properties](/latest/docs/react-native-sdk-integration-and-implementation-guide#types-and-properties2) section.

**Example**

```javascript
import { getSettingsPrompt } from 'securiti-consent-sdk';
getSettingsPrompt()
  .then((prompt) => {
    if (prompt) {
      // Use prompt
    }
  });
```

### 14. `uploadConsents(request)`

Uploads consents to the server.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `request` | `PostConsentsRequest` | The consent data to upload |

**Return Value**

`Promise&lt;boolean&gt;`

**Example**

```javascript
import { uploadConsents, ConsentStatusValues } from 'securiti-consent-sdk';
const timestamp = Date.now();
const consentRequest = {
  uuid: 'user-123',
  appUUID: 'app-456',
  device: 'iPhone 12',
  implicitConsent: false,
  version: 1,
  purposeConsents: [
    {
      purposeID: 12345,
      consentStatus: ConsentStatusValues.GRANTED,
      timestamp: timestamp,
      isEssential: false
    }
  ],
  permissions: [
    {
      permission: 'location',
      consentStatus: ConsentStatusValues.GRANTED,
      timestamp: timestamp
    }
  ],
  isTestMode: false,
  adId: 'advertising-id-789',
  bannerInfo: 'Banner version 2.0',
  sdkVersion: '1.132.0',
  platform: 'iOS'
};
uploadConsents(consentRequest)
  .then((success) => {
    if (success) {
      // Success
    }
  });
```

### 15. `presentConsentBanner()`

Displays the consent banner UI to the mobile app user.

**Parameters**

None

**Return Value**

`void`

**Example**

```javascript
import { presentConsentBanner } from 'securiti-consent-sdk';
presentConsentBanner();
```

### 16. `presentPreferenceCenter()`

Displays the preference center UI to the mobile app user.

**Parameters**

None

**Return Value**

`void`

**Example**

```javascript
import { presentPreferenceCenter } from 'securiti-consent-sdk';
presentPreferenceCenter();
```

## Types and Properties

`ConsentStatus` **values:**

- `granted`
- `declined`
- `withdrawn`

`CmpSDKOptions`

See the details from the [initialize(options)](/latest/docs/react-native-sdk-integration-and-implementation-guide#1-initializeoptions2) section.

`AppPermission`

See the details from the [getPermissions()](/latest/docs/react-native-sdk-integration-and-implementation-guide#4-getpermissions2) section.

`Purpose`

See the details from the [getPurposes()](/latest/docs/react-native-sdk-integration-and-implementation-guide#5-getpurposes2) section.

`SDK`

See the details from the [getSdksInPurpose(purposeId)](/latest/docs/react-native-sdk-integration-and-implementation-guide#6-getsdksinpurposepurposeid2) section.

### `BannerConfig`

| Property | Type | Description |
| --- | --- | --- |
| `hideCloseButton` | boolean | Whether to hide the close button |
| `hideAcceptButton` | boolean | Whether to hide the accept button |
| `embedDSRPortalLink` | boolean | Whether to embed DSR portal link |
| `recordConsentUponAppStart` | boolean | Whether to record consent on app start |
| `hideToggleForEssentialCategories` | boolean | Hide toggles for essential categories |
| `name` | string | The banner name |
| `dsrPortalLink` | string | Link to the DSR portal |
| `complianceType` | string | Values: “Notice-only”, “Opt-in”, or “Opt-out” |
| `bannerReappearanceTime` | string | When the banner should reappear |
| `privacyNoticeLink` | string | Link to privacy notice |
| `accept` | string | Localized accept button text |
| `reject` | string | Localized reject button text |
| `bannerText` | string | Localized banner text |
| `bannerHeading` | string | Localized banner heading |
| `sdkTabHeading` | string | Localized SDK tab heading |
| `privacyNoticeText` | string | Localized privacy notice text |
| `preferenceCenterLink` | string | Localized preference center link text |
| `permissionsTabHeading` | string | Localized Permission Tab Heading |
| `permissionsTabGuidance` | string | Localized Permission Tab Guidance |
| `preferenceCenterHeading` | string | Localized Preference Center Heading |
| `preferenceCenterGuidance` | string | Localized Preference Center Guidance |
| `permissionsTabDescription` | string | Localized Permissions Tab Description |
| `preferenceCenterDescription` | string | Localized Preference Center Description |
| `showPoweredBySecuritiLogo` | boolean | Should show the Security Logo or not |
| `showDescriptionTextWithPrefCenterToggle` | boolean | Should show the toggle description or not |
| `paletteTheme` | number | System palette number for pre-configured themes |
| `bannerPosition` | string | Values: “bottom” or “center” |
| `buttonShape` | string | Values: “rounded”, “square”, “pill”, “outlined” |
| `companyLogo` | string | Company Logo |
| `customPaletteTheme` | CustomColors | Custom color theme for banner |
| `shouldShowSettingsPrompt` | boolean | Should show Settings Prompt or not |
| `translations` | Record<string, string> | Map of translated strings |

### `CustomColors`

| Property | Type | Description |
| --- | --- | --- |
| `buttonBackground` | string | Hexcode for button background color |
| `buttonText` | string | Hexcode for button text color |
| `buttonBorder` | string | Hexcode for button border color |
| `bannerBackground` | string | Hexcode for banner background color |
| `bannerText` | string | Hexcode for banner text color |
| `bannerLinks` | string | Hexcode for banner link color |
| `preferenceCenterFooterBackground` | string | Hexcode for preference center footer background color |
| `preferenceCenterFooterSelector` | string | Hexcode for preference center footer selector color |

### `SettingsPrompt`

| Property | Type | Description |
| --- | --- | --- |
| `promptHeading` | string | Localized prompt heading text |
| `promptMessage` | string | Localized prompt message text |
| `settingsButtonText` | string | Localized settings button text |
| `notNowButtonText` | string | Localized “not now” button text |
| `permissions` | string[] | Permissions with settings prompt enabled |

### `PostConsentsRequest`

| Property | Type | Required | Description |
| --- | --- | --- | --- |
| `uuid` | string | Yes | Unique user identifier |
| `appUUID` | string | Yes | Application UUID |
| `device` | string | Yes | Device information |
| `implicitConsent` | boolean | Yes | Whether consent was implicit |
| `version` | number | Yes | Version of consent data |
| `purposeConsents` | PurposeConsent[] | Yes | Array of purpose consent data |
| `permissions` | PermissionConsent[] | Yes | Array of permission consent data |
| `isTestMode` | boolean | Yes | Whether in test mode |
| `adId` | string | Yes | Advertising identifier |
| `bannerInfo` | string | Yes | Banner information |
| `sdkVersion` | string | No | SDK version |
| `platform` | string | No | Platform information |

## Using Methods

Example usage in a React Native mobile app:

```javascript
import React, { useEffect, useState } from 'react';
import {
  View,
  StyleSheet,
  Text,
  ScrollView,
  ActivityIndicator,
  SafeAreaView,
  TouchableOpacity,
  Platform,
  Alert,
} from 'react-native';
// Import the functions from the library
import {
  initialize,
  presentConsentBanner,
  presentPreferenceCenter,
  isSdkReady,
  isReady,
  resetConsents,
  getConsentByPurposeId,
  getConsentByPermissionId,
  getPermissions,
  getPurposes,
  getSdksInPurpose,
  setPurposeConsent,
  setPermissionConsent,
  getBannerConfig,
  getSettingsPrompt,
  options,
  LoggerLevel,
  ConsentStatusValues,
} from 'securiti-consent-sdk';
// For types
import type {
  Purpose,
  AppPermission,
  SDK,
  BannerConfig,
  SettingsPrompt,
  CmpSDKOptions
} from 'securiti-consent-sdk';
// We'll use the isReady callback instead of native events
export default function App() {
  const [sdkReady, setSdkReady] = useState(false);
  const [isLoading, setIsLoading] = useState(false);
  const [response, setResponse] = useState<null | any>(null);
  const [purposes, setPurposes] = useState<Purpose[]>([]);
  const [permissions, setPermissions] = useState<AppPermission[]>([]);
  useEffect(() => {
    // Initialize SDK with appropriate options based on platform
  const initOptions: CmpSDKOptions = Platform.OS === 'android'
      ? {
          appURL: 'Your Android App URL',
          cdnURL: 'Your Android CDN URL',
          tenantID: 'Your Tenant ID',
          appID: 'Your Android App ID',
          testingMode: true,
          loggerLevel: LoggerLevel.DEBUG,
          consentsCheckInterval: 3600,
          subjectId: 'reactNativeAndroidSubject',
          languageCode: 'Your Language Code',
          locationCode: 'Your Location Code',
        }
      : {
          appURL: 'Your iOS App URL',
          cdnURL: 'Your iOS CDN URL',
          tenantID: 'Your Tenant ID',
          appID: 'Your iOS App ID',
          testingMode: true,
          loggerLevel: LoggerLevel.DEBUG,
          consentsCheckInterval: 3600,
          subjectId: 'reactNativeiOSSubject',
          languageCode: 'Your Language Code',
          locationCode: 'Your Location Code',
        };
    initialize(initOptions);
    console.log('Initialized SDK');
    // Use the isReady callback instead of events
    isReady((status) => {
      console.log('SDK ready callback received:', status);
      setSdkReady(status);
      if (status) {
        loadInitialData();
      }
    });
    // Also check using the synchronous method
    checkSdkReadiness();
    // No event listeners to clean up
    return () => {};
  }, []);
  const checkSdkReadiness = () => {
    // Synchronous check
    try {
      const ready = isSdkReady();
      setSdkReady(ready);
      console.log('SDK ready (sync check):', ready);
      if (ready) {
        loadInitialData();
      } else {
        // Also try the callback-based method
        isReady((ready) => {
          console.log('SDK ready (callback):', ready);
          setSdkReady(ready);
          if (ready) {
            loadInitialData();
          }
        });
      }
    } catch (error) {
      console.error('Error checking SDK readiness:', error);
    }
  };
  const loadInitialData = async () => {
    try {
      setIsLoading(true);
      console.log('Loading initial data...');
      // Load purposes and permissions in parallel
      const [purposesResult, permissionsResult] = await Promise.all([
        getPurposes(),
        getPermissions()
      ]);
      console.log('Purposes loaded:', purposesResult?.length || 0);
      console.log('Permissions loaded:', permissionsResult?.length || 0);
      setPurposes(purposesResult || []);
      setPermissions(permissionsResult || []);
    } catch (error) {
      console.error('Failed to load initial data:', error);
      Alert.alert('Error', 'Failed to load initial data');
    } finally {
      setIsLoading(false);
    }
  };
  const handleShowBanner = () => {
    try {
      presentConsentBanner();
      console.log('Consent banner presented');
    } catch (error) {
      console.error('Error presenting consent banner:', error);
      Alert.alert('Error', 'Failed to show consent banner');
    }
  };
  const handleShowPreferenceCenter = () => {
    try {
      presentPreferenceCenter();
      console.log('Preference center presented');
    } catch (error) {
      console.error('Error presenting preference center:', error);
      Alert.alert('Error', 'Failed to show preference center');
    }
  };
  const handleResetConsents = () => {
    setResponse(null);
    try {
      resetConsents();
      setResponse({
        message: 'Consents have been reset',
        timestamp: new Date().toISOString()
      });
      loadInitialData(); // Refresh data
    } catch (error) {
      console.error('Error resetting consents:', error);
      setResponse({ error: 'Failed to reset consents: ' + error });
    }
  };
  const handleGetPurposes = async () => {
    setResponse(null);
    setIsLoading(true);
    try {
      const result = await getPurposes();
      setResponse({
        purposes: result,
        timestamp: new Date().toISOString()
      });
      setPurposes(result || []);
    } catch (error) {
      console.error('Error getting purposes:', error);
      setResponse({ error: 'Failed to get purposes: ' + error });
    } finally {
      setIsLoading(false);
    }
  };
  const handleGetPermissions = async () => {
    setResponse(null);
    setIsLoading(true);
    try {
      const result = await getPermissions();
      setResponse({
        permissions: result,
        timestamp: new Date().toISOString()
      });
      setPermissions(result || []);
    } catch (error) {
      console.error('Error getting permissions:', error);
      setResponse({ error: 'Failed to get permissions: ' + error });
    } finally {
      setIsLoading(false);
    }
  };
  const handleGetSdksInPurpose = async (purposeId: number) => {
    setResponse(null);
    setIsLoading(true);
    try {
      const result = await getSdksInPurpose(purposeId);
      setResponse({
        purposeId,
        sdks: result,
        timestamp: new Date().toISOString()
      });
    } catch (error) {
      console.error('Error getting SDKs:', error);
      setResponse({ error: `Failed to get SDKs for purpose ${purposeId}: ` + error });
    } finally {
      setIsLoading(false);
    }
  };
  const handleGetBannerConfig = async () => {
    setResponse(null);
    setIsLoading(true);
    try {
      const result = await getBannerConfig();
      setResponse({
        bannerConfig: result,
        timestamp: new Date().toISOString()
      });
    } catch (error) {
      console.error('Error getting banner config:', error);
      setResponse({ error: 'Failed to get banner config: ' + error });
    } finally {
      setIsLoading(false);
    }
  };
  const handleGetSettingsPrompt = async () => {
    setResponse(null);
    setIsLoading(true);
    try {
      const result = await getSettingsPrompt();
      setResponse({
        settingsPrompt: result,
        timestamp: new Date().toISOString()
      });
    } catch (error) {
      console.error('Error getting settings prompt:', error);
      setResponse({ error: 'Failed to get settings prompt: ' + error });
    } finally {
      setIsLoading(false);
    }
  };
  const handleGetOptions = () => {
    setResponse(null);
    try {
      const sdkOptions = options();
      setResponse({
        options: sdkOptions,
        timestamp: new Date().toISOString()
      });
    } catch (error) {
      console.error('Error getting options:', error);
      setResponse({ error: 'Failed to get options: ' + error });
    }
  };
  const handleGetConsentForPurpose = async (purposeId: number) => {
    setResponse(null);
    setIsLoading(true);
    try {
      const result = await getConsentByPurposeId(purposeId);
      setResponse({
        purposeId,
        consentStatus: result,
        timestamp: new Date().toISOString()
      });
    } catch (error) {
      console.error('Error getting purpose consent:', error);
      setResponse({ error: `Failed to get consent for purpose ${purposeId}: ` + error });
    } finally {
      setIsLoading(false);
    }
  };
  const handleGetConsentForPermission = async (permissionId: string) => {
    setResponse(null);
    setIsLoading(true);
    try {
      const result = await getConsentByPermissionId(permissionId);
      setResponse({
        permissionId,
        consentStatus: result,
        timestamp: new Date().toISOString()
      });
    } catch (error) {
      console.error('Error getting permission consent:', error);
      setResponse({ error: `Failed to get consent for permission ${permissionId}: ` + error });
    } finally {
      setIsLoading(false);
    }
  };
  const handleSetConsentForPurpose = async (purpose: Purpose, consent: string) => {
    setResponse(null);
    setIsLoading(true);
    try {
      const success = setPurposeConsent(purpose, consent);
      console.log(`Set purpose consent result: ${success}`);
      // Give time for consent to apply
      await new Promise(resolve => setTimeout(resolve, 500));
      // Get updated status
      const newStatus = await getConsentByPurposeId(purpose.purposeId || 0);
      setResponse({
        message: `Set consent for purpose ${purpose.purposeId} to ${consent}`,
        success,
        newStatus,
        timestamp: new Date().toISOString()
      });
      // Refresh purposes list
      const updatedPurposes = await getPurposes();
      setPurposes(updatedPurposes || []);
    } catch (error) {
      console.error('Error setting purpose consent:', error);
      setResponse({ error: `Failed to set consent for purpose ${purpose.purposeId}: ` + error });
    } finally {
      setIsLoading(false);
    }
  };
  const handleSetConsentForPermission = async (permission: AppPermission, consent: string) => {
    setResponse(null);
    setIsLoading(true);
    try {
      const success = setPermissionConsent(permission, consent);
      console.log(`Set permission consent result: ${success}`);
      // Give time for consent to apply
      await new Promise(resolve => setTimeout(resolve, 500));
      // Get updated status
      const newStatus = await getConsentByPermissionId(permission.permissionId || '');
      setResponse({
        message: `Set consent for permission ${permission.permissionId} to ${consent}`,
        success,
        newStatus,
        timestamp: new Date().toISOString()
      });
      // Refresh permissions list
      const updatedPermissions = await getPermissions();
      setPermissions(updatedPermissions || []);
    } catch (error) {
      console.error('Error setting permission consent:', error);
      setResponse({ error: `Failed to set consent for permission ${permission.permissionId}: ` + error });
    } finally {
      setIsLoading(false);
    }
  };
  const renderPurposeItem = (purpose: Purpose) => {
    const purposeName = purpose.purposeName || `Purpose ${purpose.purposeId}`;
    return (
      <View style={styles.itemContainer} key={purpose.purposeId}>
        <Text style={styles.itemTitle}>{purposeName}</Text>
        <Text style={styles.itemSubtitle}>ID: {purpose.purposeId}</Text>
        <Text style={styles.itemSubtitle}>Status: {purpose.consentStatus || 'unknown'}</Text>
        <View style={styles.buttonRow}>
          <TouchableOpacity
            style={[styles.smallButton, styles.detailButton]}
            onPress={() => handleGetConsentForPurpose(purpose.purposeId || 0)}
          >
            <Text style={styles.smallButtonText}>Get Status</Text>
          </TouchableOpacity>
          <TouchableOpacity
            style={[styles.smallButton, styles.detailButton]}
            onPress={() => handleGetSdksInPurpose(purpose.purposeId || 0)}
          >
            <Text style={styles.smallButtonText}>Get SDKs</Text>
          </TouchableOpacity>
          <TouchableOpacity
            style={[styles.smallButton, styles.grantButton]}
            onPress={() => handleSetConsentForPurpose(purpose, ConsentStatusValues.GRANTED)}
          >
            <Text style={styles.smallButtonText}>Grant</Text>
          </TouchableOpacity>
          <TouchableOpacity
            style={[styles.smallButton, styles.declineButton]}
            onPress={() => handleSetConsentForPurpose(purpose, ConsentStatusValues.DECLINED)}
          >
            <Text style={styles.smallButtonText}>Decline</Text>
          </TouchableOpacity>
        </View>
      </View>
    );
  };
  const renderPermissionItem = (permission: AppPermission) => {
    const permissionName = permission.name || permission.permissionId || 'Unknown Permission';
    return (
      <View style={styles.itemContainer} key={permission.permissionId}>
        <Text style={styles.itemTitle}>{permissionName}</Text>
        <Text style={styles.itemSubtitle}>ID: {permission.permissionId}</Text>
        <Text style={styles.itemSubtitle}>Status: {permission.consentStatus || 'unknown'}</Text>
        <View style={styles.buttonRow}>
          <TouchableOpacity
            style={[styles.smallButton, styles.detailButton]}
            onPress={() => handleGetConsentForPermission(permission.permissionId || '')}
          >
            <Text style={styles.smallButtonText}>Get Status</Text>
          </TouchableOpacity>
          <TouchableOpacity
            style={[styles.smallButton, styles.grantButton]}
            onPress={() => handleSetConsentForPermission(permission, ConsentStatusValues.GRANTED)}
          >
            <Text style={styles.smallButtonText}>Grant</Text>
          </TouchableOpacity>
          <TouchableOpacity
            style={[styles.smallButton, styles.declineButton]}
            onPress={() => handleSetConsentForPermission(permission, ConsentStatusValues.DECLINED)}
          >
            <Text style={styles.smallButtonText}>Decline</Text>
          </TouchableOpacity>
        </View>
      </View>
    );
  };
  return (
    <SafeAreaView style={styles.container}>
      <ScrollView
        contentContainerStyle={styles.scrollContent}
        nestedScrollEnabled={true}>
        <View style={styles.header}>
          <Text style={styles.title}> Consent SDK Demo</Text>
          <Text style={styles.subtitle}>
            SDK Status: {sdkReady ? 'Ready' : 'Initializing...'}
          </Text>
        </View>
        <View style={styles.section}>
          <Text style={styles.sectionTitle}>Banner Controls</Text>
          <View style={styles.buttonRow}>
            <TouchableOpacity
              style={[styles.button, styles.primaryButton]}
              onPress={handleShowBanner}
            >
              <Text style={styles.buttonText}>Show Banner</Text>
            </TouchableOpacity>
            <TouchableOpacity
              style={[styles.button, styles.primaryButton]}
              onPress={handleShowPreferenceCenter}
            >
              <Text style={styles.buttonText}>Preference Center</Text>
            </TouchableOpacity>
          </View>
        </View>
        <View style={styles.section}>
          <Text style={styles.sectionTitle}>Get Configuration</Text>
          <View style={styles.buttonRow}>
            <TouchableOpacity
              style={[styles.button, styles.secondaryButton]}
              onPress={handleGetBannerConfig}
            >
              <Text style={styles.buttonText}>Banner Config</Text>
            </TouchableOpacity>
            <TouchableOpacity
              style={[styles.button, styles.secondaryButton]}
              onPress={handleGetSettingsPrompt}
            >
              <Text style={styles.buttonText}>Settings Prompt</Text>
            </TouchableOpacity>
            <TouchableOpacity
              style={[styles.button, styles.secondaryButton]}
              onPress={handleGetOptions}
            >
              <Text style={styles.buttonText}>SDK Options</Text>
            </TouchableOpacity>
          </View>
        </View>
        <View style={styles.section}>
          <Text style={styles.sectionTitle}>Manage Data</Text>
          <View style={styles.buttonRow}>
            <TouchableOpacity
              style={[styles.button, styles.secondaryButton]}
              onPress={handleGetPurposes}
            >
              <Text style={styles.buttonText}>Get Purposes</Text>
            </TouchableOpacity>
            <TouchableOpacity
              style={[styles.button, styles.secondaryButton]}
              onPress={handleGetPermissions}
            >
              <Text style={styles.buttonText}>Get Permissions</Text>
            </TouchableOpacity>
            <TouchableOpacity
              style={[styles.button, styles.warningButton]}
              onPress={handleResetConsents}
            >
              <Text style={styles.buttonText}>Reset Consents</Text>
            </TouchableOpacity>
          </View>
        </View>
        {isLoading && (
          <View style={styles.loaderContainer}>
            <ActivityIndicator size="large" color="#0000ff" />
          </View>
        )}
        {response && (
          <View style={styles.responseContainer}>
            <Text style={styles.sectionTitle}>Response:</Text>
            <ScrollView
              style={styles.responseScrollView}
              contentContainerStyle={styles.responseScrollContent}
              nestedScrollEnabled={true}
            >
              <Text selectable={true} style={styles.responseText}>
                {JSON.stringify(response, null, 2)}
              </Text>
            </ScrollView>
          </View>
        )}
        {/* Purposes Section */}
        <View style={styles.section}>
          <Text style={styles.sectionTitle}>Purposes</Text>
          {purposes.length === 0 ? (
            <Text style={styles.emptyText}>No purposes available</Text>
          ) : (
            purposes.map(renderPurposeItem)
          )}
        </View>
        {/* Permissions Section */}
        <View style={styles.section}>
          <Text style={styles.sectionTitle}>Permissions</Text>
          {permissions.length === 0 ? (
            <Text style={styles.emptyText}>No permissions available</Text>
          ) : (
            permissions.map(renderPermissionItem)
          )}
        </View>
      </ScrollView>
    </SafeAreaView>
  );
}
const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#f5f5f5',
  },
  scrollContent: {
    padding: 16,
  },
  header: {
    marginBottom: 20,
    alignItems: 'center',
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 8,
  },
  subtitle: {
    fontSize: 16,
    color: '#666',
    marginBottom: 8,
  },
  section: {
    marginBottom: 24,
    backgroundColor: '#fff',
    borderRadius: 8,
    padding: 16,
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 2 },
    shadowOpacity: 0.1,
    shadowRadius: 4,
    elevation: 2,
  },
  sectionTitle: {
    fontSize: 18,
    fontWeight: 'bold',
    marginBottom: 12,
  },
  buttonRow: {
    flexDirection: 'row',
    flexWrap: 'wrap',
    justifyContent: 'space-between',
    marginHorizontal: -4,
  },
  button: {
    margin: 4,
    padding: 12,
    borderRadius: 6,
    minWidth: 100,
    alignItems: 'center',
  },
  buttonText: {
    color: '#fff',
    fontWeight: 'bold',
  },
  primaryButton: {
    backgroundColor: '#2196F3',
  },
  secondaryButton: {
    backgroundColor: '#4CAF50',
  },
  actionButton: {
    backgroundColor: '#9C27B0',
  },
  warningButton: {
    backgroundColor: '#FF5722',
  },
  smallButton: {
    margin: 2,
    padding: 6,
    borderRadius: 4,
    minWidth: 60,
    alignItems: 'center',
  },
  smallButtonText: {
    fontSize: 12,
    color: '#fff',
    fontWeight: 'bold',
  },
  detailButton: {
    backgroundColor: '#607D8B',
  },
  grantButton: {
    backgroundColor: '#4CAF50',
  },
  declineButton: {
    backgroundColor: '#F44336',
  },
  loaderContainer: {
    padding: 20,
    alignItems: 'center',
  },
  responseContainer: {
    backgroundColor: '#fff',
    borderRadius: 8,
    padding: 16,
    marginBottom: 24,
    height: 300,
  },
  responseScrollView: {
    flex: 1,
    marginTop: 8,
    backgroundColor: '#f5f5f5',
    borderRadius: 4,
    borderWidth: 1,
    borderColor: '#e0e0e0',
  },
  responseScrollContent: {
    padding: 8,
  },
  responseText: {
    fontFamily: 'monospace',
    fontSize: 12,
    color: '#333',
  },
  itemContainer: {
    padding: 12,
    borderWidth: 1,
    borderColor: '#e0e0e0',
    borderRadius: 6,
    marginBottom: 8,
  },
  itemTitle: {
    fontSize: 16,
    fontWeight: 'bold',
    marginBottom: 4,
  },
  itemSubtitle: {
    fontSize: 14,
    color: '#666',
    marginBottom: 4,
  },
  emptyText: {
    padding: 16,
    textAlign: 'center',
    color: '#666',
  },
});
```

Open your terminal and run one of the following commands:

```plaintext
npx react-native run-android
```

or

```plaintext
npx react-native run-ios
```

This launches the app and display the consent banner at startup. To view the preference center, click the **Open Preference Center** button.

## Screenshots

![Banner.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a53bc812-c9ff-53ca-4f10-c18cfb3f510c.png)

*Mobile App Consent Banner*

![SDK_Purposes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e559f1a4-215c-518d-0836-82489a43932e.png)

*Mobile App Consent Preference Center - SDK Purposes Tab*

![Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-74f18cfe-75ad-568a-db2c-57d540fcf816.png)

*Mobile App Consent Preference Center - Permissions Tab*

![Essential_SDK_Expanded.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b76d1816-674e-a1b7-5efc-58772ae067c4.png)

*Mobile App Consent Preference Center - Essential SDK Expanded*

Purpose refers to one of the designated reasons for handling data, including the personal data of individuals, by those involved in the IAB EU TCF v2.2 consent framework. These reasons are outlined in the Policies or Specifications, and Vendors declare a Legal Basis for them in the Global Vendor List (GVL). The data subjects are given a choice, such as granting consent or expressing objection based on the Legal Basis for processing, facilitated by the CMP.

## Related

- [Assigning SDK Purposes](/assigning-sdk-purposes.md)
- [Using SDK Purposes](/using-sdk-purposes.md)
- [Using the SDK and Permissions Library](/using-the-sdk-and-permissions-library.md)
