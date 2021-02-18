---
description: A quick start to get you generating Iris worlds in no-time!
---

# Getting Started

### Compatibility

Iris is compatible with most world managers but Multiverse is the one we chose to actively interact with.

{% hint style="success" %}
If you want to replace the main Overworld with an Iris world, you have to follow [Replacing the Overworld](getting-started.md#replacing-the-overworld). If you want to create a new world with Iris, you have to follow [Creating a new World](getting-started.md#creating-a-new-world).
{% endhint %}

## Replacing the Overworld

1. **Install** [**Iris**](https://www.spigotmc.org/resources/iris-world-gen-the-dimension-engine.84586/) 
2. **Configure Bukkit** by adding the following to the bottom of the configuration file at `*/bukkit.yml`: `worlds:     world:       generator: Iris`
3. **Remove the world folder**, `*/world` before you start the server.
4. **Start the server**. _\*\*_
5. **Done!** You now have an Iris world as the main world!

{% hint style="info" %}
We recommend pregenerating a world to reduce lag: [FAQ - Pregeneration](plugin/faq.md#how-to-pregenerate-a-world)
{% endhint %}

## Creating a new World

1. **Install** [**Iris** ](https://www.spigotmc.org/resources/iris-world-gen-the-dimension-engine.84586/)**and** [**Multiverse Core**](https://dev.bukkit.org/projects/multiverse-core/files) 
2. **\(Re\)Start the server** 
3. **Run Iris Create**, \(more info [here](plugin/commands.md#iris-create)\) and replace `worldName` with the name of the world as you want it: `/iris create <worldName>`
4. **Run Multiverse Teleport**, \(more info [here](https://github.com/Multiverse/Multiverse-Core/wiki/Command-Reference#teleport-command)\) and - again - replace `worldName` with the name of the world as you used with step 4: `/mvtp <worldName>`

And confirm the teleport with  
`/mvconfirm`

1. **Done!** You now have a new Iris world!

{% hint style="info" %}
We recommend pregenerating a world to reduce lag: [FAQ - Pregeneration](plugin/faq.md#how-to-pregenerate-a-world)
{% endhint %}

#### Support

We offer support on our [Discord](https://discord.com/invite/3xxPTpT). You can ask questions there if you run into an error, for example, and want to know how to fix it.  
Thank you for using Iris!

* The Volmit Software Team

