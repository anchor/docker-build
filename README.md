docker-base
============

Base build scripts for docker images


# Create a new docker build from this repo


Let's call your repo `docker-myproject`


Your repo should have the following structure
     | build
     | src
       - baseline
       - objects
       - release

`src/` - copy the examples from the `docker-base/samples` directory to your `docker-myproject/src` folder

`build` - copy the example file from `docker-base/samples/build`

# Running the created image


You'll probably need a command like: 

    docker run -e FOO_ENV=blah myregistry.com.org/engineering/myproject myprojectexec

Note the `-e ENV=val` is ordered before the definition of the docker registry

