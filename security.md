# Protocol SN security

## Auth
Plugins communicate with each other, and users communicate with the plugins, via OAuth2. Keycloak is used as the authentication server. Each plugin can be used as an OAuth client. Plugins that require any particular roles will communicate them to the node manager on registration to be added to Keycloak.
