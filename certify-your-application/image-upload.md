---
description: There are two ways to Upload your Image. Below you will find both examples.
---

# Image Upload

## Dockerfile Requirements <a id="dockerfile-requirements"></a>

The following [GitHub repo](https://github.com/RHC4TP/starter/tree/master/Container%20Zone) contains a few different Dockerfile examples that pass the container image scan, as they all align with the following requirements:

1. The Base image must be \(or must be based on\) a supported Red Hat image, such as Red Hat Enterprise Linux or Red Hat Universal Base Image. Any third party or community supported images such as Ubuntu, Debian, Alpine, CentOS etc are not supported by Red Hat and cannot be certified.
2. The following labels must exist: **name**, **maintainer**, **vendor**, **version**, **release,** **summary & description.**
3. Any [software license\(s\)](https://choosealicense.com/) must be placed in a `/licenses/` directory at the root of the image.

**Although labels and licenses are not required to successfully build a running container, they are required for the Red Hat build service and scanner.**‌

## The Build Service <a id="the-build-service"></a>

‌

The Automated Image Build Service automates the rebuilding of your image whenever an updated Red Hat package is available. It also scans your image \(after a successful build\) for any security vulnerabilities that may be present prior to publishing your image to the Container Catalog. The build service clones your Github/Gitlab repository onto a build server, and uses the Dockerfile to build your image. It is a requirement from Red Hat to properly maintain your image by keeping up to date with the latest security updates. By not using the automated build service, you are opting into manually maintaining and rebuilding your image every time an update is released.‌

### **Configuration** <a id="configuration"></a>

‌

Configuration is very easy and straightforward. Follow the steps below:‌

In the Project Page you created you will notice a left hand box, click on **Build Service**:‌

![](../.gitbook/assets/containerzone3.png)

Click on the **Configure Build Service** tab.‌

![](../.gitbook/assets/buildservicetab.png)

Fill in the git repo and the Dockerfile name if it has a name other than “Dockerfile”.‌

If your repository is public, then all that is needed is the git source URL \(HTTPS link\). If your repository is private, then you must configure the build service with the SSH link and a private SSH key. The git repository needs the public SSH key associated with the private key in order to successfully clone. It is recommended to create a new public and private SSH key just for the project. Never use your own personal private key.

SSH key files must be stored in the PEM format, using the RSA algorithm. When configuring the build service, make sure to include the “-----BEGIN RSA PRIVATE KEY-----” and “-----END RSA PRIVATE KEY-----” blocks surrounding your private SSH key.‌

![](https://lh6.googleusercontent.com/PH-MUlLOpvtVmfTwBs938xJFRsJEJCa3VULuVBnGo1f7j7kJCx-6xnyjv_2PjUmVova08PFa_uU37j7xzeV50FHU5ZAAhoDKgPMVrAgFH0-87XwDD_zGsx67cWOzm1zDz29oJt_o)

Click **Submit** at the end of the page.‌

Click **Start New Build** button at the top of the page.‌

![](../.gitbook/assets/buildservicebluebutton-operator.png)

Enter a tag number \(the version number of the plugin\) and click **SUBMIT**.‌

![](https://lh6.googleusercontent.com/Y3mgzPLQ_EhPcEKMchL7pwpPWPKJNjkxUZppfAoF1h3FBEo43k6kcNi-JxnUyt1ym1Fk6gY04ysKQsqkYHfvcvCBgstksRswiMxVuqRrKNGdeGf9rtb6jRyiOx--XY11fHqLMo9e)

Once submitted, the new build will be added and scanned.

![](https://lh6.googleusercontent.com/NInim3G8rF-DO8Xvg19sh5lR-3yO6nxs_I0LW1dH_bU4emFJx3VCspMy0Ioxjv7Rl0kCkLTtJ58luVR_xk3DlE-3ObkPnFEq8lpQHN7_rNquFc8mhSSCfxHHoR8mwd9H_IL7Pen7)

The Build Service must first be completed before it can begin the scanning process for certification. If your Build Service fails or does not complete, make sure the details you entered under the Configure Build Service tab is correct and confirm that your Dockerfile conforms to the examples provided in this link.‌

## Manually Upload Your Image <a id="manually-upload-your-image"></a>

If you are not using the Build Service, you will need to manually upload your image from the **UPLOAD YOUR IMAGE** tab on the Projects page.‌

Cut and paste the following line to your terminal.

```text
# docker login -u unused -e none scan.connect.redhat.com
```

When prompted for the password copy and paste the Registry Key located on the Upload Your Image tab in the project.

{% hint style="warning" %}
This Registry Key is unique per project, please make sure you are using the correct password for the project you are working on.
{% endhint %}

![Follow the step below Upload Your Image to manually upload your image](../.gitbook/assets/manualimageupload-container.png)

{% hint style="danger" %}
If you do not have a registry key populated or are having issues pushing your image please open a Support Ticket. Instructions on how to open a Support Ticket can be found in the [Getting Help](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/tools-and-resources/getting-help) Section.
{% endhint %}

