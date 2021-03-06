## How to run test
To run all tests in this project, one could simply do

```bash
sbt test
```

It will start a local `SparkContext` with `0.75 * <number of cores in your machine>` cores to
run individual tests one by one. To speed up the test process, you could
specify the following property `spark.executor.cores` to use more cores as
the following example.

```bash
sbt -Dspark.executor.cores=10 test
```

## How to skip tests in assembly

As all the tests could take 20+ minutes to run, one could skip tests in assembly process by

```bash
sbt "set test in Test := {}" assembly
```