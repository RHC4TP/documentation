# Certification Service Options

This table summarizes the scenarios for submitting your content for certification, depending on how you want your chart to be accessed and whether the chart tests have some dependencies on your local environment.



| Objective | Include chart? | Include chart verification report? | Red Hat Certification Actions | Red Hat Publication Actions |
| :--- | :--- | :--- | :--- | :--- |
| You want your certified chart to be stored at charts.openshift.io. You also want to take advantage of Red Hat CI for ongoing chart tests. | Yes | No | chart-verifier will be executed in the Red Hat CI environment to ensure compliance | Chart will be available for download from charts.openshift.io |
| You want your certified chart to be stored at charts.openshift.io. But your chart has some external dependencies, so it must be tested in your own environment. | Yes | Yes | Results will be reviewed to ensure compliance | Chart will be available for download from charts.openshift.io |
| You don't want your  certified chart to be stored at charts.openshift.io | No | Yes | Results will be reviewed to ensure compliance | Chart will be available for download from your designated Helm chart repository. A corresponding entry will be added to the index.yaml at charts.openshift.io |



