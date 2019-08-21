## Timings

1 Week

## Summary

Uber have released an example application that uses their external API. It is built in Python using flask.

Your job is to create working development,testing and production environments and to build a pipeline to move the code through them using jenkins.

You can clone the code from the following repo:

[https://github.com/uber/Python-Sample-Application](https://github.com/uber/Python-Sample-Application)

You should fork this repo to one of your own.

## Tasks

* Create a development environment using Vagrant and provision it with Chef such that it can run the application successfully.
* Create a separate cookbook to provision Nginx as a reverse proxy and have it proxy port 80 to the port of your application. The application port should be configurble using chef attributes but default to 3000.
* Create an AMI using packer and your cookbooks that is capable of running the application and configure jenkins to use this as a slave
* Create a Jenkins job that listens for webhooks from your forked repo and starts a testing job
* Run the tests in the application on the slave node
* Create a job that builds your AMI when all tests have passed using packer.

## Deliverables

1. Python cookbook stored in a github repo ( separate )
2. Nginx cookbook stored in a github repo ( separate )
3. Forked uber application repo with Vagrantfile, Berksfile, packer.json and ability to simply Vagrant up and run in dev
4. Jenkins Job that runs test suite on pushes to master branch of forked application repo.
5. Separate Jenkins job that buils an application AMI using packer.json when tests pass successfully

## Notes

When it comes to setting up the python slave nodes the group should create their amis and only one need be used. They students will not have access to the configuration of jenkins to set one up. So the instructor can pick the best AMI and set up the slave for them to use.
