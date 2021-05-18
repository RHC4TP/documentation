# Running the Helm Chart verification tool

The tool can be invoked with the following command:

```bash
$ podman run --rm quay.io/redhat-certification/chart-verifier verify <chart URL>
```

Where _&lt;chart URL&gt;_ is the URL of the Helm chart archive \(the _.tgz_ file\). Note that the same command can be used with _docker_ instead of podman.

The output of _chart-verifier_ indicates the tests executed and a PASS/FAIL result for each test. It will also indicate whether a test is mandatory or recommended for certification. 

For more information on all the command line options, see the [chart-verifier](https://github.com/redhat-certification/chart-verifier) project on GitHub.

