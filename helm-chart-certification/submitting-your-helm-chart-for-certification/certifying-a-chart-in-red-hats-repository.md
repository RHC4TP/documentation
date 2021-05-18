# Submitting your content

On your local copy of the GitHub repository, go to the chart's directory and create a subdirectory with the version of the chart you'll be certifying. For example, if your certifying version 0.1.0 of your chart, your submission directory will be:

`charts/partners/<your company>/<your chart name>/0.1.0`

In that directory, and based on the options from the previous section, you will add:

* Your Helm chart, either the full source or the chart archive; and/or 
* Your chart verification report, stored in a file called _report.yaml_

Use the `git add` command to indicate that these files will be added, and the `git commit` command to record the changes.

Finally, you need submit a pull request \(PR\) to request the certification review. You can do this via the GitHub website, or use the [GitHub CLI](https://cli.github.com/manual/gh_pr_create). Once the PR is approved and merged, your chart will be added to the repository's index.yaml, and will be considered certified.

For additional information on this process, including troubleshooting tips, see the [repository documentation](https://github.com/openshift-helm-charts/charts/tree/main/docs) in GitHub.

