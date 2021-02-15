---
description: Need to translate the plugin into your own language? Here’s how.
---

# Custom Locale Files

## Understanding Locale Files

Within a locale file, you are able to change the messages that are sent by VehiclesPlus. Every message sent by VehiclesPlus is completely customizable.

## Creating a Locale File

1. Begin by making a copy of the `lang_en.yml` file, located under `plugins/VehiclesPlus/locale`. This is the default English locale file. 
2. Rename the file to match the language that you are translating. For example, Spanish would be `lang_es.yml`. To view a list of standard 2 letter language names, click [here](https://www.sitepoint.com/iso-2-letter-language-codes/). You do not necessarily have to match these names, but it is recommended.
3. Once renamed, open the file and begin editing the messages. Once you are satisfied, save the file.
4. Open your `config.yml` file. Find the line that says `locale: en` and edit it to match the name of your locale file. For example, if I had created `lang_es.yml`, I would change the line to `locale: es`.
5. Save your `config.yml` and restart the server.

{% hint style="info" %}
Do not include the `lang`\_ prefix or `.yml` ending on the `locale: en` line in your configuration.
{% endhint %}

