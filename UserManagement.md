# User management

Users are handled by the user plugin and Keycloak. The user plugin handles information about the user not specific to authentication and abstracts out many interactions with the auth server.

## Roles
When a plugin is registered it communicates what roles it requires. These will be added to Keycloak on registration and removed on unregistration. To prevent name confusion roles will be prefaced with the plugin name when created. For example a plugin `MyChat` with a `moderator` role will go into Keycloak as `MyChat_moderator`. 

## User registration
An endpoint should be exposed from the user plugin that allows new users to be added. It would require a `createUser` role on that plugin. This can be granted to plugins if a plugin is intended to be a user entry point.

## User deletion
As above, an endpoint should exist but require a `deleteUser` role on the user plugin.

## User modification
A user should be able to modify their own data. Node moderators can only do limited modification such as suspending a user.

## User verification
If a user's identity is known to the node moderators they can flag the user as verified.