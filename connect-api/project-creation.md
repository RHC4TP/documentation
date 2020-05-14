---
description: >-
  This guide lists the steps needed to create Connect Projects using the Connect
  API.
---

# Project Creation

{% hint style="info" %}
Note: Official documentation for the Connect API can be found [here](https://connect.redhat.com/zones/containers/v2-api-docs-container-certification).
{% endhint %}

{% hint style="info" %}
Note: This guide does not apply to Marketplace Products created with the version 3 Connect API. Updates to this guide will be provided at a later time to document usage of the version 3 API.
{% endhint %}

## **Static Values**

The following static values should be used when creating Projects within the the OpenShift & Containers Zone:

```text
rh_product_id: 3602271
rh_product_version: 3602281
```

## Prerequisites

The following prerequisites steps and values must be completed and collected before creating Projects using the API.

### Existing Product and Project

First, using the [Connect GUI](https://connect.redhat.com), a Product must be created with a Project created within it. This is required to generate the API values that will be needed to create all future Projects nested under the existing Product using the API.

### Company ID

Collect the Company ID from the Connect GUI:

1. Login to [connect.redhat.com](https://connect.redhat.com)
2. Navigate to **My Company** &gt; **View company information**
3. Click **EDIT COMPANY PROFILE**

  
   Note the URL. It will be in the following format:

  
   https://connect.redhat.com/node/\#\#\#\#\#\#\#/edit



   The \#\#\#\#\#\#\# portion is the Company ID. Record this 7 digit integer.

### API Key

Generate an API key from the Connect GUI:

1. Navigate to **Product Certification** &gt; **Manage container API keys**
2. Click **Generate New Key**
3. Enter a Key Name
4. Click **Copy** to copy the API Key
5. Record this key

### Product ID

Collect the Product ID \(`product_id`\) from the Connect API:

1. Using the Company ID collected above, run the following, replacing COMPANY\_ID and API\_KEY with their respective values:

```text
$ curl -X GET "https://connect.redhat.com/api/v2/companies/COMPANY_ID" \
-H "accept: */*" \
-H "Authorization: Bearer API_KEY" \
-H 'Content-Type: application/json' \
-d "{}" | python -m json.tool
```

   2. An array of Products will be printed similar to the output below:

```text
"products": [
    "https://connect.redhat.com/api/v2/products/#######",
    "https://connect.redhat.com/api/v2/products/#######",
    "https://connect.redhat.com/api/v2/products/#######"
],
```

   The \#\#\#\#\#\#\# portion is the Product ID \(`product_id`\). Record this 7 digit integer.

   3. If the array contains multiple Products, and it is unclear which Product is desired, run the following     command against each Product to identify the desired Product:

```text
$ curl -X GET "https://connect.redhat.com/api/v2/products/PRODUCT_ID" \
-H "accept: */*" \
-H "Authorization: Bearer API_KEY" \
-H 'Content-Type: application/json' \
-d "{}" | python -m json.tool
```

   A title section will be printed similar to the output below:

```text
"title": "Product Title"
```

### Product Version

Collect the Product Version \(`pp_version`\) from the Connect API:

1. Using the Product ID collected above, run the following:

```text
$ curl -X GET "https://connect.redhat.com/api/v2/products/PRODUCT_ID" \
-H "accept: */*" \
-H "Authorization: Bearer API_KEY" \
-H 'Content-Type: application/json' \
-d "{}" | python -m json.tool
```

  An array of Product versions will be printed similar to the output below:

```text
"product_versions": {
    "#######": "1.0",
    "#######": "2.0"
},
```

 The \#\#\#\#\#\#\# portion is the Product Version \(`pp_version`\). Record the appropriate 7 digit integer.

## Project Creation

Perform the following steps to create a Project using the Connect API:

1. Ensure that the following values have been collected from the Prerequisites and Static Values sections above:  
  
   `rh_product_id`

   `rh_product_version`

   `product_id`

   `pp_version`  

2. Note the following option choices and values:  
  
   OS Content Type \(`os_content_type`\):  
    - RHEL - `Red Hat Enterprise Linux`

    - UBI - `Red Hat Universal Base Image (UBI)`



   Distribution Method \(`distribution_method`\):

    - Red Hat Container Catalog - `rhcc`

    - Red Hat Marketplace Only - `marketplace_only`

    - External Registry - `external`

    - Non-Registry - `non_registry`



   Registry Vendor \(`registry_vendor`\):

    - Red Hat Container Catalog - `""`\(empty string\)

    - External Registry - `Own` OR `Docker` OR `Quay.io`

3. Run the following command to create a new Project, replacing API\_KEY, PROJECT\_NAME, PRODUCT\_ID, PRODUCT\_VERSION, and REPO\_NAMESPACE with their respective values:  Note: This example creates a UBI container Project using an external registry.

```text
$ curl -X POST "https://connect.redhat.com/api/v2/projects" \
-H "accept: */*" \
-H "Authorization: Bearer API_KEY" \
-H "Content-Type: application/json" \
-d "{\"zone\":\"containers\",\"project_name\":\"PROJECT_NAME\",\"product_id\":PRODUCT_ID,\"pp_version\":PRODUCT_VERSION,\"project_type\":\"Container Application\",\"rel_cat\":\"generally_available\",\"rh_product_id\":3602271,\"rh_product_version\":3602281,\"os_content_type\":\"Red Hat Universal Base Image (UBI)\",\"registry_vendor\":\"Own\",\"registry_override_instruct\":\"Registry usage instructions here.\",\"repo\":\"REPO_NAMESPACE\",\"repo_desc\":\"Description of repo.\",\"repo_path\":\"registry.example.com:5000/path/to/repository\",\"support_platforms\":[\"OpenShift Container Platform\"],\"distribution_method\":\"external\"}"
```

        Example successful output:

```text
"status":"Ok","message":"Project created.","code":200,"data":{"rid":"4209251","pid":"ospid-3b0fedb9-c611-4a70-bf1e-b2a6323dd00e","api":"https://connect.redhat.com/api/v2/projects/ospid-3b0fedb9-c611-4a70-bf1e-b2a6323dd00e"}}
```

    4. Verify the new project exists:

```text
$ curl -X GET "https://connect.redhat.com/api/v2/projects/PROJECT_ID" \
-H "accept: */*" \
-H  "Authorization: Bearer API_KEY"
```

