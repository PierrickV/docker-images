# John The Ripper

## About the project
John the Ripper jumbo - advanced offline password cracker, which supports hundreds of hash and cipher types, and runs on many operating systems, CPUs, GPUs, and even some FPGAs 
https://github.com/openwall/john

## About this image

This Docker image allow you to run the latest version of John The Ripper (known as bleeding jumbo).

## Build the image locally
```bash
sudo docker build -t john .
sudo docker run -ti -v $(pwd):/data john hashs.txt
```

## Pull the image from Docker Hub

```bash
sudo docker run -ti -v $(pwd):/data pierrickv/john hashs.txt
```
