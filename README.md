# x86_64-os-kernel
x86_64 operating system kernel that is Multiboot2 compliant.

## Prerequisites
- [Docker](https://www.docker.com/) for creating build-env
- [Qemu](https://www.qemu.org/) for emulating the OS

## Setup
Build an image for the build-env:

`docker build buildenv -t myos-buildenv`

## Build
Enter build environment:
 - Linux/MacOS: `docker run --rm -it -v "$pwd":/root/env myos-buildenv`
 - Windows: `docker run --rm -it -v "%cd%":/root/env myos-buildenv`
 
 Build for x86_64:
 - `make build-x86_64`
 
 To leave the build environment, enter `exit`.
 
 ## Emulate
 
 `qemu-system-x86_64 -cdrom dist/x86_64/kernel.iso`
