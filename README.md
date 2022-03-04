# HAPI FHIR --> Keycloak integration

This repository provides the functionality to integrate [HAPI FHIR](https://hapifhir.io/) with [Keycloak](https://www.keycloak.org/). 
It allows the addition of following functionality to the [HAPI-FHIR Starter Project](https://github.com/hapifhir/hapi-fhir-jpaserver-starter) 
1. Secure all the HAPI FHIR endpoints to only be accessed by authenticated users
2. Authentication of users created on keycloak to use the HAPI FHIR API

[Here](https://github.com/opensrp/hapi-fhir-jpaserver-starter) is a sample use of this project

## Future additions
1. Access control to HAPI FHIR endpoints via roles and user groups created on keycloak.

## Development 

### Prerequisites

In order to extend this project, you should have:
- You may wish to create a GitHub Fork of the project and check that out instead so that you can customize the project and save the results to GitHub
- OpenJDK Java (JDK) installed: Minimum JDK8 or newer.
- Apache Maven build tool (the newest version)

### Code conventions
- The code conversions used for this project can be found [here](https://github.com/opensrp/hapi-fhir-keycloak/wiki)

## Usage

### How to use the project in the [HAPI-FHIR Starter Project](https://github.com/hapifhir/hapi-fhir-jpaserver-starter)

#### Adding dependencies
This project can be added to the [HAPI-FHIR Starter Project](https://github.com/hapifhir/hapi-fhir-jpaserver-starter) as a 
dependency. Here is the dependency to add to the `pom.xml`. Remember to always use the latest version. You can find the 
releases [here](https://github.com/opensrp/hapi-fhir-keycloak/tags). 

```
<dependency>
    <groupId>org.smartregister</groupId>
    <artifactId>hapi-fhir-keycloak</artifactId>
    <version>0.0.7-SNAPSHOT</version>
</dependency>

```

This [link](https://github.com/opensrp/hapi-fhir-jpaserver-starter/blob/d03bb85af65ec7b04034f6c2f5031810986ce64c/pom.xml#L143) has a sample of the addition. 

#### [HAPI-FHIR Starter Project](https://github.com/hapifhir/hapi-fhir-jpaserver-starter) Application configuration 
After adding the dependency you will need to add the keycloak configuration for the [`applicaton.yaml`](https://github.
com/opensrp/hapi-fhir-jpaserver-starter/blob/master/src/main/resources/application.yaml). Here is a sample of the 
configuration.

```
keycloak:
  auth-server-url: <keycloak_server_url>
  realm: <keycloak_realm_name>
  resource: <keycloak_client_oauth_id>
  credentials:
    secret: <keycloak_client_oauth_secret>
  ssl-required: external

```
This [link](https://github.com/opensrp/hapi-fhir-jpaserver-starter/blob/d03bb85af65ec7b04034f6c2f5031810986ce64c/src/main/resources/application.yaml#L183) has a sample of the addition.
