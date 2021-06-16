# Connect Portal API

Red Hat Connect exposes a REST interface. The interface supports a number of endpoints which can be used to automate the work of keeping your container images up to date. Official documentation for the Connect API can be found [here](https://catalog.redhat.com/api/containers/v1/ui/). 

In order to use the API, you need to use Red Hat Connect API keys. The keys will need to be included in the request as shown below:

```text
curl -X GET \
"https://catalog.redhat.com/api/containers/v1/projects/certification/pid/ospid-00000000-0000-0000-0000-00000000" \
-H "X-API-KEY: [api key]"
```

The legacy Red Hat Connect API, which is located [here](https://connect.redhat.com/api-docs), will be deprecated on July 10th, 2021 and no longer be available for use.  To assist with migration, the [migration assistance](https://redhat-connect.gitbook.io/partner-guide-for-red-hat-openshift-and-container/appendix/old-new-api-mappings) page maps functionality from old endpoints to new ones.



