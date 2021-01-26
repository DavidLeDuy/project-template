# Installation

There are 2 Ways to supply images.

## Docker Hub

**Currently only public images in Docker Hub are supported**

The file `image-options.json` contains the options needed to donwload the image.
At the moment you only need to suppy the contianer image name `myrepo/myname:tag`. The `:tag` can be ommitted if no different versions exist.

## Dockerfile

Alternatively you can supply a Dockerfile into this folder that gets build locally on the device.

The Dockerfile acts as a fallback and the donwload over Docker Hub is prioritized.

The support for external files is not planned for this version.
