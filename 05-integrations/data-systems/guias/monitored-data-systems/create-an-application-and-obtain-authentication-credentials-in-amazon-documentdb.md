---
title: "Create an application and obtain authentication credentials in Amazon DocumentDB"
slug: "create-an-application-and-obtain-authentication-credentials-in-amazon-documentdb"
updated: 2026-07-01T15:36:22Z
published: 2026-07-01T15:36:22Z
canonical: "helpcenter.securiti.ai/create-an-application-and-obtain-authentication-credentials-in-amazon-documentdb"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create an application and obtain authentication credentials in Amazon DocumentDB

Securiti integrates with Amazon DocumentDB using a cluster in a Virtual Private Cloud (VPC). Integration with Amazon DocumentDB requires a user to have read-only access to all the databases (DBs).

The following parameters are required for activating the Amazon DocumentDB connector within the same VPC.

- Host: Amazon DocumentDB server host
- Port: Amazon DocumentDB server port number
- User: Master role username
- Password: Master role user password

Additional parameters are required for activating the Amazon DocumentDB connector outside VPC.

- SSH Host
- SSH Port
- SSH User
- SSH Certificate

Follow the matching procedure below to create a user and Amazon DocumentDB cluster.

See [Amazon's developer guide](https://docs.aws.amazon.com/documentdb/latest/developerguide/role_based_access_control.html) for more information on Role based Access Control.

1. Install Mongosh on your machine using [this link](/v1/docs/securiti-pods-and-elastic-pods).
2. Connect to your Amazon DocumentDB cluster using mongosh (the MongoDB shell) with the admin user, using the command below.

```plaintext
mongosh --ssl --host docdb-us-east-1.docdb.amazonaws.com:27017 --sslCAFile global-bundle.pem --username username --password password
```
3. Run the below command once connected, to create a user having read-only access to all databases in the cluster.

```plaintext
db.createUser({user: "user-name", pwd: "password", roles: [{role: "readAnyDatabase", db: "admin"}]})
```

Alternatively, you can create this user from the AWS console by following this [guide](https://docs.aws.amazon.com/documentdb/latest/developerguide/security.managing-users.html).

Record the username and password, to use later.
4. Create an Amazon DocumentDB cluster by following the [Amazon developer guide for cluster creation.](https://docs.aws.amazon.com/documentdb/latest/developerguide/db-cluster-create.html)

Record the values for host and port, to use later.
5. Perform the following additional steps to connect Amazon DocumentDB outside VPC. Refer to [Amazon developer guide](https://docs.aws.amazon.com/documentdb/latest/developerguide/connect-from-outside-a-vpc.html) for more details.
  1. Create an EC2 instance in the same VPC as your Amazon DocumentDB cluster by following the EC2 instance guide for [Windows](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/EC2_GetStarted.html) and [Linux](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html).
  2. Connect the EC2 instance by running the following command.

```plaintext
ssh -i "ec2Access.pem"
 ubuntu@ec2-34-229-221-164.compute-1.amazonaws.com
```
  3. Connect to your Amazon DocumentDB cluster using the following command.

```plaintext
mongo --sslAllowInvalidHostnames --ssl --sslCAFile
 global-bundle.pem --username <yourUsername> --password
 <yourPassword>
```

If this command works, it confirms that your EC2 instance and DocumentDB are in the same instance.
  4. Save the following parameters post connecting the EC2 instance for connector activation:
    - SSH Host
    - SSH User
    - SSH Port.
  5. Connect to your Amazon DocumentDB cluster by using the following command.

```plaintext
mongo --sslAllowInvalidHostnames --ssl --sslCAFile global-bundle.pem --username <yourUsername> --password <yourPassword>
```

The connection success confirms that EC2 and DocumentDB are both in the same VPC.
  6. Download the SSH PEM Certificate by following the [Amazon developer guide](https://docs.aws.amazon.com/documentdb/latest/developerguide/connect-from-outside-a-vpc.html). Save the file for connector activation.
6. Upload the *global-bundle.pem* file before connector activation if SSL is enabled for your Amazon DocumentDB cluster.
  1. Acquire the .pem certificate file from the [Amazon trust store](https://truststore.pki.rds.amazonaws.com/global/global-bundle.pem).
  2. In Securiti, go to **Settings > Integrations > Data Systems > Trust Store**
  3. Upload the certificate file on the Trust Store UI. See [Importing certificates into the Trust Store](/latest/docs/importing-certificates-into-the-trust-store), for more information.
7. Proceed to [Connecting Amazon DocumentDB with Securiti](/latest/docs/connecting-amazon-documentdb-with-securiti)
