# MinecraftPython

This tutorial works with Minecraft Java Edition 1.16.5

## Install the spigot server:

* Createa an empty directory on the server machine named `MinecraftPythonServer` in the home directory, then navigate the the directory by using:
```shell
cd ~/MinecraftPythonServer
```
* Download the spigot server from GetBukkit: https://getbukkit.org/download/spigot. Downlaod the right version of your choice and put the jar file in the above created folder.
* Extract and install the server with the downloaded jar file: spigot-1.16.5.jar by using the command:
```shell
java -Xms1024M -Xmx1024M -jar ./spigot-1.16.5.jar nogui
```
* The command above should generate an error for the first time of installation due to not accepting the user agreement EULA.
* Go to the installation directory and find the eula.txt file. Change the `accept=false` property from `false` to `true`. Save and exit.
* Enable firewall on the server's port:
```shell
sudo ufw allow 25565
```
* Re-run the server startup command:
```shell
java -Xms1024M -Xmx1024M -jar ./spigot-1.16.5.jar nogui
```

## Create a World on Server:
* Once the server is booted up, create a world by following the steps below.
* Open Minecraft game --> Play (ensure you have a paid account) --> Multiplayer --> Add Server --> Name: AdalMinecraftPython, IP: localhost:25565 --> done.
* Double click into the server to ensure everything is running okay, then exit.
* Stop the server by type the `stop` command on the commandline.

## Download the Install the RaspberryJuice Plugin to enable Python Interfacing:
* Download the plugin from https://www.spigotmc.org/resources/raspberryjuice.22724/. 
* Save the file to the plugins folder int the installation direcotry: ~/MinecraftPythonServer/plugins/raspberryjuice-1.12.1.jar
* Re-start the server. This time the raspberryjuice plugin will be found and applied.
```shell
java -Xms1024M -Xmx1024M -jar ./spigot-1.16.5.jar nogui
```

## Create a World on the **Client** machine: 
* Ensure minecraft is installed on your own client machine (different from server).
* Get into multiplayer mode and "add server". Use name: AdalMinecraftPython, IP: 10.4.10.8:25565
* Double click to enter the world.

## Install the Minecraft Python API mcpi tool on your **Client** machine: 
* Use the following command to install Python API:
```python
pip install mcpi
```
* Try the following python program on your client:
```python
import mcpi.minecraft as minecraft
import mcpi.block as block

mc = minecraft.Minecraft.create("10.4.10.8", 4711) # 10.4.10.8 is the IP of the server, 4711 is the socket port
mc.postToChat("Etown CS121!")
mc.getPlayerEntityIds()
```
* For more examples, visit: [link](https://github.com/AdventuresInMinecraft/code-files)
* For Python APIs, visit: [link](https://www.stuffaboutcode.com/p/minecraft-api-reference.html)

