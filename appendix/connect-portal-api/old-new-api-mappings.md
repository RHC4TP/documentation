# Red Hat Connect API migration assistance

The legacy Red Hat Connect API, which is located [here](https://connect.redhat.com/api-docs), will be deprecated on July 10th, 2021 and no longer be available for use.   The new API can be found [here](https://catalog.redhat.com/api/containers/v1/ui/).  In order to ease the transition, this page attempts to guide users to to endpoints in the new API that provide similar functionality to a deprecated one.

| old | new | Notes |
| -- | -- | -- |
| GET /api/v2/companies/{nid} | [get_vendor_by_org_id](https://catalog.redhat.com/api/containers/v1/ui/#/Vendors/pyxis.vendors.get_vendor_by_org_id) | nid / cnid is obsolete |
|  GET /api/v2/container/{pid}/certResults/{digest} | [query all images in your project](https://catalog.redhat.com/api/containers/v1/ui/#/Certification%20projects/pyxis.images.get_images_by_project_id)   | Scan status and certification results can be discovered by querying for your container images. For example, you may query all images in your project. Note that not all results in the certification assessment data will be applicable for a given image.
|GET /api/v2/projects/{pid} | [Query project by PID](https://catalog.redhat.com/api/containers/v1/ui/#/Certification%20projects/pyxis.projects.get_certification_project_by_pid) | Query by PID is provided as a convenience but the new API uses the _id property of projects as the primary identifier.  _id is also what you will find in the links section of the new API.  It is recommended you transition away from using PID in order to have the best experience with the new API.  Note: project _id is also visible in the url when viewing the project in the browser.
|PUT /api/v2/projects/{pid} | Update your projects using [PATCH](https://catalog.redhat.com/api/containers/v1/ui/#/Certification%20projects/pyxis.projects.patch_certification_project) or [PUT](https://catalog.redhat.com/api/containers/v1/ui/#/Certification%20projects/pyxis.projects.update_certification_project) endpoints. |  Requires using the new project identifier (_id) rather than PID.
| POST /api/v2/projects | [create project](https://catalog.redhat.com/api/containers/v1/ui/#/Certification%20projects/pyxis.projects.create_certification_project) |
| POST /api/v2/projects/{pid}/tags| Tags are distributed across image metadata. You may [query for all images in your project](https://catalog.redhat.com/api/containers/v1/ui/#/Certification%20projects/pyxis.images.get_images_by_project_id) to compile the list.
| POST /api/v2/projects/{pid}/archive | [PATCH](https://catalog.redhat.com/api/containers/v1/ui/#/Certification%20projects/pyxis.projects.patch_certification_project) your project with 'project_status' = 'archived'.
| POST /api/v2/projects/{pid}/[re]build | Create a [build request](https://catalog.redhat.com/api/containers/v1/ui/#/Certification%20projects/pyxis.cert_project_build_request.create_certification_build_request)
| POST /api/v2/projects/{pid}/containers/{digest}/tags/{tag}/publish | Create a [tag request](https://catalog.redhat.com/api/containers/v1/ui/#/Certification%20projects/pyxis.cert_project_tag_request.create_certification_tag_request)
|POST /api/v2/projects/{pid}/containers/{digest}/vulnerabilities | For a given container image record you can [query for its vulnerabilities.](https://catalog.redhat.com/api/containers/v1/ui/#/Images/pyxis.vulnerabilities.get_vulnerabilities_by_image_id)
|GET /api/v2/products/{nid} | Legacy products were replaced by [product listings](https://catalog.redhat.com/api/containers/v1/ui/#/Product%20listings) in the first half of 2020.




