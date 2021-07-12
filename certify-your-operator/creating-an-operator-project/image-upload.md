# Uploading your Operator Image

{% hint style="info" %}
Make sure to take a look at the [Technical Prerequisites](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/program-on-boarding/technical-prerequisites) section to validate that your Dockerfile will pass our certification scan.
{% endhint %}

## The Build Service <a id="the-build-service"></a>

{% hint style="warning" %}
The Build Service currently only supports regular container images and does not build operators.‌ You can use this for your operator image only, not the metadata files. 
{% endhint %}

The Automated Image Build Service automates the rebuilding of your image whenever an updated Red Hat package is available. It also scans your image \(after a successful build\) for any security vulnerabilities that may be present prior to publishing your image to the Container Catalog. The build service clones your Github/Gitlab repository onto a build server, and uses the Dockerfile to build your image. It is a requirement from Red Hat to properly maintain your image by keeping up to date with the latest security updates. By not using the automated build service, you are opting into manually maintaining and rebuilding your image every time an update is released.‌

### **Configuration** <a id="configuration"></a>

Configuration is very easy and straightforward. Follow the steps below:‌

In the header for the Project you created you will notice a tab labeled **Build Service**:‌

![](../../.gitbook/assets/screen-shot-2021-06-30-at-3.13.18-pm.png)

Click on the **Configure Build Service** button.‌

![](../../.gitbook/assets/screencapture-connect-stage-redhat-projects-60d30f5bbd852dbf4220902b-builds-configure-2021-06-30-15_14_47.png)

Toggle the **Build Service** on.

Fill in the git repo and the Dockerfile name if it has a name other than “Dockerfile”.‌

If your repository is public, then all that is needed is the git source URL \(HTTPS link\). If your repository is private, then you must configure the build service with the SSH link and a private SSH key. The git repository needs the public SSH key associated with the private key in order to successfully clone. It is recommended to create a new public and private SSH key just for the project. Never use your own personal private key.

SSH key files must be stored in the PEM format, using the RSA algorithm. When configuring the build service, make sure to include the “-----BEGIN RSA PRIVATE KEY-----” and “-----END RSA PRIVATE KEY-----” blocks surrounding your private SSH key.‌

Click **Save** at the end of the page.‌

Click **Add New Build** button on the subsequent page.‌

![](../../.gitbook/assets/screen-shot-2021-06-30-at-3.19.10-pm.png)

Enter a tag number \(the version number of the plugin\) and click **Start build**.‌

![](../../.gitbook/assets/screen-shot-2021-06-30-at-3.21.51-pm.png)

Once submitted, the new build will be added and scanned.

![](../../.gitbook/assets/screen-shot-2021-06-30-at-3.22.50-pm.png)

The Build Service must first be completed before it can begin the scanning process for certification. If your Build Service fails or does not complete, make sure the details you entered under the Configure Build Service tab is correct and confirm that your Dockerfile conforms to the examples provided in this link.‌

## Manually Upload Your Image <a id="manually-upload-your-image"></a>

If you are not using the Build Service, you will need to manually upload your image from the **UPLOAD YOUR IMAGE** tab on the Projects page.‌

Cut and paste the following line to your terminal.

```text
# docker login -u unused -e none scan.connect.redhat.com
```

When prompted for the password copy and paste the Registry Key located in the **Push your image** link on the **Images** tab in the project.

{% hint style="warning" %}
This Registry Key is unique per project, please make sure you are using the correct password for the project you are working on.
{% endhint %}

![](../../.gitbook/assets/screen-shot-2021-05-25-at-9.47.22-am-1.png)

{% hint style="danger" %}
If you do not have a registry key populated or are having issues pushing your image please open a Support Ticket. Instructions on how to open a Support Ticket can be found in the [Getting Help](https://redhat-connect.gitbook.io/red-hat-partner-connect-general-guide/managing-your-account/getting-help/support-ticket) Section.
{% endhint %}

