# Verifying your Helm chart

Certification for Helm charts relies on the [`chart-verifier`](https://github.com/redhat-certification/chart-verifier) tool. This is an open source tool used to verify a Helm chart against Red Hat certification requirements and Red Hat recommendations.

{% hint style="info" %}
It is recommended to use this tool in your environment to locally test and validate your Charts. It will allow you to use this tool as needed during your chart development cycle, without the need to constantly submit the results to Red Hat.
{% endhint %}

You can then send the results for certification when your Chart is ready and it has passed the `chart-verifier` test.
