---
description: All iris questions that we can think of will be put here
---

# FAQ

## How do I fix broken chunks?

Broken chunks are usually caused by one of the following issues:

1. [Updated Dimension for the world](faq.md#1-updated-dimension-for-the-world)
2. [Missing or invalid files in the Dimension for that world](faq.md#2-missing-files-in-the-dimension-for-that-world)
3. [Updates to Iris which were marked](faq.md#3-updates-to-iris-which-were-marked)
4. [Iris not being recognized as the generator used in the world](faq.md#4-iris-not-being-recognized-as-the-generator-used-in-the-world)

{% hint style="info" %}
If you do not think your issue is among these, feel free to contact [support](faq.md#support).
{% endhint %}

Solutions for each of these problems are listed below:

### 1. Updated Dimension for the world

If you followed the ["How To Update - Loaded Worlds" in Updates](../engine/updateoverworld.md#how-to-update-loaded-worlds) tutorial for the world you are having this issue in, the issue is most likely caused by that change. The only way to resolve this is by undoing the changes you made to update the pack by loading the backup you made \(we explicitly told you to\). Hopefully you followed our advise and made a back-up.

If you did not, you're out of luck; follow the warnings next time.

### 2. Missing files in the Dimension for that world

It can happen that you accidentally removed a file or made changes to it that invalidated the content. If this is the case, the issue is most likely caused by that. The way you want to resolve this is by reverting changes you made by either copying back the file from the trash bin \(or by copying the original from the GitHub repository for the Dimension, if it is available. [Overworld GitHub Repository](https://github.com/IrisDimensions/overworld)\), or by undoing or fixing changes to your files.

{% hint style="info" %}
If you cannot find what causes your biome not to be used, feel free to contact support on [Discord](https://discord.com/invite/3xxPTpT).
{% endhint %}

### 3. Updates to Iris which were marked

{% hint style="info" %}
The update notification sometimes contains something like this:

"This update may have an affect on your world"

It can vary somewhat from that sentence, but the idea is the same.
{% endhint %}

If you updated Iris to the latest version and find that new chunks are not lining up, it may be caused by a change in the underlying systems that dictate world generation. The way to go about resolving this is by replacing the "new" Iris by the old version you were using before \(hopefully you remember which one that was\). Old versions can be found on the [Version History](https://www.spigotmc.org/resources/iris-world-gen-the-dimension-engine.84586/history) page on Spigot.

### 4. Iris not being recognized as the generator used in the world

If you start seeing vanilla chunks where you expect Iris to make chunks, you may have an issue where Iris was forcibly removed as the generator of the world. This can happen when you did not properly follow the instructions found on the [Getting Started - Create the world with Iris](../getting-started.md#create-the-world-with-iris) page. You should go back there and follow the steps. You can regenerate broken / vanilla chunks with [/iris regen](commands.md#iris-regen).

## Can I uninstall Iris without issues?

There are multiple things Iris controls which will break when you uninstall the plugin. If you are alright with losing these features, you can uninstall the plugin.

Features that will break:

* **New chunks will not be custom:**  _New chunks will be normal vanilla chunks which do not align properly with existing chunks_
* **Custom particle & sound effects will disappear:**  _There are custom particles & sound effects which will no longer be \(dis\)played and replaced by \(boring\) vanilla equivalents_
* **Custom mob & animal spawns:**  _Iris has custom mob spawns which will be reverted to vanilla. This may lead to a steep decrease in the amount of mobs & animals spawning_

Another feature that may break is:

* **Custom leaf decay systems:** _\*\*Iris spawns custom trees which have leaves which are too far away from logs without them decaying. Iris controls leaf decay systems and uninstalling the plugin may result in leaves being removed where they shouldn't._

## Are there any unsupported plugins?

There are a few plugins that mess too much with Iris' content and soft dependencies. We try to ensure a smooth cooperation with most plugins, but these cross a line, unfortunately.

#### Unsupported plugins:

* Ultra Regions
* Region Manager
* Plugman
* Hotplug

## How to pregenerate a world?

{% hint style="warning" %}
If you try to pregen on a host it is recommended to set the following line in the `*/plugins/Iris/settings.json` file under `"gui":`to `false`:

`"localPregenGui": true`becomes `"localPregenGui": false`
{% endhint %}

You can pregenerate a world using the [/iris pregen ](commands.md#iris-pregen)command. Here is a quick step-by-step

1. **Teleport to the world**. You have to be in the world you want to generate to be able to run this command. 
2. **Run Iris Pregen**. You can now enter the pregen command. You can replace `distance` with the amount of blocks in a direction you want to generate.

   Command:  
   `/iris pregen distance`

We recommend to use `5000` for `distance` for servers with up to 10 players in total, adding `1000`for every additional players

Recommended command for less than 10 players:  
`/iris pregen 5000`

1. **Wait for the pregen to finish**. You will see updates on progress in the console around every 5 seconds. If you are hosting locally a window will also open where you can monitor progress directly.  Note that the pregeneration task can take quite some time depending on how much or little power Iris has access to, and the size of the task you give. If you ever have issues with the ram running full and your server crashing, decrease the [Parallax Chunk Eviction MS setting](configuration.md#parallax-chunk-eviction-ms) in the settings. Note that at the end of a pregeneration task, it can go over 100%. This is merely Iris filling up dead space, but it can take a while.

## How do I make biomes larger?

![Diagram of Dimension settings&apos; effects](../.gitbook/assets/image%20%284%29.png)

In this diagram you see what settings affect biome sizes. To make biomes larger, you can increase the zoom on the region's specific biomes [here](../engine/understanding/regions.md#4-biome-zooming), which will make the collection of biomes that are in a category larger. You can also change all biome & region sizes to be larger, this setting is found [here](../engine/understanding/dimensions.md#7-biome-and-region-zoom).

## Support

We offer support on our [Discord](https://discord.com/invite/3xxPTpT). Ask questions you cannot answer using the Wiki there.  
We ask you to look on the wiki for a solution for your issue before going there.  
Thank you for using Iris!

* The Volmit Software Team

