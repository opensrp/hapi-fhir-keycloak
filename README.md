# HAPI FHIR --> Keycloak integration

This repository provides the functionality to integrate [HAPI FHIR](https://hapifhir.io/) with [Keycloak](https://www.keycloak.org/). 
It allows the following functionality
1. Secure all the HAPI FHIR endpoints to only be accessed by authenticated users
2. Authentication of users created on keycloak to use the HAPI FHIR API

## Future additions
1. Access control to HAPI FHIR endpoints via roles and user groups created on keycloak. 



### Spotless licensee and formatting

Spotless is a general purpose formatting plugin that we are using to manage our file formatting and license addition to 
our project files. Read more about the spotless integration [here](https://github.com/diffplug/spotless/tree/main/plugin-maven)

#### How to use 
1. `mvn spotless:check` -- Helps check for files that aren't formatted as the formatting plugin requires. 
2. `mvn spotless:apply` -- Applies the formatting and adds license headers to the project files. 
