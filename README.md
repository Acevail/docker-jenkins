Intro
=====

This is an example of using Docker images to host an entire build server infrastructure.

## Fig File overview

We create a build slave image that has node and maven installed

We spool up a copy of the Jenkins Docker image

We Spool up a Selenium environment using the Selenium Docker Images
 - 'nodes' for Chrome, Firefox with VNC access enabled (password: 'secret')
 - Selenium 'hub' to manage the nodes

A more in-depth overview can be found in [the About file](ABOUT.md)

Configuration
=============

### Git 

Remember that Git is not installed on Jenkins by default.  Go in and add the 'Git Plugin' and restart Jenkins

### Boot2docker notes

If you want your Jenkins to be visible on the network, it's a good idea to shut down boot2docker, use the VirtualBox
administration console to turn on the 3rd ethernet interface and set it to the default (bridged).  This will cause the
host computer to have two IP addresses, one that routes straight to the VM.  This will save you from having to set up
port forwards for everything.
