# Cross Image Building for Shared Component libraries

This repo hosts a custom GitHub Action pipeline that builds custom [cross](https://github.com/cross-rs/cross) docker images for cross complication of rust crates.

The main target for these custom cross images are the Android builds for the different shared components libraries:

- [Aries Askar](https://github.com/hyperledger/aries-askar)
- [Indy VDR](https://github.com/hyperledger/indy-vdr)
- [AnonCreds RS](https://github.com/hyperledger/anoncreds-rs)

By default, cross uses the following android related variables for building the Android cross images:

- Android NDK Version: `r25b`
- Android SDK Level: `28`
- Android Version: `9.0.0_r1`

The versions are too high for most deployments, and therefore this images builds the images configured with the following variables:

- Android NDK Version: `r13b`
- Android SDK Level: `21`
- Android Version: `5.0.0_r1`

## Using the images

> TODO: Add instructions on how to use the custom images over the default cross images

## Building the images

To build the images, make sure you have maintainer rights on the repository. Then go to the [Build Shared Components Cross Images](./actions/workflows/build-cross-images.yml] action page, and manually run the workflow. This should build the images and push them to the GitHub container registry.

The following images are built:

- ghcr.io/animo/cross/aarch64-linux-android:latest
- ghcr.io/animo/cross/armv7-linux-androideabi:latest
- ghcr.io/animo/cross/i686-linux-android:latest
- ghcr.io/animo/cross/x86_64-linux-android:latest
