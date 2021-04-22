# Containers and the Red Hat Universal Base Images \(UBI\)

Red Hat Universal Base Images \(UBI\) are OCI-compliant container base operating system images with complementary runtime languages and packages that are freely redistributable. Like previous base images, they are built from portions of Red Hat Enterprise Linux \(RHEL\). UBI images can be obtained from the [Red Hat container catalog](https://access.redhat.com/containers/#/product/5c180b28bed8bd75a2c29a63) and be built and deployed anywhere.

Red Hat Universal Base Images \(UBI\)  provide the same quality trusted foundation for building container images as their non-UBI predecessors \(`rhel6`, `rhel7`, `rhel-init`, and `rhel-minimal` base images\), but offer more freedom in how they are used and distributed.

UBI FAQ's -including licensing information can be found [here](https://developers.redhat.com/articles/ubi-faq/?redirect_fragment=resources#error=login_required&state=e8bb7295-2fb7-40dc-8716-35b5a6324c22).

UBI: Images, repositories, and packages details can be found [here](https://access.redhat.com/articles/4238681).

### **NEW: Expanded scope of Red Hat Container Certification** 

**‌**Red Hat Partner Connect program has expanded the scope of the Red Hat Container Certification to enable Red Hat technology partners to include Red Hat Enterprise Linux \(RHEL\) user space packages. This means that when partners build upon UBI base images, partners will be able to use any package from Red Hat Enterprise Linux user space required to run their software \(except the kernel\) and  re-distribute these certified images through Red Hat or non-Red Hat container registries \(e.g. Quay.io, Docker.io, a private registry  etc\).

**Specific requirements that partners have to meet to take advantage of the expanded scope:**

1. * Partner container images must use RHEL7 UBI or RHEL8 UBI as base image. 
   * Partners must accept the Red Hat Partner Connect agreement. There is no change to the current agreement, so if it is already signed there is no need to re-sign it.
   * Partners must participate in Red Hat Container Certification:
     1. Accept the updated “Container Appendix” terms as part of the certification workflow. This updated Container Appendix grants use of all RHEL packages except the kernel, so long as the resulting work does not constitute a material reproduction of a commercial Red Hat product.
     2. Successfully complete the container certification.

{% hint style="danger" %}
As required by expanded scope of Container Certification we have updated Container Appendix on February 27th 2020. Container Appendix is presented during Container Certification workflow. If you have not yet re-accepted it please do so once. Once re-accepted you will not be prompted to accept it again.
{% endhint %}

#### **Distribution of certified container images**

Red Hat Container Certification program offers the following two options for the distribution of certified container images:

* **Red Hat Container Registry:**  Managed by Red Hat at no cost to partners.  This distribution option is available for container images whether you use UBI or  RHEL7 base image. This option requires compliance with U.S. export control laws. See details in our [Export compliance guide](https://redhat-connect.gitbook.io/red-hat-partner-connect-general-guide/initial-onboarding/export-compliance)
* **Non-Red Hat Container Registry:** In this option your can distribute through your organization’s own registry or use any public registry such as Quay.io registry, Docker.io registry etc. This option is only available for container images built with one of the [Universal Base images](https://access.redhat.com/articles/4238681) \(ubi, ubi-init, ubi-minimal\). 

#### **Recommended repository names for container images**

In alignment with Red Hat’s container repo policy it is recommended to explicitly indicate the RHEL version in repo names \(like so: -ubi7, -ubi8, rhel7, rhel8\).  ****

 **Repository name format: &lt;**Container Registry name&gt;/Namespace/Repository

{% hint style="success" %}
_**Example:**_   **** quay.io/MyCompany/MyProduct**-ubi7**
{% endhint %}

_**\*Note: I**f a container image is created with UBI7 or UBI8 base image and includes RHEL7 or RHEL8 packages \(except kernel\) please use suffix -**rhel7 or -rhel8.**_

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

* [**RHEL 8 How To**](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html-single/building_running_and_managing_containers/index#using_red_hat_universal_base_images_standard_minimal_and_runtimes)
* [**RHEL 7 How To**](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux_atomic_host/7/html-single/getting_started_with_containers/index#using_red_hat_universal_base_images_standard_minimal_and_runtimes)
* \*\*\*\*[**Adding RHEL packages to UBI**](https://app.gitbook.com/@redhat-connect/s/best-practices-guide/base-image) **\(**\*_Please scroll down_**\)**

**Dockerfile Requirements:**

You can use this[ link](https://github.com/RHC4TP/starter/tree/master/Container%20Zone) as a reference to how the Dockerfile needs to be configured to have your UBI based container image build and pass container certification successfully.

To begin the process of certifying a container image, please follow the workflow described below.

**Workflow for a Partner Product with existing Container Certification:**

* If you are NOT making a change to any of the items listed below, please continue to use your existing project to upload images for certification. 
* If you are planning to change any one or more of the items listed below, please un-publish your existing images and [Create a New Project](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/creating-a-container-application-project) for certification. 

1. The container base image  
2. The distribution method  

**Workflow for a Partner Product with no existing Container Certification:**

Follow existing Container Certification workflow starting with “[Add a Product](https://redhat-connect.gitbook.io/red-hat-partner-connect-general-guide/managing-your-account/product-listing)” section and then proceeding to “CERTIFY YOUR APPLICATION” section.

{% hint style="info" %}
If you wish to certify your product container image with UBI7 as well as UBI8 you would have created two projects, one for each base image version.
{% endhint %}

