---
description: >-
  Emojis arent just for Emotes, you can use them as "variables" across your
  server so that when you change the text of the emoji, it updates everywhere
  such as your server name
---

# Emojis

## Using Emojis

Gloss comes pre-configured with 67 emojis for typical use. However, all emojis can be modified and you can even add your own!

### Emojis in-game

Any emoji can be used using `:emoji:` . Just like in discord. However some emojis such as `:heart:` will also replace `<3` For example.

{% hint style="info" %}
You can tab-complete emojis. For example typing in `:air` and hitting tab will tab-complete to the airplane emoji.
{% endhint %}

You can list emojis ingame via `/gloss emoji` 

## Creating Emojis

You can easily create emojis. Here is an example emoji 

```javascript
{
    "emoji": "U+2702;",
    "trigger": "<uses :id:>",
    "enabled": true
}
```

{% hint style="info" %}
For the trigger, specifying `<uses :id:>` tells gloss that only `:<emoji>:` will trigger the emoji. You can change the trigger to replace text into an emoji such as `<3`.
{% endhint %}

### UTF-8 Icons

Utf formatting in minecraft can be weird at times simply because of file formats and methods of reading. To solve this, gloss has a text filter for UTF-8 to replace them. `U+<code>;` .

For example, if we look at the heart utf-8 symbol on utf8icons [https://www.utf8icons.com/character/10084/heavy-black-heart](https://www.utf8icons.com/character/10084/heavy-black-heart). You will see the "Unicode Hex" on the sidebar as `U+2764` To use this in gloss simply add a semicolon `U+2764;` and that represents a heart in gloss!

### Using Emojis as text variables

You can save a lot of time if you place your server name in all your holograms or on your boards. Simply make an emoji named `server.json` in the emojis folder.

```javascript
{
    "emoji": "&l&dShadow&l&8Realms",
    "trigger": "<uses :id:>",
    "enabled": true
}
```

This will now replace any occurrence of `:server:` to `&l&dShadow&l&8Realms` in chat, holograms, scoreboards, and tablists. You can now edit the emoji and all sources using the emoji will update too!

