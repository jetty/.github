# .github

## Reusable GitHub Action

This repostiory contains some pre defined/re usable GitHub Actions to avoid copy/paste the same code in multiple repositories

Simply use

```yaml

jobs:
  build:
    name: Maven Build CI
    uses: jetty/.github/.github/workflows/maven-ci.yml@main
    with:
      jdk-matrix: '[ "11" ]'
      verify-goal: 'install javadoc:javadoc -e -B -V'
      ...... nore parameters
```
### Parameters 

`maven_args`: contains some Apache Maven arguments (default: `-D"invoker.streamLogsOnFailures"`)

`maven_version`: Apache Maven version to use (default: `3.9.5`)

`os-matrix`: array of os to use as matrix (default: `[ "ubuntu-latest" ]`) (possible values: `[ "ubuntu-latest", "windows-latest", "macOS-latest" ]` )

`jdk-matrix`: array of jdk to use (default: `[ "11", "17" ]`)

`matrix-exclude`: array of exclusion from the matrix (default: none) (format: `'[{ "jdk": "8", "distribution": "microsoft"},{ "jdk": "20", "distribution": "microsoft"}}`)

`max-parallel`: maximum of jobs in parallel (default: 100)

`timeout-minutes`: total timeout for the build (default: 360)

`jdk-distribution-matrix`: matrix of jdk distribution to use (default: `[ "temurin" ]`)

`verify-goal`: Apache Maven goals to use (default: `install javadoc -e -V -B`)

`verify-fail-fast`: fail fast of the build in case of one part of the matrix failure (default: `true`)



