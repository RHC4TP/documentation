# Creating a Helm Chart Certification Project

Partners who want to certify a Helm chart must create the corresponding project in Red Hat Partner Connect. This is a one-time this step you will to provide information about your company and your product, so it can be included in the ecosystem catalog.

To create a project, you must log into the certified technology portal in [Red Hat Partner Connect](https://connect.redhat.com/login). For more information on registration and access, see the [Program Prerequisites](../../program-on-boarding/prerequisites.md) section.

**Note :** **It is strongly recommended to have your container image certified before creating your Helm Chart certification project**

Once you are logged in, go to the **Manage certification projects** section under the **Product Certification** menu.&#x20;

![Product certification Menu](<../../.gitbook/assets/Screenshot 2022-03-22 at 11.08.49.png>)

1 .You will see an option to **Create Project**. Then choose **Red Hat OpenShift** as a Platform

![Choose OpenShift platform](<../../.gitbook/assets/Helm cert - Platform choice.png>)

2\. Select **Helm Chart** as the project type

![Choose Helm chart](<../../.gitbook/assets/Helm cert - Helm choice.png>)

3\. You will need to provide the following information:

![Helm chart Certification - Creating project](<../../.gitbook/assets/Screenshot 2022-08-04 at 15.01.41.png>)

* **Project name** **:** This is a name you choose to track the project within the certification service. It is not visible externally.
* **Chart name :** The name of your chart, which must follow Helm [naming conventions](https://helm.sh/docs/chart\_best\_practices/conventions/).&#x20;
* **Specialised Certification :** Select this option if you want to certify a **CNF** (Cloud Native Network Function) Helm Chart
* **Distribution method :** You have 2 choices:
  * Publish your chart in the Red Hat Helm Chart repository, _charts.openshift.io_. In this case, users will pull your chart from this repository.
  * Publish your chart in your own Helm Chart repository. In this case, an entry will be added to the index at _charts.openshift.io_ with information about the location of your chart.

{% hint style="info" %}
If you want your Helm Chart to be **only** published on our [Ecosystem catalog](https://catalog.redhat.com/), please contact us by opening a ticket with [TPSD](https://connect.redhat.com/support/technology-partner/#/case/list)
{% endhint %}

4\. Once the basic information filled, you will be redirected to the **Project checklist** page, where you can view and edit all the required details for the Certification.

![Helm Chart certification - Checklist](<../../.gitbook/assets/Screenshot 2022-08-04 at 15.23.50.png>)
