---
description: A quick tutorial on how to begin using the API
---

# Getting Started with API

## Importing the API

Start by determining how you would like to include the API in your project.

{% tabs %}
{% tab title="Maven" %}
In your `pom.xml` file, add the following lines to add the Volmit repository:

```markup
<repository>
    <id>volmit</id>
    <url>http://repo.volmit.com/repository/volmit/</url>
</repository>
```

After you’ve added the repository, you’ll have to add VehiclesPlus as a dependency:

```markup
<dependency>
  <groupId>me.legofreak107.vehiclesplus</groupId>
  <artifactId>VehiclesPlus-Pro-API</artifactId>
  <version>2.2.5</version>
</dependency>
```
{% endtab %}

{% tab title="Gradle" %}
In your `build.gradle` file, add the following lines to add the Volmit repository:

```groovy
repositories {
	maven { url 'http://repo.volmit.com/repository/volmit/' }
}
```

After you’ve added the repository, you’ll have to add VehiclesPlus as a dependency:

```groovy
dependencies {
    compileOnly "me.legofreak107.vehiclesplus:VehiclesPlus-Pro-API:2.2.5"
}
```
{% endtab %}
{% endtabs %}

## plugin.yml Dependency

To make sure that your plugin recognizes VehiclesPlus as a dependency, add the following line to your `plugin.yml`:

```yaml
depend: VehiclesPlus
```

Now you’re all set! Continue to the next page to learn more.

