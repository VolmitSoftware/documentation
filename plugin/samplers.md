---
description: >-
  Samplers are very powerful. They can tell you realtime, tons of about your
  server.
---

# Samplers

## Samplers

{% tabs %}
{% tab title="Tick & Process" %}
| ID | Description | Example |
| :--- | :--- | :--- |
| TPS | Ticks per second | 20 |
| TICK | Tick time \(ms\) | 14ms |
| CPU | CPU Process Usage | 38% |
| TIU | Tick utilization | 26% |
| REACT\_TIME | React tick time | 1ms |
| REACT\_TASK\_TIME | React task count | 24 |
{% endtab %}

{% tab title="Memory" %}
| ID | Description | Example |
| :--- | :--- | :--- |
| MEM | Memory used | 943m |
| FREEMEM | Free memory | 3.1g |
| MAXMEM | Maximum memory | 4g |
| ALLOCMEM | Allocated Memory | 1.2g |
| MAHS | Memory allocated per second | 34mb/s |
| MEMTOTALS | Samples memory total | 5g |
{% endtab %}

{% tab title="World" %}
| ID | Description | Example |
| :--- | :--- | :--- |
| CHK\_TIME | Chunk tick time | 2ms |
| EXPLOSION\_TIME | Explosion tick time | 5ms |
| GROWTH\_TIME | Growth tick time | 3ms |
| CHK | Total loaded chunks | 928 |
| CHKS | Chunks loaded per second | 31/s |
{% endtab %}

{% tab title="Entities" %}
| ID | Description | Example |
| :--- | :--- | :--- |
| PLAYERCOUNT | The player count | 14 |
| ENT | Entity count total | 302 |
| ENTLIV | Living entity count \(mobs\) | 194 |
| ENTDROP | Drop count | 36 |
| ENTTILE | Tile entity count | 79 |
| ENTITY\_DROPTICK | Entity droptick | 7.5 |
| TILE\_DROPTICK | Tile droptick | 2.3 |
| TILE\_TIME | Tile tick time | 12ms |
| ENTITY\_TIME | Entity tick time | 7ms |
| TILE\_TIME\_LOCK | Tile time lock | 20ms |
| ENTITY\_TIME\_LOCK | Entity time lock | 10ms |
{% endtab %}

{% tab title="Physics" %}
| ID | Description | Example |
| :--- | :--- | :--- |
| REDSTONE\_TICK\_USAGE | Redstone tick usage | 3% |
| REDSTONE\_TICK | Redstone per tick | 4/t |
| REDSTONE\_SECOND | Redstone per second | 28/s |
| REDSTONE\_TIME | Redstone tick time | 2ms |
| PHYSICS\_TIME | Physics tick time  | 7ms |
| HOPPER\_TICK\_USAGE | Hopper tick usage | 8% |
| HOPPER\_TICK | Hopper per tick | 7/t |
| HOPPER\_SECOND | Hopper per second | 43/s |
| HOPPER\_TIME | Hopper tick time | 9ms |
| FLUID\_TICK\_USAGE | Fluid tick usage | 4% |
| FLUID\_TICK | Fluid flows per tick | 4/t |
| FLUID\_SECOND | Fluid flows per second | 54/s |
| FLUID\_TIME | Fluid tick time | 3ms |
{% endtab %}
{% endtabs %}



