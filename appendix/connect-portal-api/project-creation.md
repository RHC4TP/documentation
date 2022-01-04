---
description: >-
  This guide lists the steps needed to create Connect Projects using the Connect
  API v2.
---

# Project Creation

## **Static Values**

The following static values should be used when creating Projects within the the OpenShift & Containers Zone:

```
rh_product_id: 3602271
rh_product_version: 3602281
```

## Prerequisites

The following prerequisites steps and values must be completed and collected before creating Projects using the API.

### Existing Product

First, using the [Connect](https://connect.redhat.com) web interface, a Product must be created. This is required so that Projects created later can be attached to a parent Product.

#### Create Product

1. Navigate to **Product Certification** > **Manage products** > **Create Listing**
2. Enter **Product name and major version**
3. Select **OpenShift Operator or Containerized Product**
4. Click **Create listing**

### Company ID

Collect the Company ID from the [Connect](https://connect.redhat.com) web interface:

1. Navigate to **My Company** > **View company information**
2. Click **EDIT COMPANY PROFILE**
3.  Note the URL. It will be in the following format:

    \
    `https://connect.redhat.com/node/#######/edit`



    The `#######` portion is the Company ID. Record this 7 digit integer.

### API Key

Generate an API key from the [Connect](https://connect.redhat.com) web interface:

1. Navigate to **Product Certification** > **Manage container API keys**
2. Click **Generate New Key**
3. Enter a Key Name
4. Click **Copy** to copy the API Key
5. Record this key

## Project Creation

Perform the following steps to create a Project using the Connect API:

1.  Ensure that the following values have been collected from the Prerequisites and Static Values sections above:\
    \
    `rh_product_id`

    `rh_product_version`

    `company_id`\

2.  Note the following option choices and values:\
    \
    OS Content Type (`os_content_type`):\
    &#x20;\- RHEL - `Red Hat Enterprise Linux`

    &#x20;\- UBI - `Red Hat Universal Base Image (UBI)`



    Distribution Method (`distribution_method`):

    &#x20;\- Red Hat Container Catalog - `rhcc`

    &#x20;\- Red Hat Marketplace Only - `marketplace_only`

    &#x20;\- External Registry - `external`

    &#x20;\- Non-Registry - `non_registry`



    Registry Vendor (`registry_vendor`):

    &#x20;\- Red Hat Container Catalog - `""`(empty string)

    &#x20;\- External Registry - `Own` OR `Docker` OR `Quay.io`


3. Run the following command to create a new Project, replacing API\_KEY, PROJECT\_NAME, COMPANY\_ID, and REPO\_NAMESPACE with their respective values:\
   \
   Note: This example creates a UBI container Project using an external registry.

```
$ curl -X POST "https://connect.redhat.com/api/v2/projects" \
-H "accept: */*" \
-H "Authorization: Bearer API_KEY" \
-H "Content-Type: application/json" \
-d "{\"zone\":\"containers\",\"project_name\":\"PROJECT_NAME\",\"company_id\":COMPANY_ID,\"project_type\":\"Container Application\",\"rel_cat\":\"generally_available\",\"rh_product_id\":3602271,\"rh_product_version\":3602281,\"os_content_type\":\"Red Hat Universal Base Image (UBI)\",\"registry_vendor\":\"Own\",\"registry_override_instruct\":\"Registry usage instructions here.\",\"repo\":\"REPO_NAMESPACE\",\"repo_desc\":\"Description of repo.\",\"repo_path\":\"registry.example.com:5000/path/to/repository\",\"support_platforms\":[\"OpenShift Container Platform\"],\"distribution_method\":\"external\"}"
```

&#x20;       Example successful output:

```
"status":"Ok","message":"Project created.","code":200,"data":{"rid":"4209251","pid":"ospid-3b0fedb9-c611-4a70-bf1e-b2a6323dd00e","api":"https://connect.redhat.com/api/v2/projects/ospid-3b0fedb9-c611-4a70-bf1e-b2a6323dd00e"}}
```

&#x20;   4\. Verify the new project exists:

```
$ curl -X GET "https://connect.redhat.com/api/v2/projects/PROJECT_ID" \
-H "accept: */*" \
-H  "Authorization: Bearer API_KEY"
```

&#x20;   5\. Attach the Project to the Product:

&#x20;       1\. Navigate to Partner Connect using a web browser\
&#x20;       2\. Select **Product Certification** > **Manage products**\
&#x20;       ****        3. Select the Product\
&#x20;       4\. Click **Certification Projects** on the left side\
&#x20;       5\. Click the appropriate **Attach Project** button (note Project type created above)\
&#x20;       6\. Select the new Project\
&#x20;       7\. Click **Attach**

