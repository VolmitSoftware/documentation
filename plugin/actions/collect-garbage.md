# Collect Garbage

## Collect Garbage

The collect garbage action is a very simple action to force the JVM to perform a **full gc**.

{% hint style="warning" %}
If **-XX:+DisableExplicitGC** is set in your server launch arguments, this will have no effect.
{% endhint %}

{% hint style="danger" %}
This action can cause serious freezes and can even lock the server until it "stops responding". **Use this with extreme care.**
{% endhint %}

### Usage

```text
/re act collect-garbage
```

### Selector Usage

There are no selectors for this action

### Aliases

| Node |
| :--- |
| collect-garbage |
| gc |

