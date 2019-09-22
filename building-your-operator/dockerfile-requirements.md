# Dockerfile Requirements

For Step 1 Operator Image Dockerfile requirements are as follows: 

1. Base image must be based on a Red Hat product, e.g. Red Hat Enterprise Linux or Red Hat Universal Base Image. Any images using Ubuntu, Debian, CentOS, etc. as a base will not be certified.
2. You must configure the required labels \(name, maintainer, vendor, version, release, summary\)
3. Software [license\(s\)](https://choosealicense.com/) must be included within the image.

{% hint style="info" %}
Although typically labels and licenses are not required to successfully build a running container, they are required for the Red Hat build service and scanner.
{% endhint %}

Below is an example Dockerfile for a **Helm Operator** which includes the aforementioned requirements:

{% code-tabs %}
{% code-tabs-item title="Dockerfile" %}
```bash
FROM quay.io/operator-framework/helm-operator:v0.6.0

### Required OpenShift Labels
LABEL name="Memcached Operator" \
      vendor="Awesome Tech LLC" \
      version="v0.0.1" \
      release="1" \
      summary="This is an example operator." \
      description="This operator will deploy 3 instances of memcached to the cluster."

# Required Licenses
COPY licenses /licenses

COPY helm-charts/ ${HOME}/helm-charts/
COPY watches.yaml ${HOME}/watches.yaml
```
{% endcode-tabs-item %}
{% endcode-tabs %}

A few things to note about the Dockerfile above:

* This Dockerfile was created using the `operator-sdk new` command. That means that this was created via a scaffold. The container image `quay.io/operator-framework/helm-operator:v0.6.0` is the default image used for all Helm Operators as of SDK version 0.6.0 that will contain all dependencies. This image is also based on RHEL 7.6.
* This Dockerfile contains all of the required labels. These labels must be manually added \(name, vendor, version, release, summary, and description\). 
* Lastly, this Dockerfile also references a `licenses/` directory, which needs to be manually added to the **root** of the project. This directory must include the software license\(s\) of your project.

At the time of building your operator with `operator-sdk build <operator-name>:<version>` , your operator should build successfully and the image will be stored in your local Docker image cache, which will then be ready to be tagged and pushed to the Red Hat Container Scanner.

Your project directory structure should look similar to the hierarchy below. Note the location of the licenses directory.

{% code-tabs %}
{% code-tabs-item title="my-helm-memcached-operator" %}
```bash

my-helm-memcached-operator/
├── build
│   └── Dockerfile
├── deploy
│   ├── crds
│   │   ├── cache_v1alpha1_memcached_cr.yaml
│   │   └── cache_v1alpha1_memcached_crd.yaml
│   ├── operator.yaml
│   ├── role.yaml
│   ├── role_binding.yaml
│   └── service_account.yaml
├── helm-charts
│   └── memcached
│       ├── Chart.yaml
│       ├── charts
│       ├── templates
│       │   ├── NOTES.txt
│       │   ├── _helpers.tpl
│       │   ├── deployment.yaml
│       │   ├── ingress.yaml
│       │   ├── service.yaml
│       │   └── tests
│       │       └── test-connection.yaml
│       └── values.yaml
├── licenses
│   └── MIT.txt
└── watches.yaml
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Once your Operator project is ready, you can build your operator image by running this command:

```bash
$ operator-sdk build <operator-name>:<operator-version>
```

The `operator-sdk` knows that the Dockerfile resides within the `build/` directory, so you do not need to specify the location of the Dockerfile when building the image.

