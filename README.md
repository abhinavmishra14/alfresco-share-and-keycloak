# alfresco-share-and-keycloak

This project demonstrates how to configure Alfresco, Share, Nginx, and Keycloak in a Dockerized environment. It also shows how to integrate the Share interface with Keycloak for OIDC-based authentication.

## Important Configuration

- Create a local IP to HOST_NAME name mapping in in `hosts` file. e.g. 192.168.1.12 alfresco.local.com or 127.0.0.1 localhost.

- Add a hostname in host file to map to HOST_NAME variable in `.env` before running Docker Compose. This is used to start keycloak with a hostname.

- Review `alfresco-realm.json` in case you want to add/update any user or group. Do not change the realm and client configuration until first import. You can play around realm later and adjust accordingly as needed.

- TODO::


### Docker Image Versions used for this project

- Alfresco Content Services : 7.4.2.5-A1
- Share : 7.4.2.5-A1
- Keycloak : 24.0.3
- Alfresco Search Service (Solr6) : 2.0.15
- Postgres : 14.4
- Transform Service (CORE-AIO) : 5.1.7
- Active MQ : 5.18-jre17-rockylinux8

### Add-Ons used for this project

- OOTBee Support Tools : 1.2.2.0


### To build use following command:

- To build the images, This command will ignore any images which are already built and no changes to DockerFile has been identified. It will use cache.

`docker-compose -f ./docker-compose.yml build`

- To build the images with no cache. It will force rebuild

`docker-compose -f ./docker-compose.yml build --no-cache`


### To launch containers use following command:

`docker-compose -f ./docker-compose.yml up`


### To build and launch containers use following command:

`docker-compose -f ./docker-compose.yml up --build`


### To shutdown use following command:

`docker-compose -f ./docker-compose.yml down`

### To tail logs use following command:

`docker-compose -f ./docker-compose.yml logs -f`


### You can use launcher.bat/launcher.sh script to build, start, stop, purge volumes and tail logs:

- For Windows:

`.\launcher.bat build`

`.\launcher.bat start`

`.\launcher.bat stop`

`.\launcher.bat purge`

`.\launcher.bat tail`


- For Linux:

`.\launcher.sh build`

`.\launcher.sh start`

`.\launcher.sh stop`

`.\launcher.sh purge`

`.\launcher.sh tail`


## URLs to test services

http://localhost:8080

Alfresco Content App

* user: admin
* password: admin

http://localhost:8080/share

Share

* user: admin
* password: admin

http://localhost:8080/alfresco

Alfresco Content Services

* user: admin
* password: admin

http://localhost:8999

Keycloak

* user: admin
* password: admin

**Sample users and groups available to test with**

Users

* Username: admin | Password: admin
* Username: johndoe | Password: admin

Roles
* editorial_role
* default-roles-alfresco

Groups

* Editorial
* Administrator
