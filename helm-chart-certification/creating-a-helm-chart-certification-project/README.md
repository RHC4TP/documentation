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

{% hint style="danger" %}
The following information cannot be changed once selected. Read the descriptions carefully; or if you have any question please go to: Get Help
{% endhint %}

![Helm chart Certification - Creating project](<../../.gitbook/assets/Screenshot 2022-08-04 at 15.01.41.png>)

* **Project name** **:** This is a name you choose to track the project within the certification service. It is not visible externally.
* **Chart name :** The name of your chart, which must follow Helm [naming conventions](https://helm.sh/docs/chart\_best\_practices/conventions/).&#x20;
* **Specialised Certification :** Select this option if you want to certify a **CNF** (Cloud Native Network Function) Helm Chart
* **Distribution method :**&#x20;
  * **Publish your chart in the Red Hat Helm Chart repository**  : \
    Choose this option if you want your chart hosted and published in charts.openshift.io. In this case, users will pull your chart from this repository. Your helm chart will be available in the [Ecosystem Catalog](https://catalog.redhat.com/platform/red-hat-openshift/software/search?type=Helm%20chart) and Developer Catalog (or by default with OpenShift).
  *   **Publish your chart in your own Helm Chart repository :**&#x20;

      Choose this option if you want to host your helm chart in any publicly available repository. An entry will be added to the index at charts.openshift.io with information about the location of your chart. Users will pull your chart from this repository and your helm chart will be available in the [Ecosystem Catalog ](https://catalog.redhat.com/platform/red-hat-openshift/software/search?type=Helm%20chart)and Developer catalog (or by default with OpenShift).
  *   **Web catalog only** : \
      Choose this option if you do not want your helm chart to be available via charts.openshift.io. In this case, your helm chart will not be available within the Developer Catalog (or by default with OpenShift) therefore users will not be able to pull your helm chart from this repository. There will only be a catalog listing in the [Ecosystem Catalog](https://catalog.redhat.com/platform/red-hat-openshift/software/search?type=Helm%20chart).&#x20;



4\. Once the basic information filled, you will be redirected to the **Project checklist** page, where you can view and edit all the required details for the Certification.

![Helm Chart certification - Checklist](<../../.gitbook/assets/Screenshot 2022-08-04 at 15.23.50.png>)

{% hint style="info" %}
If you have selected **CNF** during the project creation, you will need to validate the functionality of your CNF through this [specific workflow](https://redhat-connect.gitbook.io/openshift-badges/badges/cloud-native-network-functions-cnf). To begin the process, click on the button **Start** in the specific CNF checklist item.
{% endhint %}
