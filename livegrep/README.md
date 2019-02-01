# Livegrep 

This directory contains tooling for helping you build a Livegrep image to serve the Livegrep UI.

## Usage

1. **Building the Livegrep image**

    You can build the image with the following command:
    
    ```bash
    make build
    ```
    
2. **Running the Livegrep instance with local Codesearch**
    
    Before running the Livegrep container, you must have a [Codesearch image](../codesearch/README.md) container running for the Livegrep server to use.
    
    If you are running your Codesearch image locally, you can start your Livegrep image with the following command:
    
    ```bash
    make run
    ```
    
3. **Running the Livegrep instance with remote Codesearch**
    
    If you are running your Codesearch elsewhere, you'll need to notify your Livegrep container of the location of the Codesearch image.
    
    You can use the following commands:
    
    ```bash
    export BACKEND_ADDR=<ip of your Codesearch container>
    docker run -p 8910:8910 -e "BACKEND_ADDR=${BACKEND_ADDR}:9999" livegrep
    ```
    
    Your Livegrep container will be accessible in your browser at `localhost:8910`.