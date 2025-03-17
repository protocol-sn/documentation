# A Protocol-based social network

## Overview
The protocolized social network should offer the ability for distributed platforms to communicate on a shared and understood protocol. The building blocks of this network is nodes. Each node is capable of functioning as a standalone system, with its own user management and authentication, but should be able to communicate with other nodes, even sharing plugins with them.

A node must have three features: a node manager, an authentication tool (default is Keycloak), and a user plugin. The node manager is what defines an individual node, and it should be possible for a node to use authentication or user management from another node if desired.

All the interesting functions of the social network should be added in via plugins. What a plugin is as a user experience should be able to vary wildly, but they must at the least have a web service that can act as the plugin's line of communication with the node manager. These plugins should be able to access information on what other plugins are available on the node to determine how, if at all, they should interact. For example, if both an instant messenger plugin and image board plugin exist, the instant messenger should be able to embed images from the image board.

Users should be visible to their node, and where appropriate visible to nodes their node is connected to. Users will be domained to their node, preventing conflicting handles. For example if node-1 and node-2 both have user "John85" they can be distinguished as node-1::John85 and node-2::John85. A node's moderation team should have the ability to verify the identity of a user in at least three categories: "Unverified" for users whose identity has not been verified at all, "Verified Alias" where the moderation team knows the user's identity, but an alias is used publicly, and "publicly verified" where the moderation team knows the user's identity, and that identity is presented publicly.

Both users and plugins should have credentials with the authentication tool. Roles should be supplied to both to ensure they do not have more access than is necessary. Plugins will have their own authentication that may give them access to other plugins. Caution should be taken to ensure this does not allow users a backdoor to more data than they should be able to see.

Users and plugins that interact with other nodes will need to authenticate with that node, and will not necessarily have the same access they do on their own node. Node moderators will need to be cognizant of the degree to which they can trust another node. This can result in reduced access, and re-categorizing verification of users (e.g. verified by other node, but not trusted).

By default, the node manager should ship with a user interface that serves as a portal to any registered plugins, as appropriate. Plugins that would need direct user interaction should provide their own UI, which that portal can link to. Node moderators may benefit from crafting a UI that matches their specific needs after choosing what plugins to set up.

## Planning notes
The plan is to operate on a sort-of waterfall style. I will be setting goals for each minor version. The minor version goals will then be translated to tasks. The completion of each task will represent a patch version, with each repository having its own versioning. On achieving the goals for a minor release each relevant repo will be set to that minor release version. There is currently no plan for what will constitute a 1.0 release.
