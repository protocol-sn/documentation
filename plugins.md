# Protocol SN plugins

The protocolized social network is intended to be highly configurable. Nodes are able to add as many features as desired by registering plugins with the Node Manager.

## Plugin lib
A plugin library should be supplied that, when included in a build, handles features that are standard to the plugin and provides standardized configurations.

 - Registration - a bean that runs on service startup and registers the service with the Node Manager
 - Configuration
   - coop.protocolsn
     - node-manager
       - baseUrl - required - Where to find the node manager
       - registrationEndpoint - optional (default `/registerPlugin`) - url extension to register the plugin with the Node Manager
       - unregistrationEndpoint - optional (default `/unregisterPlugin`) - url extension to register the plugin with the Node Manager
     - registration
       - clientId - required - Unique identifier for this client as recognized by the Node Manager
       - clientSecret - required - secret recognized by the node manager
       - displayName - required - Human readable name for this plugin
       - clientBasUrl - optional - If the plugin has a client it wants to register it should be listed here
 - User authentication
   - Users