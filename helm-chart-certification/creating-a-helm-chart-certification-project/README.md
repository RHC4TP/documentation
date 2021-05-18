# Creating a Helm Chart Certification Project

Partners who want to certify a Helm chart must create the corresponding project in Red Hat Partner Connect. This is a one-time this step you will to provide information about your company and your product, so it can be included in the ecosystem catalog.

To create a project, you must log into the certified technology portal in [Red Hat Partner Connect](https://connect.redhat.com/login). For more information on registration and access, see the [Program Prerequisites](../../program-on-boarding/prerequisites.md) section.

Once you are logged in, go to the Manage Projects section under the Product Certification menu. 

![](../../.gitbook/assets/screen-shot-2021-04-26-at-3.24.58-pm.png)

You will see an option to Create Project. Select Helm Chart as the project type.

You will need to provide the following information:

* Project name. This is a name you choose to track the project within the certification service. It is not visible externally.
* Chart name. The name of your chart, which must follow Helm [naming conventions](https://helm.sh/docs/chart_best_practices/conventions/). 
* Distribution method. You have two choices:
  * Publish your chart in the Red Hat Helm Chart repository, _charts.openshift.io_. In this case, users will pull your chart from this repository.
  * Publish your chart in your own Helm Chart repository. In this case, an entry will be added to the index at _charts.openshift.io_ with information about the location of your chart.



