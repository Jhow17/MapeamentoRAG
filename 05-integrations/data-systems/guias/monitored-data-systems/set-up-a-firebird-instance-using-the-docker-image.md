---
title: "Set up a Firebird instance using the docker image"
slug: "set-up-a-firebird-instance-using-the-docker-image"
updated: 2026-07-20T19:52:06Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/set-up-a-firebird-instance-using-the-docker-image"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Set up a Firebird instance using the docker image

This is an alternative method to create a Firebird server. Use this procedure if you do not have direct access or limited access to the Firebird server. Our recommended method for Firebird Connector is [Create and configure a Firebird server](/latest/docs/create-and-configure-a-firebird-server).

Refer to the matching procedure to set up a Firebird Instance using docker.

1. Download Docker software for your operating system using [Docker documentation](https://www.firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html).
2. Access your command terminal.
3. Use the following command to pull the docker image for Firebird.

```plaintext
docker pull jacobalberty/firebird
```

For more information about docker Firebird commands, refer to [docker hub documentation](https://www.firebirdsql.org/file/documentation/html/en/firebirddocs/qsg5/firebird-5-quickstartguide.html).
4. Use the following command to run the docker container.

```plaintext
docker run -p 3050:3050 -e EnableWireCrypt=true jacobalberty/firebird
```
5. Use the following command to run the docker logs and get Credentials.

```plaintext
 docker logs [containerID]
```

This command generates the following Credentials for Connector Activation:
  - Host
  - Port
  - Database file path
  - Username
  - Password
6. Record the above Credentials for Connector Activation.
7. Proceed to [Connect Firebird connector with Securiti](/latest/docs/connect-firebird-connector-with-securiti).
