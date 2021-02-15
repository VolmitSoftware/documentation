---
description: How to install and configure VehiclesPlus
---

# Getting Started

## Downloading Requirements

Begin by downloading the latest versions of both [Vault ](https://www.spigotmc.org/resources/vault.34315/)and [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/). VehiclesPlus **requires** these plugins for various features.

Once you have downloaded both, head over to the [VehiclesPlus page](https://polymart.org/resource/vehiclesplus.633) to download the latest version.

{% hint style="info" %}
If you already have Vault and/or ProtocolLib installed, it doesn't hurt to check to make sure you are using the latest versions!
{% endhint %}

## Installing the Plugins

Installing all three plugins is actually quite simple. Just drop them directly into your `plugins` folder. Make sure to restart your server afterwards so that the plugins load on next startup.

{% hint style="warning" %}
Do not use `/reload` to reload your server! VehiclesPlus, and many other plugins, **will** break!
{% endhint %}

## Installing the Resource Pack

VehiclesPlus makes use of resource packs to display the 3D models of a vehicle. 

1. Because Minecraft changes resource pack formats quite often, we have designed a few example resource packs for your convenience. You can download the version that matches your server version [here](https://github.com/relavis/VehiclesPlus/tree/master/Resource%20Packs). 
2. Once you have downloaded the version that corresponds to your server version, you must upload the resource pack as a `.zip` file to a file sharing site of your choice, such as [Google Drive](https://drive.google.com), [Dropbox](https://www.dropbox.com), or similar.
3. Now that it is uploaded, it is time to edit your `server.properties` file. This file is located in the root directory of your server. Look for the line called `resource-pack=` and add the URL of the resource pack’s download link to the end of the line. It should look like this:

```text
resource-pack=https://yourdomain.com/ResourcePack.zip
```

Make sure to save and restart your server after applying these changes.

{% hint style="warning" %}
Your URL must be a **direct link** to your resource pack! If it does not end in `.zip`, Minecraft will be unable to recognize the link, and therefore unable to download the resource pack.
{% endhint %}

## \(Optional\) Editing Your Configuration

Once your server has been restarted, you will have new configuration files under `plugins/VehiclesPlus`. Take a look at our [Configuration page](setup/configuration.md) to determine whether or not you would like to change your configuration. Once you have edited the configurations, save your files and restart the server.

