# Docker

Docker allows us to create images which are like AMI's in AWS so it already has some things installed on it.

We can use a docker image for our jobs by adding `image: imageName` or `image: imageName:version` under our job name, for example you can use `image: node:lts` to use an image with node and npm already installed, the lts stands for long term support.