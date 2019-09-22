# Creating an Operator Project

{% hint style="info" %}
Certified operators are listed in and consumed by customers through the embedded OpenShift OperatorHub, providing them the ability to easily deploy and run your solution. Additionally, your product and operator image will be listed in the Red Hat Container Catalog using the listing information you provide.‌
{% endhint %}

From the [Red Hat Partner Connect web portal](https://connect.redhat.com/), select **ZONES** at the top of the page.‌

Scroll down to the RED HAT OPENSHIFT & CONTAINER zone and click **CREATE A PROJECT**.‌

![](../.gitbook/assets/project1.png)

Complete the Create New Project Wizard. 

### 1. Product 

![](../.gitbook/assets/project1%20%281%29.png)

### 2. Container Type 

Select **Operator**

![](../.gitbook/assets/project2op.png)

### 3. Release Category

![](../.gitbook/assets/project3.png)

### 4. OS Content Type 

{% hint style="danger" %}
This information cannot be changed after project is created. If you used the Operator-SDK to build your operator, select **Red Hat Universal Base Image \(UBI\)**. 
{% endhint %}

![](../.gitbook/assets/project4.png)

### 5. Distribution Method

{% hint style="danger" %}
This information cannot be changed after project is created
{% endhint %}

![](../.gitbook/assets/project5.png)

Once you have finalized all your selection click on **Create Project.** 

