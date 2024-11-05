# kaniko-build-no-push

Uses an agent matching label 'kaniko'. Create template using this example config:
```
image: gcr.io/kaniko-project/executor:debug
Working directory: /home/jenkins/agent
command to run: sleep
arguments: 9999999
```
