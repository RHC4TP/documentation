# Operators Introduction

An Operator is a method of packaging, deploying and managing a Kubernetes application. A Kubernetes application is an application that is both deployed on Kubernetes and managed using the Kubernetes APIs and kubectl/oc tooling. You can think of Operators as the runtime that manages this type of application on Kubernetes. 

## Distributing Operators 

As a partner, there are three places where you can contribute an operator, each with a different publishing endpoint:

![](../.gitbook/assets/operator-publishing-paths-1.png)

* **Certified Operators** - submitted through Red Hat Connect - listed in OpenShift OperatorHub
* **Community Operators** - submitted through GitHub - listed in both OpenShift _and_ OKD OperatorHub
* **Upstream Community Operators** - also submitted through GitHub -  listed in the [OperatorHub.io](https://operatorhub.io)  community website

{% hint style="success" %}
This guide is made for Red Hat Connect and will take you through the process of publishing a Certified Operator to OpenShift OperatorHub.  
{% endhint %}



