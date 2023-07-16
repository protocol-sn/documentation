# Protocol-based social network overview

Will use multiple interactive microservices build an extensible service. A centralized plugin manager will govern the interaction to allow users to take advantage of them seamlessly.

## Node Manager

A node is a singular instance of the social network. It is defined by its node manager. The node manager knows what plugins are available to the node. The node manager is itself a microservice.

The plugin manager also tracks the client id and client secret for expected plugins. It should reject registration attempts from plugins that are not expected.

### Endpoints

 - Register plugin
   - unsecured
   - POST
   - /registerPlugin
     - request
       - body
         - Str - `baseUrl` - base URL of the plugin
         - Str - `displayName` - Identifier for the plugin intended for end-user recognition
         - Str - `clientBaseURL` - If a URL should be displayed for a client (e.g. a browser client) put it here
       - headers
         - str - `client_id` - unique id for this plugin relative to this node
         - str - `client_secret` - functionally the plugin's password
       - response
         - 200
         - body
           - str - `bearerToken` - JWT to be used in future requests
 - Unregister plugin
   - Requires plugin credentials
   - DELETE
   - /unregisterPlugin
     - request
       - headers
         - str - 'authorization' - "Bearer " and bearer token.
 - List plugins
   - unsecured
   - GET
   - /plugins
     - request

## Users Plugin

Because at least a node admin user is necessary this plugin is necessary to run a node. It will be used to track users across the node and the roles they have across the various plugins.