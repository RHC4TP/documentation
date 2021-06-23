---
description: >-
  There are two ways to submit images to be published in the hosted registry
  service.  Below you will find both examples.
---

# Scanning Images to be published in registry.connect.redhat.com



{% hint style="info" %}
Make sure to take a look at the [Technical Prerequisites](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/program-on-boarding/technical-prerequisites) section to validate that your Dockerfile will pass our certification scan.
{% endhint %}

## The Build Service <a id="the-build-service"></a>

The Automated Image Build Service automates the rebuilding of your image whenever an updated Red Hat package is available. It also scans your image \(after a successful build\) for any security vulnerabilities that may be present prior to publishing your image to the Container Catalog. The build service clones your Github/Gitlab repository onto a build server, and uses the Dockerfile to build your image. It is a requirement from Red Hat to properly maintain your image by keeping up to date with the latest security updates. By not using the automated build service, you are opting into manually maintaining and rebuilding your image every time an update is released.‌

### **Configuration** <a id="configuration"></a>

Configuration is very easy and straightforward. Follow the steps below:‌

In the Project Page you created, click on the **Builds** tab:

![Container Project Main Page](../.gitbook/assets/screen-shot-2021-05-25-at-9.33.34-am%20%281%29.png)

Click on the **Configure Build Service** tab.‌

![](../.gitbook/assets/screen-shot-2021-05-25-at-9.39.20-am.png)

Fill in the Git source and the Dockerfile name if it has a name other than “Dockerfile”.‌

If your repository is public, then all that is needed is the Git source URL \(HTTPS link\). If your repository is private, then you must configure the build service with the SSH link and a private SSH key. The git repository needs the public SSH key associated with the private key in order to successfully clone. It is recommended to create a new public and private SSH key just for the project. Never use your own personal private key.

SSH key files must be stored in the PEM format, using the RSA algorithm. When configuring the build service, make sure to include the “-----BEGIN RSA PRIVATE KEY-----” and “-----END RSA PRIVATE KEY-----” blocks surrounding your private SSH key.‌

![](../.gitbook/assets/screen-shot-2021-05-25-at-9.42.20-am.png)

Click **Submit** at the end of the page.‌

Click **Start New Build** button at the top of the page.‌

![](../.gitbook/assets/buildservicebluebutton-operator.png)

Enter a tag number in the field provided

### Image Tagging <a id="configuration"></a>

Tag version numbers follow the convention of using a dash "-" and then a number in order to accommodate Red Hat package updates that are independent of the partner application.

For example, if the initial image published is 1.0-1, the partner version is the 1.0 and the Red Hat build is -1. 

If for some reason there is a security vulnerability or other Red Hat package update for that image, the Build Service will rebuild the image with a 1.0-2 tag to indicate a second Red Hat build of the same partner software version. 

![](https://lh6.googleusercontent.com/Y3mgzPLQ_EhPcEKMchL7pwpPWPKJNjkxUZppfAoF1h3FBEo43k6kcNi-JxnUyt1ym1Fk6gY04ysKQsqkYHfvcvCBgstksRswiMxVuqRrKNGdeGf9rtb6jRyiOx--XY11fHqLMo9e)

Once submitted, the new build will be added and scanned.

![](https://lh6.googleusercontent.com/NInim3G8rF-DO8Xvg19sh5lR-3yO6nxs_I0LW1dH_bU4emFJx3VCspMy0Ioxjv7Rl0kCkLTtJ58luVR_xk3DlE-3ObkPnFEq8lpQHN7_rNquFc8mhSSCfxHHoR8mwd9H_IL7Pen7)

The Build Service must first be completed before it can begin the scanning process for certification. If your Build Service fails or does not complete, make sure the details you entered under the Configure Build Service tab is correct and confirm that your Dockerfile conforms to the examples provided in this link.‌

## Manually Upload Your Image <a id="manually-upload-your-image"></a>

If you are not using the Build Service, you will need to manually upload your image. Navigate back to your project overview landing page, and select the **Images** tab. Click on the **Push Image Manually** link**.**

![](../.gitbook/assets/screen-shot-2021-05-25-at-9.46.15-am.png)

Cut and paste the following line to your terminal.

```text
# podman login -u unused scan.connect.redhat.com
```

When prompted for the password copy and paste the Registry Key located on the Upload Your Image tab in the project.

{% hint style="warning" %}
This Registry Key is unique per project, please make sure you are using the correct password for the project you are working on.
{% endhint %}

![](../.gitbook/assets/screen-shot-2021-05-25-at-9.47.22-am-1.png)



{% hint style="danger" %}
If you do not have a registry key populated or are having issues pushing your image please open a Support Ticket. Instructions on how to open a Support Ticket can be found in the [Getting Help](https://redhat-connect.gitbook.io/red-hat-partner-connect-general-guide/managing-your-account/getting-help/support-ticket) Section.
{% endhint %}

