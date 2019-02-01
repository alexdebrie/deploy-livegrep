# Deploy Livegrep

This repository contains Dockerfiles and tooling for building [Livegrep](https://github.com/livegrep/livegrep) images.

For a guided walkthrough, read the post on getting [Faster GitHub Search with Livegrep](https://www.alexdebrie.com/posts/faster-code-search-livegrep/).

## Contents

1. **Base Image**

   You can build a base image from the tooling in the `base/` directory.
   
   A pre-built image is available on Docker Hub as `alexdebrie/livegrep-base:1`. You can use it as a base image in your Dockerfile:
   
   ```Dockerfile
   FROM alexdebrie/livegrep-base:1
   
   ...
   ```
   
   Or run it on your command line:
   
   ```bash
   docker run -it alexdebrie/livegrep-base:1 /bin/bash
   ```
   
2. **Codesearch image**

   The tooling in the `codesearch/` directory will help you build an image with a Codesearch index for serving.
   
   [Check out the instructions](./codesearch/README.md) in that directory for more information.
   
3. **Livegrep image**

   The tooling in the `livegrep/` directory will help you build an image to run the Livegrep web UI.
   
   [Check out the instructions](./livegrep/README.md) in that directory for more information.