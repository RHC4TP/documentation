# Image Scanning & Verification

## Image Scan

After the image has completed being uploaded, the image will display _Scan In-Progress_ in the **Status** column:

![](https://lh6.googleusercontent.com/Md5GfSHas9u1RwKUuIRsaR-ll2V1mIafz3DnQcX3rzEivwbuJMO0B0sVlXSB4E3mB1bVSxG1FHrxV8Xq0qWXtyGfUBoDTkbMoaTgpBIkQhZuoF7jp41vGwYOamixgPaAlrDzEuQG)

{% hint style="info" %}
It may be necessary to refresh the browser page to see the current status.
{% endhint %}

Once the image has completed the scan in Red Hat Connect repository, the image will show the results of the scan. Scans normally take about 10-15 minutes to complete.

![](https://lh4.googleusercontent.com/0ff1SFj6Zi13yXPvQdSl12lqEu1aSGQeNNMeawneaCiEXp1NQtQBh9SPo2oepfmb1oZ2ei_f2YMCGcsNFQ3W7NLtH_FkXZpD6a0s8zM8x3OovctfHnmffnwMWmXqyZmf02tZVHRR)

The **View** button will expand on the scan results. The **Publish** button will publish the image to the Red Hat Container Catalog. It will change to **Unpublish** once an image has been published. The **Remove** button allows you to remove an image that you no longer need.

## Image Verification

{% hint style="warning" %}
If the image returns a Passed scan status but the Publish button is still blocked, verify that you have completed the Certification Checklist.
{% endhint %}

If the image returns a **Failed** scan status, the results will automatically be displayed. Click on the name of the failed item \(in this example, _has\_licenses_\) for reference to the policy guide.

![](../.gitbook/assets/image%20%285%29.png)

{% hint style="info" %}
If you receive an **Access Denied** response when accessing the Policy Guide, please open a Support Ticket. Instructions on how to open a Support Ticket can be found in the [Getting Help](https://redhat-connect.gitbook.io/red-hat-partner-connect-general-guide/managing-your-account/getting-help/support-ticket) Section.
{% endhint %}

