# Livegrep base image 

This directory contains tooling for building the base image for Livegrep and Codesearch.

This image is available on Docker Hub as `alexdebrie/livegrep-base:1`. You shouldn't need to use this directly unless you want to build your own images.

## Usage

1. **Building the Livegrep binaries**

    The first step is to build all of the Livegrep binaries and leave them on our local machine.
    
    You can do this with the following command:
    
    ```bash
    make build-binaries
    ```
    
    This will take a few minutes and will leave the built binaries on your local machine in the `bazel-bin/` directory.
    
2. **Building the base image**

    Once we've built the binaries, we'll create a small image that contains the binaries.
    
    You can build them with the following command:
    
    ```bash
    make run
    ```
    
    If you'd like your own tag for the image, you can use your own build command:
    
    ```bash
    docker build -t <your tag name> .
    ```
