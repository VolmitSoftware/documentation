---
description: Iris configuration files
---

# Configuration

configuration for Iris itself is small because all world configuration is done in Packs \(more info [here](../engine/introduction-to-the-engine.md)\)

```javascript
{
    "studio": true,
    "commandSounds": true,
    "forceThreadCount": -1,
    "defaultWorldType": "overworld",
    "pluginMetrics": true,
    "systemEffects": true,
    "disableNMS": false,
    "parallaxChunkEvictionMS": 5000,
    "configurationVersion": 2,
    "parallaxRegionEvictionMS": 15000,
    "systemEntityInitialSpawns": true,
    "useServerLaunchedGuis": true,
    "streamingCacheSize": 8192,
    "maxAsyncChunkPregenThreads": 300,
    "sharedCaching": true,
    "maximumPregenGuiFPS": false,
    "maxBiomeChildDepth": 5,
    "splashLogoStartup": true,
    "systemEntitySpawnOverrides": true,
    "openVSCode": true,
    "forceSingleThreadedPerChunk": false,
    "verbose": false,
    "localPregenGui": true,
    "ignoreWorldEdit": false,
    "saveAllDuringPregen": true,
    "useGleamPregenerator": true
}
```

{% hint style="success" %}
We have introduced a hotloading feature for these settings, meaning they _should_ automatically update in the server.
{% endhint %}

## Studio

Studio mode allows you to design worlds with projects. Typically you want to keep this off on your production servers. This is only for when designing worlds with a local server.

```javascript
"studio": false,
```

## Command Sound

Commands with Iris have an autocomplete function in game. This setting toggles whether a sound effect is played when displaying / swapping through options and when running commands.

```javascript
"commandSounds": true,
```

## Force Thread count

Iris uses a system outside your server to generate chunks as fast as possible. You can manually set the amount of threads this system uses. The default \(when set to `-1`\) is the amount of Threads available for maximal power.

```javascript
"forceThreadCount": -1,
```

{% hint style="info" %}
Turning on `"useGleamPregenerator"`will overwrite this setting, effectively.
{% endhint %}

## Default world type

This changes the default pack Iris uses when running [`/iris create`](commands.md#iris-create) without specifying a `type` .

```javascript
"defaultWorldType": "overworld",
```

## Plugin Metrics

This toggles [plugin metrics for bstats](https://bstats.org/plugin/bukkit/Iris%20World%20Gen/8757). It helps us know what people are using so we can improve the plugin. All information is anonymous. Please leave this on :\)

```javascript
"pluginMetrics": true
```

## Effects System

Iris' Dimensions can play sound and particle effects. This setting globally toggles these effects.

```javascript
"systemEffects": true,
```

## Disable NMS

This setting turns NMS usage on and off. We use NMS \(Basically Minecraft source\) "hacking" to do two things: Allow for village & other vanilla structures to spawn in Iris worlds and to initialize worlds created very quickly. Turning this setting to `true` will disable both these systems.

```javascript
"disableNMS": false,
```

## Parallax Chunk Eviction MS

Iris uses a parallax system to hold information about objects & trees. The higher this value is, the longer Iris will keep information loaded in memory.

Making this value higher will make your chunks generate faster, but your server will use more memory. Making this lower does the opposite, it makes chunk generation slower, but your server will usel less memory.

```javascript
"parallaxChunkEvictionMS": 5000,
```

{% hint style="info" %}
The default is selected to ensure that most servers can run the pregen task fast without destroying RAM usage. If you're looking
{% endhint %}

## Configuration Version

We use this setting internally to make sure your settings are not faulty or outdated. Do not change this.

```javascript
"configurationVersion": 2,
```

## Parallax Region Eviction MS

This setting is very similar to [Parallax Chunk Eviction MS](configuration.md#parallax-chunk-eviction-ms). The difference is that a Region contains 1024 Chunks. These chunks are unloaded when we are sure they are no longer needed. Making this too low can cause chunks to not align anymore so we recommend keeping this at least `5000`. You can again make it higher for more speed at the cost of more RAM usage.

```javascript
"parallaxRegionEvictionMS": 15000,
```

## Initial Entity System

This toggles initial mob spawns in chunks. Initial entity spawns are defined in the pack. This has barely any effect on generation speed but may cause weird mobless chunks if turned off.

```javascript
"systemEntityInitialSpawns": true,
```

## Server launched GUI's

Turns GUI's on or off. Examples are the Noise, Pregeneration and Studio Map GUI's. If you are hosting locally we recommend keeping this on true, otherwise turn it to false.

```javascript
"useServerLaunchedGuis": true,
```

## Streaming Cache Size

Iris saves noise and terrain heightmaps for large maps. Making this lower will have severe impact on performance. Increasing this setting during pregeneration is recommended, especially when using the [Gleam Pregenerator](configuration.md#gleam-pregenerator). Make sure this setting is always a power of two \(`8192`, `16384`, `32768`, `65536`, `131072`\). This will increase memory \(RAM\) and CPU usage by quite a bit so do not overdo this.

```javascript
"streamingCacheSize": 8192,
```

## Shared Caching

## Maximum Pregen GUI FPS

Turning this to `true` will make the FPS of the pregeneration GUI a lot higher but it will also increase CPU usage, decreasing pregeneration speed. If you want to enjoy watching the GUI for a while, turn this to `true`, but keep it `false` if you are looking for maximum performance

```javascript
"maximumPregenGuiFPS": false,
```

## MaxBiomeChildDepth

Iris supports cyclic biome references. I.e. Desert could have a child biome of Savanna, and Savanna could technically also have a child of Desert if you design it that way. This parameter stops biome from infinitely generating too deep. Unless your biomes really take advantage of more than 5 layers of biome children \(depth\), there is usually no need to increase this. \(This also prevents infinite looooooping.\)

```javascript
"maxBiomeChildDepth": 5,
```

## Logo on Startup

Toggles whether or not the Iris logo is sent to the console on startup.

```javascript
"splashLogoStartup": true,
```

## Entity Override System

Just like the [Effects System](configuration.md#effects-system) and [Initial Entity System](configuration.md#initial-entity-system) this setting globally toggles entity overrides on or off. Iris has a few custom systems in place to overwrite normal mobs with, but you can turn those off here.

```javascript
"systemEntitySpawnOverrides": true,
```

## Open VSCode

When opening a project or creating a new project, Iris automatically opens VSCode, or the respective program associated with `.code-workspace` files. You can disable this. Note that this will never happen when the [Studio setting](configuration.md#studio) is disabled.

```javascript
"openVSCode": true,
```

## Force Single Thread per Chunk

This setting dictates whether one chunk can only be generated by one thread at a time. Turning this to `true` has near-negligible performance impact, but we recommend keeping to the default `false`.

```javascript
"forceSingleThreadedPerChunk": false,
```

## Verbose

Shows all files & objects being loaded when they are needed & additional information that may help you while developing projects. It is disabled by default for your own safety :P. Spams the console a lot, **a lot**.

```javascript
"verbose": false,
```

## Local Pregen GUI

Turns the local pregen GUI on or off separately from [Server launched GUI's](configuration.md#server-launched-guis). If that setting is set to `false`, this will be overwritten and the GUI will also be disabled.

```javascript
"localPregenGui": true,
```

## Ignore Worldedit

Awaiting more info on this....

```javascript
"ignoreWorldEdit": false,
```

## Save all during pregen

Awaiting more info on this....

```javascript
"saveAllDuringPregen": true,
```

## Gleam Pregenerator

Awaiting more info on this....

```javascript
"useGleamPregenerator": true
```

