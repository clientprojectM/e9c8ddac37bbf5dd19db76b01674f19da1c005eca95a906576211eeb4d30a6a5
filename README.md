## Dependencies
This project assumes you have the latest BL launcher. It uses the plugin jar and patches jar from client. You can update these by launching the launcher which will download the latest files. After a runelite update run client.repack task in gradle to create a repacked client jar from the latest runelite. 

## Starting the Client
Run the Client.main() gradle task to start the client. It will load externals as well as the plugins that come with the client so if you're working on your own external make sure its not also present in the externals folder or it will take that one over the classes in this project. It supports hotswapping classes. If this is enabled simply click the build button(the green hammer) for the Client.main() task while it is running. It may sometimes fail to build because theres conflicting classes on the classpath which aren't loaded in the right order. If this happens hotswapping will not work until you restart the client. I have no fix for this currently.

## Setting up externals
Make sure the package for your plugin starts with net.runelite.client.plugins. it is the same as developping a plugin inside the runelite project. When the project is build the jar containing all of the plugins will be in plugins/build/libs/plugins-1.0.jar. You can open this jar with a zip manager and delete the plugins you dont want to bundle. Feel free to rename the plugins-1.0.jar as well.
