---
description: >-
  Partners have two methods for uploading and testing their Operator metadata
  bundle image.
---

# Uploading your Operator Bundle

## CI/Local Pipeline <a href="manually-upload-your-image" id="manually-upload-your-image"></a>

This option is our advanced method for partners interested in integrating the tooling into their own developer workflows for continuous verification, want access to comprehensive logs for a faster feedback loop, or have dependencies that are not available in a default OpenShift installation.

You will run the tooling on your own OpenShift cluster, using [OpenShift Pipelines](https://cloud.redhat.com/learn/topics/ci-cd) (based on Tekton) to run the certification tests, and you will be able to see comprehensive logs and debug in real time. Once you are ready to certify and publish your Operator bundle, the pipeline submits a pull request (PR) to GitHub on your behalf. If everything passes successfully, your Operator will be automatically merged and published.

Find the instructions for the local pipeline[ HERE.](https://github.com/redhat-openshift-ecosystem/certification-releases/blob/main/4.9/ga/ci-pipeline.md#operator-certification-ci-pipelineinstructions) If you run into any issues please reach out to the [Success Team](https://connect.redhat.com/support/technology-partner/#/).&#x20;

## Hosted Pipeline  <a href="manually-upload-your-image" id="manually-upload-your-image"></a>

This option is our quicker, more simple path to certification for those who are not as interested in the comprehensive logs, or are not ready to include it in their own workflows.

The process begins by submitting your Operator bundle via a GitHub PR. Red Hat then runs the certification tests using an in-house OpenShift cluster. This option is similar to the previous certification workflow, but was built with improved infrastructure. You will still receive information on what is failing both as comments on the PR and test results within your Red Hat Partner Connect account.

Find the instructions for the local pipeline [HERE](https://github.com/redhat-openshift-ecosystem/certification-releases/blob/main/4.9/ga/hosted-pipeline.md). If you run into any issues please reach out to the [Success Team](https://connect.redhat.com/support/technology-partner/#/).

