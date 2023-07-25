# ProtocolSN plugin library
This library contains all the standardized activities and configurations that any plugin will need.

## Registration
On startup register the plugin with the node manager. This will read the appropriate information from the plugin configurations and pass them on to the node manager.

## Inter-plugin communication
Abstract out the communication with other plugins