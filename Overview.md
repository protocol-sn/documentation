# Protocol-based social network overview

Will use multiple interactive microservices build an extensible service. A centralized plugin manager will govern the interaction to allow users to take advantage of them seamlessly.

## Node Manager

A node is a singular instance of the social network. It is defined by its node manager. The node manager knows what plugins are available to the node. The node manager is itself a microservice.

The plugin manager also tracks the client id and client secret for expected plugins. It should reject registration attempts from plugins that are not expected.

### Endpoints

 - Register plugin
 - Unregister plugin
 - List plugins

## Users Plugin

Because at least a node admin user is necessary this plugin is necessary to run a node. It will be used to track users across the node and the roles they have across the various plugins.