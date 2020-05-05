# Upgrading your operator

## How to release a newer version of your operator

Push the new operator image to the Connect portal, just like the original image.

Copy your existing metadata files, and edit them to reference the new version:

* Rename the CSV to have the new version number
* Put the new version number in the metadata.name
* Put the new version number in the spec.version
* Update any reference to your image with new tags
* Edit the package.yaml to refer to the new CSV version
* Add a spec.replaces field in the CSV naming the version this one replaces 
  * The spec.replaces field must match the exact name of the CSV, not just the version number

#### clusterserviceversion.yaml

```text
metadata:
  annotations:
    containerImage: quay.io/example-repo/example-operator:v0.0.2 ## Updated with new tag
  name: example-operator.v0.0.2  ## Updated to new version 
spec:
  replaces: example-operator.v0.0.1 ##This line is added
  version: 0.0.2  ## Updated to new version
  install:
    spec:
      deployments:      
      ...
              containers:
                image: quay.io/example-repo/example-operator:v0.0.2 ## Updated with new tag
```

#### package.yaml

```text
packageName: example-operator
channels:
  - name: alpha
    currentCSV: example-operator.v0.0.2   ## Updated to new version
```

Create an updated metadata.zip containing the updated files, **the old CSV,** and any CRDs. Upload this data to the Connect portal for scanning, just like the original metadata.

```text
metadata.zip/
├── example-operator.package.yaml
├── example-operator.v0.0.2.clusterserviceversion.yaml
├── example-operator.v0.0.1.clusterserviceversion.yaml
└── apm_v1alpha1_example_crd.yaml
```

After the metadata bundle passes, you can Publish your updated operator.



