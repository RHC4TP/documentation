# Technical Prerequisites

### Getting Software

You may need download Not-for-resale \(NFR\) access to Red Hat software such as Red Hat OpenShift Container Platform. To request software access as a partner, [follow these instructions](https://redhat-connect.gitbook.io/red-hat-partner-connect-general-guide/benefits/software-access). Once your access has been approved, you may [download software from the Customer Portal](https://access.redhat.com/downloads/).

The following are requirements for building any Certified Images. This section includes both Container Application and Operator Images. Although Labels and Licenses are not required to successfully build a container, they are required for Red Hat Certification. 

### Licenses Requirements

You need to include any relevant licenses within the `licenses/`directory. This is important for the end user to be aware of the terms and conditions applicable to the software. Including opens source licensing information, if open source components are included in the image. Here are some examples:  [https://choosealicense.com/](https://choosealicense.com/) 

### Dockerfile Requirements 

1. The Base image must be \(or must be based on\) a supported Red Hat image, such as Red Hat Enterprise Linux or [Red Hat Universal Base Image](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/program-on-boarding/containers-with-red-hat-universal-base-image-ubi). Any third party or community supported images such as Ubuntu, Debian, Alpine, CentOS etc are not supported by Red Hat and cannot be certified.
2. The following labels must exist: **name**, **maintainer**, **vendor**, **version**, **release,** **summary & description.**

#### **Example Dockerfile for Container Application:** 

```text
FROM registry.redhat.io/rhel7
MAINTAINER NAME <EMAIL@ADDRESS>

### Required OpenShift Labels 
LABEL name="APPLICATION NAME" \
      maintainer="EMAIL@ADDRESS" \
      vendor="COMPANY NAME" \
      version="VERSION NUMBER" \
      release="RELEASE NUMBER" \
      summary="APPLICATION SUMMARY" \
      description="APPLICATION DESCRIPTION" \

### add licenses to this directory
COPY licenses /licenses

### Add necessary Red Hat repos here
RUN REPOLIST=rhel-7-server-rpms,rhel-7-server-optional-rpms \

### Add your package needs here
    INSTALL_PKGS="PACKAGES HERE" && \
    yum -y update-minimal --disablerepo "*" --enablerepo rhel-7-server-rpms --setopt=tsflags=nodocs \
      --security --sec-severity=Important --sec-severity=Critical && \
    yum -y install --disablerepo "*" --enablerepo ${REPOLIST} --setopt=tsflags=nodocs ${INSTALL_PKGS} && \

### Install your application here -- add all other necessary items to build your image
RUN "ANY OTHER INSTRUCTIONS HERE"
```

#### Example Dockerfile Operator Image:

```text
FROM quay.io/operator-framework/helm-operator:v0.11.0

### Required OpenShift Labels
LABEL name="Wordpress Operator" \
      vendor="Bitnami" \
      version="v0.0.1" \
      release="1" \
      summary="This is an example of a wordpress helm operator." \
      description="This operator will deploy wordpress to the cluster."

# Required Licenses
COPY licenses /licenses

COPY helm-charts/ ${HOME}/helm-charts/
COPY watches.yaml ${HOME}/watches.yaml
```

### Operators 

An Operator is a method of packaging, deploying and managing a Kubernetes application. A Kubernetes application is an application that is both deployed on Kubernetes and managed using the Kubernetes APIs and kubectl/oc tooling. You can think of Operators as the runtime that manages this type of application on Kubernetes.

### Certified Operator Build Guide

We have created another guide that you can find[ here.](https://redhat-connect.gitbook.io/certified-operator-guide/) This guide is designed to take you step by step through the process of creating your operator using the Operator-SDK. There are examples for using both Helm and Ansible as well as more information on deploying a test environment for you to work with while developing your operator



