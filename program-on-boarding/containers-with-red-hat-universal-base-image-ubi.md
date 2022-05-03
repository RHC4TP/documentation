# Containers and the Red Hat Universal Base Images (UBI)

Red Hat Universal Base Images (UBI) are OCI-compliant container base operating system images with complementary runtime languages and packages that are freely redistributable. Like previous base images, they are built from portions of Red Hat Enterprise Linux (RHEL). UBI images can be obtained from the [Red Hat container catalog](https://access.redhat.com/containers/#/product/5c180b28bed8bd75a2c29a63) and be built and deployed anywhere.

Red Hat Universal Base Images (UBI) provide the same quality trusted foundation for building container images as their non-UBI predecessors (`rhel6`, `rhel7`, `rhel-init`, and `rhel-minimal` base images), but offer more freedom in how they are used and distributed.

{% hint style="info" %}
See the [Containers and UBI Technical Track](https://redhat-connect.gitbook.io/red-hat-technical-tracks/universal-base-image) for more information
{% endhint %}

### **Expanded scope of Red Hat Container Certification**&#x20;

**‌**Red Hat Partner Connect program has expanded the scope of the Red Hat Container Certification to enable Red Hat technology partners to include Red Hat Enterprise Linux (RHEL) user space packages. This means that when partners build upon UBI base images, partners will be able to use any package from Red Hat Enterprise Linux user space required to run their software (except the kernel) and re-distribute these certified images through Red Hat or non-Red Hat container registries (e.g. Quay.io, Docker.io, a private registry, etc).

**Specific requirements that partners have to meet to take advantage of the expanded scope:**

* Partner container images must use RHEL7 UBI or RHEL8 UBI as base image.&#x20;
* Partners must accept the Red Hat Partner Connect agreement. There is no change to the current agreement, so if it is already signed there is no need to re-sign it.
* Partners must participate in Red Hat Container Certification:
  1. Accept the updated “Container Appendix” terms as part of the certification workflow. This updated Container Appendix grants use of all RHEL packages except the kernel, so long as the resulting work does not constitute a material reproduction of a commercial Red Hat product.
  2. Successfully complete the container certification.

{% hint style="danger" %}
As required by expanded scope of Container Certification we have updated Container Appendix on February 27th 2020. Container Appendix is presented during Container Certification workflow. If you have not yet re-accepted it please do so once. Once re-accepted you will not be prompted to accept it again.
{% endhint %}

#### **Recommended repository names for container images**

In alignment with Red Hat’s container repo policy it is recommended to explicitly indicate the RHEL version in repo names (like so: -ubi8, -rhel8). ****&#x20;

&#x20;**Repository name format:** \<Container Registry name>/Namespace/Repository

{% hint style="success" %}
_**Example:**_**   ** quay.io/MyCompany/MyProduct**-ubi8**
{% endhint %}

_**\*Note: I**f a container image is created with UBI7 or UBI8 base image and includes RHEL7 or RHEL8 packages (except kernel) please use suffix -**rhel7 or -rhel8.**_

It is recommended so users can clearly identify the operating system in the container image to understand support implications with respect to underlying RHEL host. It also helps prevent naming conflicts between images that need to be built and distributed for different versions of RHEL.\
****_**Note:**_ Red Hat Enterprise Linux Container Compatibility Matrix is outlined [here](https://access.redhat.com/support/policy/rhel-container-compatibility).\
****

#### **Building, running and managing containers with UBI**

Getting started with UBI is designed to be easy. Use [Podman](https://developers.redhat.com/blog/2018/08/29/intro-to-podman/) to pull an image from one of the following UBI repositories and go.

*   **For UBI 8:**

    podman pull registry.access.redhat.com/ubi8/ubi

    podman pull registry.access.redhat.com/ubi8/ubi-minimal

    podman pull registry.access.redhat.com/ubi8/ubi-init

If you need more information, refer to the full Universal Base Image Guide here**:**

* [**RHEL 8 How To**](https://access.redhat.com/documentation/en-us/red\_hat\_enterprise\_linux/8/html-single/building\_running\_and\_managing\_containers/index?lb\_target=stage#using\_red\_hat\_universal\_base\_images\_standard\_minimal\_and\_runtimes)

**Workflow for a Partner Product with existing Container Certification:**

* If you are NOT making a change to any of the items listed below, please continue to use your existing project to upload images for certification.&#x20;
* If you are planning to change any one or more of the items listed below, please un-publish your existing images and [Create a New Project](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/certify-your-application/creating-a-container-application-project) for certification.&#x20;

1. The container base image &#x20;
2. The distribution method &#x20;

**Workflow for a Partner Product with no existing Container Certification:**

* Create a Product Listing
* Create your certification project and certify your container

{% hint style="info" %}
If you wish to certify your product container image with UBI8 and UBI9 you would have created two projects, one for each base image version.
{% endhint %}
