# jenkinz

Docker image with custom Jenkins with plugins

## Customize your own Jenkins
### Clone this project
```shell
#http
git clone https://github.com/scabrerao/jenkinz.git

#ssh
git clone git@github.com:scabrerao/jenkinz.git
```

### Add Jenkins plugin
  To add or modify these plugins only need to modify the content of plugins.txt file, some plugins need add also configuration files like "locale.xml" inside config that need to be copied into jenkins_home of the container.

### Building the project locally
```
docker build --no-cache --pull --force-rm --rm -f dockerfile -t "jenkinz:{version}" .
```

### Starting Jenkins from custom iamge locally
- docker-compose 
	```
	docker-compose up -d
	```
    *Need to check the version in the docker-compose.yml file
- commands 
	```
	docker run --name jenkinz -p 8080:8080 -p 50000:50000 -v jenkinsVol:/var/jenkins_home scabrerao/jenkinz:lts
	```

### Publish a docker image
```
docker login
docker tag jenkinz:{version} {githubUser}/jenkinz:latest
docker push {githubUser}/jenkinz:latest
```

## Public Docker image example
[jenkinz Docker Image](https://cloud.docker.com/u/scabrerao/repository/docker/scabrerao/jenkinz)

```docker push scabrerao/jenkinz:tagname```

## Jenkins components
 - Jenkins:lts
 - Users:
    Admin
 - Plugings:
        - slack
        - rebuild
        - global-build-stats
        - ec2
        - email-ext
        - greenballs
        - snsnotify
        - ssh-slaves
        - windows-slaves
        - build-timestamp
        - build-timeout
        - build-pipeline-plugin
        - delivery-pipeline-plugin
        - git-parameter
        - jenkins-multijob-plugin
        - pipeline-utility-steps
        - uno-choice
        - workflow-aggregator
        - nested-view
        - view-job-filters
        - extra-columns
        - bitbucket-build-status-notifier
        - bitbucket-pullrequest-builder
        - cloudbees-bitbucket-branch-source
        - git
        - stashNotifier
        - ansicolor
        - copyartifact
        - envinject
        - groovy
        - job-dsl
        - nodejs
        - powershell
        - ws-cleanup
        - bitbucket
        - file-operations
        - cucumber-living-documentation
        - cucumber-reports
        - cucumber-trends-report
        - sonar
        - performance
        - build-user-vars-plugin
        - metrics
        - build-metrics
        - cobertura
        - blueocean
        - locale
        - msbuild
        - mstest
        - mstestrunner
        - build-with-parameters
        - nodelabelparameter
        - kubernetes
        - docker-plugin
        - github-pullrequest
        - pipeline-aggregator-view
        - gitlab-plugin
        - parallel-test-executor
