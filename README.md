# jenkins-pipeline

Contains relevant files for deploying a Jenkins pipeline for a simple site on an EC2 instance using Docker.

To set up, install [Jenkins](https://www.jenkins.io/doc/book/installing/) and [Docker](https://docs.docker.com/engine/install/) by following the relevant instructions.

We will need to install the Jenkins plugin `Docker Pipeline`.

Next add the jenkins user to the docker group and restart the machine:
```
sudo usermod -aG docker jenkins
reboot
```

Finally, set up GitHub hook trigger for GITScm polling and we should be good to go.
