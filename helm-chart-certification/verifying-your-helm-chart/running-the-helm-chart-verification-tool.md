# Running the Helm Chart verification tool

The tool can be invoked with the following command:

```bash
$ podman run --rm quay.io/redhat-certification/chart-verifier verify <chart URI>
```

Where _\<chart URI>_  indicates the location of the Helm chart. For example, the locations of the chart archive (the _.tgz _file). Note that the same command can be used with _docker_ instead of _podman_.

The output of _chart-verifier_ includes the tests executed and a PASS/FAIL result for each test. It will also indicate whether each test is mandatory or recommended for certification.&#x20;

For more information on all the command line options, see the [chart-verifier](https://github.com/redhat-certification/chart-verifier) on GitHub.
