# Protocol SN security

## Credentials
There are two types of credentials: user and plugin.

### User Credentials
User credentials are the normal credentials we see in most applications and are associated to a user account. These will use normal OAUTH2 flows

### Plugin Credentials
When a plugin registers with the node manager it is issued plugin credentials that can be used to authenticate its communication with the Node Manager or other plugins. Plugins must supply an agreed upon client id and client secret up on registration with the Node Manager to be issued credentials.