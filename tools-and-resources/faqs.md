# FAQs

## Who can upload images through the Portal?

The administrator account created for your organization may upload images. However, this account may grant permissions to other user accounts so that those accounts may also upload images.

## Can I change the Product Version after I created a Project?

No you cannot; therefore make sure you set it up correctly before starting any project with that product version. Keep in mind that the product version should be considered as the name of the image, the version can be specified later on when you Tag your image during the project.

## Can a container be built on another version of Linux other than Red Hat?

No, the Red Hat certification is a validation that the container, which is a combination of application software and Linux, is made of genuine Red Hat parts. Currently, Red Hat has just a little over one million paying customers today. Our customers do not use other versions of Linux and pay us for the services and support we provide to them. Therefore, your container needs to be built on a version of Red Hat Linux.

## Will the catalog support an ISO or virtual machine image as the container image?

No, this certification process is specifically for containers. Therefore, your image needs to be in Dockerfile format. You can find an example provided by Red Hat Engineering: Dockerfile Examples

## What path should my licenses be on?

Should be on / \(the root or home directory of where the application resides\). You can find an example provided by RH Engineer:Dockerfile Example

## How do I change the namespace and repository name of my project?

First, unpublish all containers. Then change the namespace/repo in the project settings. Finally, re-publish your containers.

