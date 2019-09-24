# Containers and the Red Hat Universal Base Image \(UBI\)

The Red Hat Universal Base Image \(UBI\) is a set of packages built on the same trusted foundation as Red Hat Enterprise Linux \(RHEL\).

The packages included with UBI are released, maintained and updated by Red Hat in alignment with the RHEL life cycle.

Learn more about the Red Hat Universal Base Image [here](https://connect.redhat.com/explore/red-hat-container-certification).

UBI FAQ's -including licensing information can be found [here](https://developers.redhat.com/articles/ubi-faq/?redirect_fragment=resources#error=login_required&state=e8bb7295-2fb7-40dc-8716-35b5a6324c22).

#### **Distribution of certified container images**

Red Hat Container Certification program offers  following two options for the distribution of certified, UBI content based, container images:

* **Red Hat Container Registry:**  Managed by Red Hat at no cost to partners.  This distribution option is available for container images whether you use UBI content or the broader RHEL content. This option requires compliance with U.S. export control laws. 

 \*View our [Export Compliance Guide](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/initial-on-boarding/export-compliance). 

* **External Registry:** In this option your can distribute through your organization’s own registry or use any public registry such as Quay.io registry, Docker registry etc. This option is only available for container images built with [UBI content](https://access.redhat.com/articles/4238681). 

#### **Recommended repository names for container images**

In alignment with Red Hat’s container repo policy it is recommended to explicitly indicate the RHEL version in repo names \(like so: -ubi7, -ubi8, rhel7, rhel8\). 

* **Certified partner images with “UBI” only content :** Eligible for distribution through External Registries      **Example:**   Namespace/Repository      MyCompany/MyProduct**-ubi7**
* **Certified partner images with RHEL content :** Only available through registry.connect.redhat.com       **Example:**   Namespace/Repository      MyCompany/MyProduct**-rhel7**

It is recommended so users can clearly identify the operating system in the container image to understand support implications with respect to underlying RHEL host. It also helps prevent naming conflicts between images that need to be built and distributed for different versions of RHEL.  
****_**Note:**_ Red Hat Enterprise Linux Container Compatibility Matrix is outlined [here](https://access.redhat.com/support/policy/rhel-container-compatibility).  
****

#### **Building, running and managing containers with UBI**

Getting started with UBI is designed to be easy. Use [Podman](https://developers.redhat.com/blog/2018/08/29/intro-to-podman/) to pull an image from one of the following UBI repositories and go.

* **For UBI 8:**

  podman pull registry.access.redhat.com/ubi8/ubi

  podman pull registry.access.redhat.com/ubi8/ubi-minimal

  podman pull registry.access.redhat.com/ubi8/ubi-init

* **For UBI 7:**

  podman pull registry.access.redhat.com/ubi7/ubi

  podman pull registry.access.redhat.com/ubi7/ubi-minimal

  podman pull registry.access.redhat.com/ubi7/ubi-init

If you need more information, refer to the full Universal Base Image Guide here**:**

* [**RHEL 8 How To**](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html-single/building_running_and_managing_containers/index?lb_target=stage#using_red_hat_universal_base_images_standard_minimal_and_runtimes)
* [**RHEL 7 How To**](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux_atomic_host/7/html-single/getting_started_with_containers/index#using_red_hat_universal_base_images_standard_minimal_and_runtimes)

**Dockerfile Requirements:**

You can use this[ link](https://github.com/RHC4TP/starter/tree/master/Container%20Zone) as a reference to the Dockerfile needs to be configured to have your UBI based container image build and pass container certification successfully.

To begin the process of certifying a container image, please follow the workflow described below.

**Workflow for a Partner Product with existing RHEL7 Container Certification:**

Certify Product Container image with RHEL 7 UBI

1. Upload the UBI 7 container image to existing project as outlined in  “[Image Upload](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/image-upload)” section of this guide.
2. Follow existing Container Certification workflow as of “[Image Scan and Verification](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/image-scan-and-verification#image-scan)” section of this guide.

Certify Product Container image with RHEL 7 UBI and distribute through External Registry

1. Create a New Container Project, for the same product, as outlined in “[Create a Container Project](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/create-a-container-project)” section of this guide.
2. Follow existing Container Certification workflow as of “[The Certification Checklist](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/the-certification-checklist)” section of this guide.
3. Upload the UBI 7 container image to this new project in “[Image Upload](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/image-upload)” step and continue with the existing Container Certification workflow.

Certify Product Container image with RHEL 8 UBI

1. Create a New Container Project, for the same product, as outlined in “[Create a Container Project](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/create-a-container-project)” section of this guide.
2. Follow existing Container Certification workflow as of “[The Certification Checklist](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/the-certification-checklist)” section of this guide.
3. Upload the UBI 8 container image to this new project in “[Image Upload](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/image-upload)” step and continue with the existing Container Certification workflow.

**Workflow for a Partner Product with no existing Container Certification:**

Follow existing Container Certification workflow starting with “[Add a Product](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/program-on-boarding/add-a-product)” section and then proceeding to “CERTIFY YOUR APPLICATION” section.

{% hint style="info" %}
If you wish to certify your product container image with RHEL 7 UBI as well as RHEL 8 UBI you would have created two projects, one for each base image version.
{% endhint %}

