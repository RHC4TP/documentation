# Preparing your test environment

To run the full set of chart-verifier tests you will need access to an **OpenShift cluster**, so the chart installation and its chart test(s) can be executed. You can disable these OpenShift tests through command line options, but they will need to run successfully for certification to be approved.

As a Red Hat partner, you have free access to an **OpenShift Container Platform subscription** that you can use to install a cluster in your own lab. To learn more about the benefit of software access as part of Red Hat Partner Connect, see the [program guide](https://redhat-connect.gitbook.io/red-hat-partner-connect-general-guide/benefits/software-access).



Furthermore, you have different options to install an OpenShift cluster to create your test environment :

* You can install a fully managed cluster with our [Managed Services Openshift cluster](https://www.redhat.com/en/technologies/cloud-computing/openshift/osd-managed-trial). This option is a 60 day trial.
* You can install a [Self managed cluster](https://www.redhat.com/en/technologies/cloud-computing/openshift/ocp-self-managed-trial) **** that you can install in your cloud, datacenter or computer. This option allows you to make use of our Partner Subscriptions (also known as NFRs) for permanent deployments.

See [openshift.com/try](https://www.openshift.com/try) for details and restrictions.



If you need more information on how to manage your cluster to install and configure your Helm Chart, please consult this documentation :

* [OpenShift Container Platform](https://docs.openshift.com/container-platform/4.7/welcome/index.html)
* [Openshift Cluster CLI Management](https://docs.openshift.com/container-platform/4.7/cli\_reference/openshift\_cli/getting-started-cli.html)
* [Helm Chart Management in Cluster](https://docs.openshift.com/container-platform/4.7/cli\_reference/helm\_cli/getting-started-with-helm-on-openshift-container-platform.html)
