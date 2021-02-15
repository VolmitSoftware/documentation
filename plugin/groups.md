---
description: >-
  Gloss Groups allow you to group players by their permission group. You can
  then configure group specific features through gloss
---

# Groups

## Groups Folder

The groups folder is located in Gloss's data folder \(Gloss/groups\). In this folder, by default, it will contain a help.txt file explaining different parameters you can use.

### Creating a custom group

Simply duplicate either the \_op.yml or member.yml and rename it to your permission group name you wish to add to.

```text
# Modifies the player's tablist name
# I.e. &7cyberpwn
tablist-name: '&7$player'

# Show a specific board for this group upon login
default-board: member-board
```

Simply save the file and use /gloss reload.

{% hint style="warning" %}
The \_op.yml file is formatting and board information for ops since they may or may not have a default group.
{% endhint %}

{% hint style="info" %}
If you do not wish to use a group specific default board, simply set it to a board name that doesn't exist such as "none".
{% endhint %}

