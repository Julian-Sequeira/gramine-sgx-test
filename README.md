# Description

Playing around with and learning about Gramine SGX;
* attested TLS
* creating manifest files
* deploying nodeJS applications in Gramine
* Gramine shielded containers

# Creating a manifest file

There are three main components to Gramine, and we need to specify them in the manifest file:

1. **Library OS**: 
2. **Platform Adaption Layer (PAL)**: This is the layer that implements a drawbridge interface to the Gramine library OS. Whenever Gramine needs something from the host platform (ex. something from the file system) - it calls a function in PAL.
3. **Patched C Library**: 



# Gramine Shielded Containers

This is infrastructure allowing the deploying of Docker containers protected by Intel SGX enclaves.
* `gsc` transforms Docker image into a new image including library OS, manifest files, other SGX information
* `gsc build` creates the Docker image
* `gsc sign-image` signs it
* image is then run using `docker run` as normal
