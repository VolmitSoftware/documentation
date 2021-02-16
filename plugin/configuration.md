---
description: React configuration files
---

# Configuration

{% hint style="success" %}
We have introduced a hotloading feature for these settings, meaning they _should_ automatically update in the server
{% endhint %}

```text
features:
  react:
    style:

      #Use console coloring and formatting
      console-strip-color: true

      # Change the react text color to something else
      text-color: GRAY

      # Strip all color in chat from react
      # NOTE: Some parts of react may not respond
      # to this setting yet.
      strip-color: false

      # Change the react theme color to something else, or set it to RGB...
      theme-color: AQUA

      # Change the react dark color to something else.
      dark-color: DARK_GRAY
    saftey:

      # Treats item frames as dangerous, and prevents react from killing them, or
      # culling them. Set this to false to allow culling them with rules, or purging
      # them.
      treat-itemframes-dangerous: true

      # Treats armor stands as dangerous, and prevents react from killing them, or
      # culling them. Set this to false to allow culling them with rules, or purging
      # them.
      treat-armorstands-dangerous: true
    modes:

      # Disable all capabilities for react to unload chunks
      safemode-unload-chunks: false

      # Disable all capabilities for react to interact with FastAsyncWorldEdit
      # (FAWE).
      safemode-fawe: false

      # Disable all capabilities for react to communicate to the internet. I.e. Cant
      # create pastebin reports, or use stats.
      safemode-networking: false

      # Disable all capabilities for react to interact with the game's protocol. I.e.
      # Sending & intercepting packets, Ping and other features.
      safemode-protocol: false

      # Disables all capabilities for react to utilize NMS classes in CraftBukkit.
      # Use this if either you are having serious problems, or are using
      # Sponge,MCPC+,KCauldron, or even Glowkit
      safemode-nms: false
    spikes:

      # The time a report will not show again for (in ticks) after it was just shown
      time-nag: 200

      # Monitor the main thread and warn the chat AND console if the server is
      # locked. Please note that there is no way of knowing if the server is during a
      # garbage collection. This means there WILL BE false positives. Especially with
      # react.
      report-spikes: true

      # Save tracked spikes to React/spikes
      save-spikes: false

      # Due to word wrapping and hover elements, react hides the full package names
      # by default.
      # For example net.minecraft.server.V1_12R2 would be converted to
      # n.m.s.V
      show-fully-qualified-names: false

      # The average time in milliseconds a spike must make to trigger the spike
      # message.
      time-radius: 2000
    tick-splitter:

      # Slows down block physics on a per world basis if the maximum ticks per world
      # is exceeded
      max-ticks-per-world: 180

      # Enable or disable React AI
      enabled: true
    monitor:

      # Double crouching quickly locks and unlocks the monitor. Turn this off if you
      # have a plugin such as vanish that uses this kind of mechanic. (/re mon -lock
      # still works)
      double-sneak-lock: true

      # The default ping in ms.
      default-ping: -1

      # Use protocollib to monitor keep alive packets to get super accurate (non
      # averaged) ping values. Most ping plugins just grab the value from bukkit, but
      # that value is usually inaccurate due to intense averaging paired with the
      # slow ping update speed.
      fast-ping: true

    # Notify action completions via advancements (1.9+)
    advancements: false
    command-overrides:

      # Override the /tps and /lag commands to add additional information
      tps: true

      # Override the '/killall all' command to instead use react to remove entities.
      killall: false

      # Interpret '/killall all -f' as /re a pe -f (force kill everything but
      # players)
      killall-force: false

      # Override /mem with additional information
      memory: true
    queue:

      # Learns the patterns of repeated executions and attempts to grab low cpu tasks
      # and burn through them to improve low ms latency.
      group-suppression: true
    collision:

      # Disables collision for entities about to be culled.
      disable-collide-on-pre-cull: true

      # Disables collision for certain entities based on lag and conditions.
      collision-tweaks-enabled: true
      disable-collide-always:
      - BAT
      disable-collide-spawner:
      - BAT
      - BLAZE
      - CAVE_SPIDER
      - CHICKEN
      - COD
      - COW
      - CREEPER
      - DOLPHIN
      - DONKEY
      - DROWNED
      - ELDER_GUARDIAN
      - ENDER_DRAGON
      - ENDERMAN
      - ENDERMITE
      - EVOKER
      - FALLING_BLOCK
      - FISHING_HOOK
      - GHAST
      - GIANT
      - GUARDIAN
      - HORSE
      - HUSK
      - ILLUSIONER
      - IRON_GOLEM
      - LLAMA
      - LLAMA_SPIT
      - MAGMA_CUBE
      - MINECART
      - MINECART_CHEST
      - MINECART_COMMAND
      - MINECART_FURNACE
      - MINECART_HOPPER
      - MINECART_MOB_SPAWNER
      - MINECART_TNT
      - MULE
      - MUSHROOM_COW
      - OCELOT
      - PAINTING
      - PARROT
      - PHANTOM
      - PIG
      - PIG_ZOMBIE
      - POLAR_BEAR
      - PUFFERFISH
      - RABBIT
      - SALMON
      - SHEEP
      - SHULKER
      - SILVERFISH
      - SKELETON
      - SKELETON_HORSE
      - SLIME
      - SNOWMAN
      - SPIDER
      - SQUID
      - STRAY
      - TRIDENT
      - TROPICAL_FISH
      - TURTLE
      - VEX
      - VILLAGER
      - VINDICATOR
      - WITCH
      - WITHER
      - WITHER_SKELETON
      - WOLF
      - ZOMBIE
      - ZOMBIE_HORSE
      - ZOMBIE_VILLAGER
    beta:

      # Try some beta stuff [NOT RECCOMENDED] use at your own risk
      junk: false
    map:

      # Cap the framerate of the map. Bukkit hard caps at 60, anything higher than 60
      # will do nothing. Keep in mind that the higher the frame rate, the more bukkit
      # will spawn craft scheduler threads. Keeping this low reduces memory, cpu
      # usage and allows more people to use the map at the same time.
      max-framerate: 20

      # Cap the framerate of the individual graphs in the react map. Keep this value
      # low as there are many graphs to map.
      max-graph-framerate: 5

    # Disable all automatic actions, including RAI. Will still purge chunks if
    # enabled.
    monitoring-only: false
    rai:

      # Enable or disable React AI
      enabled: true

      # RAI will do nothing unless the tps drops below this value for more than 20
      # ticks. It does, rai will look for issues to fix.
      activation-threshold: 18.5
    sampler:

      # Modify the average radius of the server tps sampler
      tps-average-radius: 7

      # Sample time viewport. Higher means more visible data in graphs over time. Due
      # to lossy compression however, data may look weird near the beginning of a
      # large graph.
      sample-viewport: 12000

      # Modify the average radius of server tick time sampler
      tick-time-average-radius: 3

      # Sample points per sampler type
      sample-points: 250
    sound:

      # 'Meow' instead of 'Plop'
      meow: false

    # Use Fast Async World Edit if it is installed.
    use-fawe: true
    purge:

      # Allow the purger to purge named entities
      allow-purge-named: false

      # Allow the purger to purge item drops
      allow-purge-drops: false

      # Allow the purger to purge tamed entities
      allow-purge-tamed: false

    # Language to use. Languages are downloaded from
    # https://github.com/VolmitSoftware/React/tree/master/language
    language: enUS

    # Enable the ability for players to request temporary access to react. Admins
    # must accept the request. Admins are always able to revoke access too.
    allow-tempaccess: true

    # Use NMS Adapters. Disabling this will basically make any nms or fast options
    # do nothing either way. This may fix issues with FAWE and chunks on 1.8.8
    # though
    nms-adapters: true

    # Play sounds during react's usage (chat, monitor, map, etc)
    interaction-sounds: true
    actions:

      # Actions such as lock-redstone, lock-hoppers, and lock-fluids. Should they
      # ever be un-frozen (using the time field)
      unlock-locked-actions: true

    # Notify config hotloads via advancements (1.9+)
    advancement-on-hotload: false
    legacy:
      remote-server:

        # Use the legacy remote server (for react remote)
        enable-react-remote-server: false

        # The port to bind to when the remote server is enabled. This cannot be your
        # server port or an already used port.
        remote-port: 8147
    worlds:

      # Generate seperate configurations for each world (disable this if you have
      # over 100 worlds)
      world-configs: true

    # Opens an inventory gui to fire an action when using /re act. You can still
    # change pages with /re act 1 and /re act 2 etc
    action-panel: true
  mythic-mobs:

    # If mythic mobs is enabled, use mob stacking on them
    allow-stacking: false

    # If mythic mobs is enabled, allow purging of them with /re a pe
    allow-purging: true
    allow-culling: true
  entity-stacker:
    options:

      # Format for nametags
      # %size% = Number of entities in stack
      # %type% = Entity type
      # i.e. Pig
      # %hp% = Health
      # Color codes and formatting supported.
      nametag-format: '&e%size%x &a%type% &c%hp%'

      # Increase sheep wool drops depending on stack size
      sheep-wool-drops: true

      # Show a nametag of the stacked entity
      show-nametag: false

      # Only stack sheep with the same color
      sheep-color-specific: false

      # Show particles on stacked entities. More particles = bigger stack. This is if
      # you don't want to directly show players the stack size.
      show-particles: true

    # Try to stack entities in different locations on an interval.
    stack-on-interval: true

    # Speed up interval stacking by queueing each entity to stack as often as
    # possible in a 1 second time window.
    fast-intervals: false

    # The radius (in blocks) to search for entities to stack together.
    search-radius: 6
    enabled: false

    # Scale all damage causes except for player x entity damage with the stack
    # size. This means a stacked pig would have the same effective health by
    # scaling damage to that pig. Excludes player damage.
    non-player-damage-normalization: true

    # The maximum size an entity stack can have
    max-stack-size: 16

    # The minimum number of entities required in a search radius to actually create
    # a stack. Setting this lower will create frequent small-stacks, higher will
    # make larger stacks less often.
    minimum-group-size: 6
    stack-reasons:
    - natural
    - jockey
    - chunk_gen
    - spawner
    - egg
    - spawner_egg
    - lightning
    - build_snowman
    - build_irongolem
    - build_wither
    - village_defense
    - village_invasion
    - breeding
    - slime_split
    - reinforcements
    - nether_portal
    - dispense_egg
    - infection
    - cured
    - ocelot_baby
    - silverfish_block
    - mount
    - trap
    - ender_pearl
    - shoulder_entity
    - drowned
    - sheared
    - explosion
    - raid
    - patrol
    - beehive
    - custom
    - default

    # The maximum health a stacked entity can have. (make sure this is below
    # spigots limits if you changed them)
    max-health: 1600

    # Try to stack entities around a newly spawned entity.
    stack-on-spawn: false

    # Cache stack data through reboots, unloads and reloads.
    persist-stacks: true
  culling:
    mark-for-death:

      # Use particles to indicate an entity has been marked for death, and when they
      # are removed (village angry & explosion)
      particles: true
      name-tags:
        enabled: false

        # Use nametags for a countdown
        format: '&6⚠ &7%time%'

      # The time between an entity being marked for death and actually being
      # killed.
      # In ticks. Setting this to 100 would mark an entity for death, then
      # actually kill it 5 seconds later.
      death-time: 150
  tick-smearing:
    tiles:

      # Allow the tile tick throttle to be X higher than the current time to prevent
      # odd skipping of entities, and to allow room for error.
      seperation-bias: 0.07

      # How many ticks should the tick time be averaged across to compute biases
      smear-factor: 50.0

      # The maximum tile tick time before throttling
      max-time: 35.0

      # Enable entity tick throttling
      enable: true
    entities:

      # How many ticks should the tick time be averaged across to compute biases
      smear-factor: 50.0

      # Enable entity tick throttling
      enable: true

      # The maximum tile tick time before throttling
      max-time: 30.0

      # Allow the tile tick throttle to be X higher than the current time to prevent
      # odd skipping of entities, and to allow room for error.
      seperation-bias: 0.65
  glass:

    # The maximum amount of events to capture per tick before ignoring the rest to
    # prevent lag from glass.
    max-queue: 256

    # Display particles instead of block packets to visualize physics (better
    # framerates than block packets)
    display-particles: true

    # Display glass-block packets to visualize physics
    display-blocks: false
  entity-culler:
    enabled: true

    # Should react autocull near players (in their view distances) constantly to
    # enforce entity limits in the culling rules? Please keep in mind that there
    # may be a performance comprimise here.React AI only culls what is causing lag.
    # This abolishes that idea.
    auto-cull: false
  console:

    # Uses the listen-channels to print to the console.
    # Channels:
    # -rai
    # -spikes
    # -verbose
    # -action
    # -gc 
    listen-channels-enabled: false
    listen-channels:
    - rai
    - verbose
    - spikes
    - action
    - gc
tweaks:
  chunks:

    # Bypass forced open chunks to be purged, 1.13+ only
    force-bypass: true

    # Should chunk purging be enabled? Only chunks OUTSIDE of every player's view
    # distance combined are purged.
    purge-enabled: true

    # The interval at which chunks are purged. Only chunks OUTSIDE of every
    # player's view distance combined are purged.
    purge-interval: 1200

    # Chunk purge distance multiplier (multiplied by the server's view distance)
    distance-multiplier: 1.5
  fast-leaf-decay:

    # Use fast block destruction for fast leaf decay. Turn this on if you dont like
    # snow floating above leaves, though you lose most of the performance benefits
    # of fast decay.
    fast-destroy: true

    # The maximum milliseconds react is allowed to use to fast-leaf decay
    max-ms: 0.8
    enabled: true

    # Trigger fast leaf decay when leaves decay normally
    trigger-on-decay: true

    # Saturate the destruction queue as fast as possible, ignoring tick limits.
    instantaneous: false

    # The period of time (in ticks) which a leaf block that is marked for decay
    # will actually decay. If 10 blocks are set to be destroyed, they will be
    # destroyed randomly within 7 ticks (by default)
    decay-period: 7
  explosions:

    # The percent of tnt to be removed when tnt is over the max ms limit
    throttled-ratio: 0.65

    # Throttle explosions to a maximum tick time per tick
    max-explosions-milliseconds: 5.0

    # Skip block physics for explosion block damage. Breaks cannons obviously.
    fast-block-destruction: false

    # Throttle explosions by removing a percentage of tnt entities after it has
    # exceeded the max ms set. This obviously breaks cannons.
    throttle-explosions: true
  xp:

    # Fast pickup xp (pick up all xp orbs at once.)
    fast-xp-pickup: false

    # Skip spawning xp orbs if the player who caused the xp to drop is known (just
    # give them the xp). Reduces entities.
    fast-drop-xp: false

  # If factions is installed, this option will configure react to be more
  # compatible with a factions server (cannon stuff etc)
  factions-compat: true
  drops:

    # Drops spawned from entities or blocks will not have a pickup cooldown. This
    # reduces left behind drops while mining.
    fast-drop-items: false

    # Instant teleport drops to the nearest player (only from entities and block
    # drops)
    teleport-to-source: false

    # Despawn arrows that cannot be picked up by players anyways. (Think skeleton
    # arrow landed entities).
    despawn-useless-arrows: true
  hoppers:

    # Full hoppers for some reason spam-tick and cause a ton of lag. React helps by
    # preventing this from happening.
    reduce-overtick-hoppers: true
  redstone:

    # Dynamically change the redstone tick speed depending on redstone tick time
    # (may cause issues with large contraptions)
    dynamic-clocking: false
  fast-growth:
    enabled: true
entity-types:
  culling-rules:
  - '@Refuse Tamed'
  - '@Defer Named'
  - '@Defer Leashed'
  - '@Defer Stacked'
  - '@Defer Ridden'
  - '@Defer Mythic'
  - '@Defer Young'
  - '@Defer Non-Living'
  - '@Defer Grounded'
  - '@Defer Passive'
  - '@Defer Lit'
  - '@Prefer Living'
  - '@Prefer Hostile'
  - '@Prefer Mature'
  - '@Prefer Underwater'
  - '@Prefer Airborne'
  - '@Prefer Projectiles'
  - '@Prefer Caves'
  - '@Restrict Pig,Cow,Sheep,Chicken = 14'
  - '@Restrict Zombie,Spider,Skeleton,Creeper = 14'
  - '@Restrict Wolf,Ocelot,Horse = 9'
  - '@Restrict Pufferfish,Tropical Fish,Squid = 3'
  - '@Restrict Area Effect Cloud = 16'
  - '@Restrict Armor Stand = 16'
  - '@Restrict Arrow = 16'
  - '@Restrict Bat = 16'
  - '@Restrict Blaze = 16'
  - '@Restrict Boat = 16'
  - '@Restrict Cave Spider = 16'
  - '@Restrict Chicken = 16'
  - '@Restrict Cod = 16'
  - '@Restrict Complex Part = 16'
  - '@Restrict Cow = 16'
  - '@Restrict Creeper = 16'
  - '@Restrict Dolphin = 16'
  - '@Restrict Donkey = 16'
  - '@Restrict Dragon Fireball = 16'
  - '@Restrict Dropped Item = 30'
  - '@Restrict Drowned = 16'
  - '@Restrict Egg = 16'
  - '@Restrict Elder Guardian = 16'
  - '@Restrict Ender Crystal = 16'
  - '@Restrict Ender Dragon = 16'
  - '@Restrict Ender Pearl = 16'
  - '@Restrict Ender Signal = 16'
  - '@Restrict Enderman = 16'
  - '@Restrict Endermite = 16'
  - '@Restrict Evoker = 16'
  - '@Restrict Evoker Fangs = 16'
  - '@Restrict Experience Orb = 16'
  - '@Restrict Falling Block = 16'
  - '@Restrict Fireball = 16'
  - '@Restrict Firework = 16'
  - '@Restrict Fishing Hook = 16'
  - '@Restrict Ghast = 16'
  - '@Restrict Giant = 16'
  - '@Restrict Guardian = 16'
  - '@Restrict Horse = 16'
  - '@Restrict Husk = 16'
  - '@Restrict Illusioner = 16'
  - '@Restrict Iron Golem = 16'
  - '@Restrict Item Frame = 16'
  - '@Restrict Lightning = 16'
  - '@Restrict Lingering Potion = 16'
  - '@Restrict Llama = 16'
  - '@Restrict Llama Spit = 16'
  - '@Restrict Magma Cube = 16'
  - '@Restrict Minecart = 16'
  - '@Restrict Minecart Chest = 16'
  - '@Restrict Minecart Command = 16'
  - '@Restrict Minecart Furnace = 16'
  - '@Restrict Minecart Hopper = 16'
  - '@Restrict Minecart Mob Spawner = 16'
  - '@Restrict Minecart Tnt = 16'
  - '@Restrict Mule = 16'
  - '@Restrict Mushroom Cow = 16'
  - '@Restrict Ocelot = 16'
  - '@Restrict Painting = 16'
  - '@Restrict Parrot = 5'
  - '@Restrict Phantom = 16'
  - '@Restrict Pig = 16'
  - '@Restrict Pig Zombie = 16'
  - '@Restrict Polar Bear = 16'
  - '@Restrict Primed Tnt = 16'
  - '@Restrict Pufferfish = 3'
  - '@Restrict Rabbit = 16'
  - '@Restrict Salmon = 16'
  - '@Restrict Sheep = 16'
  - '@Restrict Shulker = 16'
  - '@Restrict Shulker Bullet = 16'
  - '@Restrict Silverfish = 16'
  - '@Restrict Skeleton = 16'
  - '@Restrict Skeleton Horse = 16'
  - '@Restrict Slime = 16'
  - '@Restrict Small Fireball = 16'
  - '@Restrict Snowball = 16'
  - '@Restrict Snowman = 16'
  - '@Restrict Spectral Arrow = 16'
  - '@Restrict Spider = 16'
  - '@Restrict Splash Potion = 16'
  - '@Restrict Squid = 16'
  - '@Restrict Stray = 16'
  - '@Restrict Thrown Exp Bottle = 16'
  - '@Restrict Tipped Arrow = 16'
  - '@Restrict Trident = 16'
  - '@Restrict Tropical Fish = 3'
  - '@Restrict Turtle = 3'
  - '@Restrict Unknown = 16'
  - '@Restrict Vex = 16'
  - '@Restrict Villager = 16'
  - '@Restrict Vindicator = 16'
  - '@Restrict Weather = 16'
  - '@Restrict Witch = 16'
  - '@Restrict Wither = 16'
  - '@Restrict Wither Skeleton = 16'
  - '@Restrict Wither Skull = 16'
  - '@Restrict Wolf = 16'
  - '@Restrict Zombie = 16'
  - '@Restrict Zombie Horse = 16'
  - '@Restrict Zombie Villager = 16'
  allow-stacking:
  - BAT
  - BLAZE
  - CAVE_SPIDER
  - CHICKEN
  - COD
  - COW
  - CREEPER
  - DOLPHIN
  - DONKEY
  - DROWNED
  - ELDER_GUARDIAN
  - ENDER_DRAGON
  - ENDERMAN
  - ENDERMITE
  - EVOKER
  - FALLING_BLOCK
  - FISHING_HOOK
  - GHAST
  - GIANT
  - GUARDIAN
  - HORSE
  - HUSK
  - ILLUSIONER
  - IRON_GOLEM
  - LLAMA
  - LLAMA_SPIT
  - MAGMA_CUBE
  - MINECART
  - MINECART_CHEST
  - MINECART_COMMAND
  - MINECART_FURNACE
  - MINECART_HOPPER
  - MINECART_MOB_SPAWNER
  - MINECART_TNT
  - MULE
  - MUSHROOM_COW
  - OCELOT
  - PAINTING
  - PARROT
  - PHANTOM
  - PIG
  - PIG_ZOMBIE
  - POLAR_BEAR
  - PUFFERFISH
  - RABBIT
  - SALMON
  - SHEEP
  - SHULKER
  - SILVERFISH
  - SKELETON
  - SKELETON_HORSE
  - SLIME
  - SNOWMAN
  - SPIDER
  - SQUID
  - STRAY
  - TRIDENT
  - TROPICAL_FISH
  - TURTLE
  - VEX
  - VILLAGER
  - VINDICATOR
  - WITCH
  - WITHER
  - WITHER_SKELETON
  - WOLF
  - ZOMBIE
  - ZOMBIE_HORSE
  - ZOMBIE_VILLAGER
  allow-culling:
  - AREA_EFFECT_CLOUD
  - ARMOR_STAND
  - ARROW
  - BAT
  - BLAZE
  - BOAT
  - CAVE_SPIDER
  - CHICKEN
  - COD
  - COMPLEX_PART
  - COW
  - CREEPER
  - DOLPHIN
  - DONKEY
  - DRAGON_FIREBALL
  - DROPPED_ITEM
  - DROWNED
  - EGG
  - ELDER_GUARDIAN
  - ENDER_CRYSTAL
  - ENDER_DRAGON
  - ENDER_PEARL
  - ENDER_SIGNAL
  - ENDERMAN
  - ENDERMITE
  - EVOKER
  - EVOKER_FANGS
  - EXPERIENCE_ORB
  - FALLING_BLOCK
  - FIREBALL
  - FIREWORK
  - FISHING_HOOK
  - GHAST
  - GIANT
  - GUARDIAN
  - HORSE
  - HUSK
  - ILLUSIONER
  - IRON_GOLEM
  - ITEM_FRAME
  - LIGHTNING
  - LINGERING_POTION
  - LLAMA
  - LLAMA_SPIT
  - MAGMA_CUBE
  - MINECART
  - MINECART_CHEST
  - MINECART_COMMAND
  - MINECART_FURNACE
  - MINECART_HOPPER
  - MINECART_MOB_SPAWNER
  - MINECART_TNT
  - MULE
  - MUSHROOM_COW
  - OCELOT
  - PAINTING
  - PARROT
  - PHANTOM
  - PIG
  - PIG_ZOMBIE
  - POLAR_BEAR
  - PRIMED_TNT
  - PUFFERFISH
  - RABBIT
  - SALMON
  - SHEEP
  - SHULKER
  - SHULKER_BULLET
  - SILVERFISH
  - SKELETON
  - SKELETON_HORSE
  - SLIME
  - SMALL_FIREBALL
  - SNOWBALL
  - SNOWMAN
  - SPECTRAL_ARROW
  - SPIDER
  - SPLASH_POTION
  - SQUID
  - STRAY
  - THROWN_EXP_BOTTLE
  - TIPPED_ARROW
  - TRIDENT
  - TROPICAL_FISH
  - TURTLE
  - UNKNOWN
  - VEX
  - VILLAGER
  - VINDICATOR
  - WEATHER
  - WITCH
  - WITHER
  - WITHER_SKELETON
  - WITHER_SKULL
  - WOLF
  - ZOMBIE
  - ZOMBIE_HORSE
  - ZOMBIE_VILLAGER
  allow-purging:
  - AREA_EFFECT_CLOUD
  - ARMOR_STAND
  - ARROW
  - BAT
  - BLAZE
  - BOAT
  - CAVE_SPIDER
  - CHICKEN
  - COD
  - COW
  - CREEPER
  - DOLPHIN
  - DONKEY
  - DRAGON_FIREBALL
  - DROPPED_ITEM
  - DROWNED
  - EGG
  - ELDER_GUARDIAN
  - ENDER_CRYSTAL
  - ENDER_DRAGON
  - ENDER_PEARL
  - ENDER_SIGNAL
  - ENDERMAN
  - ENDERMITE
  - EVOKER
  - EVOKER_FANGS
  - FALLING_BLOCK
  - FIREBALL
  - FIREWORK
  - FISHING_HOOK
  - GHAST
  - GIANT
  - GUARDIAN
  - HORSE
  - HUSK
  - ILLUSIONER
  - IRON_GOLEM
  - LLAMA
  - LLAMA_SPIT
  - MAGMA_CUBE
  - MINECART
  - MINECART_CHEST
  - MINECART_COMMAND
  - MINECART_FURNACE
  - MINECART_HOPPER
  - MINECART_MOB_SPAWNER
  - MINECART_TNT
  - MULE
  - MUSHROOM_COW
  - OCELOT
  - PAINTING
  - PARROT
  - PHANTOM
  - PIG
  - PIG_ZOMBIE
  - POLAR_BEAR
  - PUFFERFISH
  - RABBIT
  - SALMON
  - SHEEP
  - SHULKER
  - SHULKER_BULLET
  - SILVERFISH
  - SKELETON
  - SKELETON_HORSE
  - SLIME
  - SMALL_FIREBALL
  - SNOWBALL
  - SNOWMAN
  - SPECTRAL_ARROW
  - SPIDER
  - SPLASH_POTION
  - SQUID
  - STRAY
  - THROWN_EXP_BOTTLE
  - TIPPED_ARROW
  - TRIDENT
  - TROPICAL_FISH
  - TURTLE
  - VEX
  - VILLAGER
  - VINDICATOR
  - WITCH
  - WITHER
  - WITHER_SKELETON
  - WITHER_SKULL
  - WOLF
  - ZOMBIE
  - ZOMBIE_HORSE
  - ZOMBIE_VILLAGER
rai:
  tps:

    # The server is considered lagging if the tick time exeeds this value
    high-tick: 50.0
```
