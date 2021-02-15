# Timings

## Timings

The timings action simply allows you to run the server's timings, but with additional help to run it for a specified amount of time instead of having to manually stop it yourself.

{% hint style="warning" %}
Later versions of Paperspigot force you to pull timings reports which are longer than 3.5 minutes roughly. Ensure you set the action time selector to a time value your server flavor supports.
{% endhint %}

### Usage

```text
/re act timings 
```

### Selector Usage

{% tabs %}
{% tab title="Time" %}
You can use a time selector to specify how long to pull a timings report for \(when to stop it and output the report\)

```text
/re act timings @t:5m
```

{% hint style="success" %}
The default time for this selector is **@t:3s**
{% endhint %}
{% endtab %}
{% endtabs %}

### Aliases

| Node |
| :--- |
| timings |
| time |
| times |
| tr |

