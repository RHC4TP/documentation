# Verifying your Helm chart

Certification for Helm charts relies on the [`chart-verifier`](https://github.com/redhat-certification/chart-verifier) tool. This is an open source tool used to verify a Helm chart against Red Hat certification requirements and Red Hat recommendations.

{% hint style="info" %}
It is recommended to use this tool in your environment to locally test and validate your Charts. It will allow you to use this tool as needed during your chart development cycle, without the need to constantly submit the results to Red Hat.
{% endhint %}

{% hint style="info" %}
We **strongly** recommend to use the latest version of chart-verifier to certify your Helm chart.

For the Helm chart certification, a **N-2 lifecycle policy** is supported for the chart-verifier tool (Red Hat will support the three latest Major or Minor Releases (N, N-1, and N-2) of software)
{% endhint %}

You can then send the results for certification when your Chart is ready and it has passed the `chart-verifier` test.
