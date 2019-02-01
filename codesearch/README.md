# Codesearch 

This directory contains tooling for helping you build a Codesearch image with an index for serving.

## Usage

1. **Building an index**

    You can build a Codesearch index for your GitHub user by running the following commands:
    
    ```bash
    export GITHUB_USER=<your GitHub username>
    make build-index
    ```
    
    This will use the base image to build an index of all your public GitHub repos.
    
    If you'd like to use different Codesearch flags to build the index, you can run the following command:
    
    ```bash
    docker run -v ${PWD}:/out alexdebrie/livegrep-base:1 /livegrep-github-reindex <your Codesearch flags> -out /out/livegrep.idx
    ```
    
2. **Building and running the Codesearch image**

    After you've generated the index, you can build an image using your index with the following command:
    
    ```bash
    make build
    ```
    
    Then you can run your image with:
    
    ```bash
    make run
    ```
    
    Your codesearch instance will be serving GRPC requests at `localhost:9999`.
    
    For interacting directly with a GRPC server, I recommend using [Bloom RPC](https://github.com/uw-labs/bloomrpc). The relevant `.proto` file can be found [here](https://github.com/livegrep/livegrep/blob/master/src/proto/livegrep.proto).
