## tn-query-parent

A parent POM that sets up the common build elements across the tn libraries and services.

### Features
In addition to the usual features provided by Maven, `tn-parent` adds the following:

* switches the Java compiler to Java 21.
* attaches source and test jars that will be installed/deployed to the Maven repository when the relevant `install` and `deploy` goals are used.
* configures assembly when `src/main/assembly/assembly.xml`exists.
* configures Docker build when `Dockerfile` exists.
* integration test separation via a `src/it` directory, so that fast running unit tests can be run in isolation to typically slower integration tests.
* contract test separation via a `src/ct` directory, so that fast running unit tests can be run in isolation to typically slower contract tests.
* [JaCoCo](https://www.jacoco.org/index.html) coverage reports, which are generated with every `test` run.
* [Pitest](https://pitest.org/) mutation tests, that can be optionally run by adding `-Dpitest` to the Maven command.

### Build

Typically, the command `mvn clean install` is used, which builds and packages, runs unit and integration tests and installs the artifacts into the local
[Maven](https://maven.apache.org/) repository.