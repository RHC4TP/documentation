# Running the Helm Chart verification tool

In order to run the test, your chart structure should look like this :

```
.
└── src
    ├── Chart.yaml
    ├── README.md
    ├── templates
    │   ├── deployment.yaml
    │   ├── _helpers.tpl
    │   ├── hpa.yaml
    │   ├── ingress.yaml
    │   ├── NOTES.txt
    │   ├── serviceaccount.yaml
    │   ├── service.yaml
    │   └── tests
    │       └── test-connection.yaml
    ├── values.schema.json
    └── values.yaml

```

Before running the `chart-verifier`, you will need to package your Helm chart with the following command:&#x20;

```
helm package <helmchart folder>
```

This will archive the Helm chart into a **.tgz** file



To run the full set of `chart-verifier` tests you will have 2 options:&#x20;

* Run it through the **podman/docker** command&#x20;
* Run the binary (Linux only)

**I - Using Podman/Docker:**

1. Run `podman run --rm quay.io/redhat-certification/chart-verifier verify <chart URI>`
2. The `chart-uri` is the location of the chart archive (**path to a local directory** or **http(s) URI**). The archive should be in **.tgz** format

**II - Using the binary file:**

1. Download and install the [chart-verifier](https://github.com/redhat-certification/chart-verifier/releases) on your server
2. Run the following command : `$ ./chart-verifier verify <chart-uri>`
3. The `chart-uri` is the location of the chart archive on your server. The archive should be in **.tgz** format

**III - Using Github Action**

_More information to come soon_

The output of `chart-verifier` includes the tests executed and a **PASS/FAIL** result for each test. It will also indicate whether each test is mandatory or recommended for certification.

{% hint style="info" %}
For more details and updates about the `chart-verifier` tool, please visit the Github [documentation](https://github.com/redhat-certification/chart-verifier/blob/main/docs/helm-chart-checks.md)
{% endhint %}
