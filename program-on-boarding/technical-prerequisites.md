# Technical Prerequisites

### Getting Software

Certification requires that you verify the functionality of your product on the target Red Hat platform. Through the partner program, Red Hat offers free (also know as Not-for-resale or NFR) subscriptions for products such as Red Hat OpenShift Container Platform. To request software access as a partner, [follow these instructions](https://redhat-connect.gitbook.io/red-hat-partner-connect-general-guide/benefits/software-access). Once your access has been approved, you may [download software from the Customer Portal](https://access.redhat.com/downloads/).

The following are requirements for building container images such that they meet the certification criteria. This section applies to both container application and Operator images. Although labels and licenses are not required to successfully build a container, they are required for Red Hat Certification.&#x20;

### Dockerfile Requirements

See our [Certification Policy Guide ](https://access.redhat.com/documentation/en-us/red\_hat\_openshift\_certification/4.9/html-single/red\_hat\_openshift\_software\_certification\_policy\_guide/index#assembly-requirements-for-container-images\_openshift-sw-cert-policy-introduction)for full image requirements for certification.

#### **Example Dockerfile for Container Application:**&#x20;

```
FROM registry.redhat.io/rhel8
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

### Operator Requirements&#x20;

See our [workflow documentation](https://access.redhat.com/documentation/en-us/red\_hat\_openshift\_certification/4.9/html/red\_hat\_openshift\_software\_certification\_workflow\_guide/con\_operator-certification\_openshift-sw-cert-workflow-complete-pre-certification-checklist-for-containers).

{% hint style="info" %}
**Note:** We suggest using the [Operator SDK ](https://sdk.operatorframework.io/)to build your Kubernetes Operator for certification.
{% endhint %}

###

