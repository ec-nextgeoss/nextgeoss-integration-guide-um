# NextGEOSS User Management Integration Guide

## Table of Contents
1. [Introduction](#introduction)
2. [General View](https://github.com/hector-rodriguez/um-nextgeoss/blob/master/general_view.adoc)
    1. [Authentication Flows](https://github.com/hector-rodriguez/um-nextgeoss/blob/master/general_view.adoc#authentication-flows)
    2. [Client Authentication](https://github.com/hector-rodriguez/um-nextgeoss/blob/master/general_view.adoc#client-authentication)
    3. [Request Endpoints for Authentication](https://github.com/hector-rodriguez/um-nextgeoss/blob/master/general_view.adoc#request-endpoints-for-authentication)
3. [Implementation on the Client Side](https://github.com/hector-rodriguez/um-nextgeoss/blob/master/client_implementation.adoc)
    1. [Registration](https://github.com/hector-rodriguez/um-nextgeoss/blob/master/client_implementation.adoc#registration)
    2. [Implementation Solutions](https://github.com/hector-rodriguez/um-nextgeoss/blob/master/client_implementation.adoc#implementation-solutions-for-js-clients)
4. [Implementation on the Service Side](https://github.com/hector-rodriguez/um-nextgeoss/blob/master/service_implementation.adoc)
5. [Resources for Developers](https://github.com/hector-rodriguez/um-nextgeoss/blob/master/dev_resources.adoc)


## Introduction <a name="introduction"></a>

The NextGEOSS User Management (UM) Service provides users with Single-Sign-On (SSO) authentication for accessing GEOSS data and services in a federated environment. In summary, the GEOSS UM Service demonstrates the following functionalities:

* Allow registration of users into a community (targeting the GEO/GEOSS community) and managing related user 'identity' information (user name, family name, email, telephone number, gender, ...);
* Allow registration directly via an existing social network login (from a user account on Google, Twitter, Facebook, ...) by importing that user 'identity' information;
* Allow authentication and authorization mechanisms towards acknowledged third-party services (targeting GEO/GEOSS services), based on user credentials defined at the level of the NextGEOSS UM Service;
* Allow registration of GEO/GEOSS services or applications (i.e. data harvesting, discovery, access, processing) that shall be subject to the definition of authentication and authorization mechanisms within the NextGEOSS UM Service.
* Provide SSO capability that enables a registered user to log in once, and access multiple GEO/GEOSS applications where the user signed-up already, without being required to authenticate for each application separately.
* Allow integration of other SSO systems (handled as identity providers, similarly to the handling of social network providers) in order to provide to existing EO data users a federation of GEO/GEOSS resources (e.g. ESA-https://eo-sso-idp.eo.esa.int, NASA-https://urs.earthdata.nasa.gov/). These systems could be based on different protocols: OpenID Connect, SAML2, Oauth2, ....

The NextGEOSS UM Service is based on OpenID Connect (OIDC) for authentication and UMA for the single-point authorization management allowing integration of social network login (Google, Twitter, Facebook, ...) and other SSO systems to provide a federation (ESA, NASA). Those SSO systems could be based on different protocols: OpenID Connect, SAML2 and OAuth2 integrated through proxies.

This version of the user guide is focusing on the processes to register and integrate NextGEOSS client services or applications (i.e. data harvesting, discovery, access and processing), and leverages the authentication based on OIDC protocol, and the authorization mechanisms based on OIDC scopes or UMA protocol.
