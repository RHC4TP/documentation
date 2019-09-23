# Operator Metadata

{% hint style="danger" %}
Make sure your Operator Image has been PUBLISHED before you Upload your Metadata. 
{% endhint %}

In your Project Page, click on **Operator Metadata** on the left hand box. 

![](../.gitbook/assets/image%20%285%29.png)

Publication in the OpenShift Marketplace requires a .ZIP metadata file. The .ZIP file should ONLY contain the following .YAML files: CSV, CRD, and Package Manifest. All other files added will cause the scan to fail. 

{% hint style="info" %}
For further questions or information regarding the files required please reach out to your Red Hat Connect contact or email connect@redhat.com
{% endhint %}

{% hint style="success" %}
We recommend creating a GitHub repository with the 3 required files and downloading it as ZIP. 
{% endhint %}

Once you have your .ZIP file ready you can upload it by clicking Upload Metadata. 

![](../.gitbook/assets/image%20%288%29.png)

Once upload is complete, scanning will begin. This may take up to 1 hour to complete. 

