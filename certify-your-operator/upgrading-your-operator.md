# Upgrading your Operator

To create a new update for your operator, you'll need to create a new version directory, and place your crds and csv inside. You can make any updates to these files as normal.&#x20;

{% hint style="warning" %}
You must always bump the version number whenever re-certifying your Operator bundle.
{% endhint %}

```
$ mkdir bundle/3.0.0
$ cp <latest csv> bundle/3.0.0
$ cp <crd> bundle/3.0.0
```

Here's an example what the structure should look like when you're done:

![](../.gitbook/assets/metatdat.png)

{% hint style="warning" %}
Don't forget to update your package yaml, too! It's not in one of the version sub-directories because the package determines which operator version is used.
{% endhint %}

Move into the bundle directory. You can now use opm to create the annotations.yaml.

```
$ cd bundle
$ opm alpha bundle generate -d ./3.0.0/ -u ./3.0.0/
```

