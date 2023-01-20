## Bash Size Limit Report

This bash script leverages [Size Limit](https://github.com/ai/size-limit) package to check a pull request size change to master. This is helpful when developing component frameworks to see how your additions might be effecting inital loads.

It's hard for SaaS companies to leverage Github actions currently due to security concerns[1]. This script can be run in Circle CI without the use of a GHA. 

[1] See: [How We Discovered Vulnerabilities in CI/CD Pipelines of Popular Open-Source Projects](https://cycode.com/github-actions-vulnerabilities/).  

This does require setting up a `GITHUB_TOKEN` within CircleCI.

Example config.yml
```
checkSizeLimit:
  requires
    - install 
  steps:
    - run:
        name: Check Size
        command: bin/checkSize
```
