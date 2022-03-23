# Submitting your content

On your local copy of the GitHub repository, go to the chart's directory and create a subdirectory with the version of the chart you'll be certifying.&#x20;

If the version will be 0.1.0, the submission directory will be :&#x20;

`charts/partners/<your company>/<your chart name>/0.1.0`

**I - If you are submitting the chart :**

* The chart could be a **.tgz file** created using the `helm package` command or **a directory** with the chart source. If it is a tarball, it can be placed directly under the 0.1.0 directory.
* You can also add the chart verification report, stored in a file called `report.yaml`

**II - If you are submitting only the report :**

* You should stored the chart verification report in the directory, in a file called `report.yaml`

Use the `git add` command to indicate that these files will be added, and the `git commit` command to record the changes.

Finally, you need submit a **pull request (PR)** to request the certification review. You can do this via the GitHub website in your repository, or use the [GitHub CLI](https://cli.github.com/manual/gh\_pr\_create).&#x20;

**If the pull request is successful, your Helm chart will be certified.**&#x20;

If you have allowed publishing in our repository, the chart will be available through the **official repository URL**: [https://charts.openshift.io](https://charts.openshift.io) .&#x20;

You can follow the instructions given there to install it in your OpenShift cluster.

{% hint style="info" %}
For additional information on this process, including troubleshooting tips, see the [repository documentation](https://github.com/openshift-helm-charts/charts/tree/main/docs) in GitHub.
{% endhint %}
