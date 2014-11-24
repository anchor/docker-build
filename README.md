docker-base
============

Base build scripts for docker images

This repo contains both scripts full of functionality for the automation of docker builds, and a subfolder of sample implementations for customizing the steps of the deployment. 

You can use the sample files under the Automating section of this README to create your own repo. During building, the CI environment will clone this repo and use the function scripts to automate the build processes. 


### Create a new docker build from this repo

Let's call your repo `docker-myproject`

Your repo should have the following structure

     | build
     | src
       - baseline
       - objects
       - release

There are a number of sample files within the `docker-base/samples` folder. These include the `src` extensions, and sample base `build` file. 

### Automated project setup

    mkdir -p docker-myproject/src
    git clone https://github.com/anchor/docker-base
    cp docker-base/samples/* docker-myproject/src
    mv docker-myproject/src/build docker-myproject
    cd docker-myproject
    
Use the sample implementation files in `src/` to get started. 

### Running automated builds

To execute in your project build in your CI environment, e.g. jenkins, use this command:
`sh build NAME DOCKER_REGISTRY DOCKER_OPTS VERSION`



### Running the created image


You'll probably need a command like: 

    docker run -e FOO_ENV=blah myregistry.com.org/engineering/myproject myprojectexec

Note the `-e ENV=val` is ordered before the definition of the docker registry

