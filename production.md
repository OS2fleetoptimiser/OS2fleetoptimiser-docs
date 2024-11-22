---
title: Production
layout: default
nav_order: 2
---
# Production
Below you can see the complete production setup for FleetOptimiser. If running in production mode, it's required that users are validated through Keycloak.
The users' type of access can be controlled through attributes on the identity provider or wide access can be given if environment variables are not provided.
Webproxy is optional, but if used, proxy set headers must be forwarded. 


![Production environment](/assets/foprod.png)



### Prerequisites 
- Environment capable of running docker and compose
- Keycloak, with a FleetOptimiser realm and client
- Access to a database (recommended) or mapping to a volume containing a db file

### Images 
We need the following images in order to run FleetOptimiser 
- fleetoptimiser-frontend:latest
- fleetoptimiser-backend:latest
- rabbitmq:3-management
- redis:latest

### Setup
As the production environment suggests, we need to make sure that the frontend and backend are on the same docker network.
We do this to allow communication between the two, but from the outside, clients are only able to reach through the frontend.
Hence, we don't need any authentication on the backend when we make the frontend middelware assert validity of the connection.

The backend, worker and queue management share network in order to direct the processing and be able to handle multiple tasks 
in the same environment. The worker and backend are on the same queue, so when a job is received it's queued to the right worker.
 
The _docker-compose.yaml_ is dependent on a _.prod-env_ file that expects the following variables:

| env                         | description                                                                                                                                      |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| CELERY_BACKEND_URL          | the uri to the running redis                                                                                                                     |
| CELERY_BROKER_URL           | the uri to the running rabbitmq                                                                                                                  |
| CELERY_QUEUE                | a unique name for the queue to use                                                                                                               |
| RABBITMQ_DEFAULT_USER       | a username used to login to service                                                                                                              |
| RABBITMQ_DEFAULT_PASS       | a password used to login to service                                                                                                              |
| DB_NAME (optional)          | name of the database                                                                                                                             |
| DB_USER (optional)          | user of the database                                                                                                                             |
| DB_PASSWORD (optional)      | password of the user on the database                                                                                                             |
| DB_URL (optional)           | host and port to the database                                                                                                                    |
| DB_SERVER (optional)        | dialect and driver                                                                                                                               |
| EXTRACTORS (optional)       | extractor to use when testing location precision. Comma separated list. Options; SKYHOST, MILEAGEBOOK, GAMFLEET, FLEETCOMPLETE, PUMA, SKYHOST_V2 |
| {EXTRACTOR}_KEYS (optional) | list of keys to use with EXTRACTORS                                                                                                              |
| TRIP_DURATION (optional)    | maximum number of days for a roundtrip                                                                                                           |  


In addition to the above backend environments. The following environment variables are typed directly in the _docker-compose.yaml_ file for the frontend. 


| env             | description                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------|
| KEYCLOAK_ID     | id of the keycloak registration                                                                  |
| KEYCLOAK_SECRET | secret of the keycloak client registration                                                       |
| KEYCLOAK_ISSUER | the realm authenticator of the keycloak provider                                                 |
| NEXTAUTH_SECRET | a secret for the frontend to validate authentication                                             |
| NEXTAUTH_URL    | host of the running application                                                                  |
| ROLE_CHECK      | the matching role from the authentication if the user has access, if present user must have this |
| ROLE_CHECK_READ | the matching role if user only has read access                                                   |


#### Database
DB environment variables are optional, since a dummy sqlite in memory DB will be loaded if nothing is provided.
When a connection to database is established the tables and necessary settings data will be created. 

#### Extractors
The extractor specific env variables are used to feed in fleet provider specific details (api keys etc.), in order to do _live_ testing of aggregation precision.
If not provided, the feature of testing precision when changing/adding parking spots will not work. Precision testing works with fleet management systems that does not require read entries to be patched. 

### Running FleetOptimiser
Run the queue services by running the following command
```
docker-compose -f redis-rabbit-docker-compose.yaml up
```

Run FleetOptimiser with frontend, backend api and a celery worker by running the following commnad
```
docker-compose -f docker-compose.yaml up
```

Now, FleetOptimiser can be accessed at the mapped port (localhost:8001).

