# bits-and-pieces
A collection of code snippets / commands I often use, all enclosed in this project. This repo is often updated 

**I always cite original authors!**

----

##### 1. Install `VirtualBox Guest Additions` in `Debian`

Taken from [this answer](https://unix.stackexchange.com/a/286937/273498) by [Stephen Kitt](https://unix.stackexchange.com/users/86440/stephen-kitt):

    echo deb http://ftp.debian.org/debian stretch-backports main contrib > /etc/apt/sources.list.d/stretch-backports.list
    apt update
    apt install virtualbox-guest-dkms virtualbox-guest-x11 linux-headers-$(uname -r)
    
That's it. Just restart your VM. 

----
    
##### 2. Jump to the EOF when using `nano`

Taken from [my answer](https://unix.stackexchange.com/a/420892/273498) on [Unix StackExchange](https://unix.stackexchange.com/users/273498/marko-pacak):

Open the file with `nano file.txt`.
Now type `Ctrl + _` and then `Ctrl + V`

----

##### 2. Install and set-up docker on `Raspbian`

Taken from [medium.freecodecamp.org](https://medium.freecodecamp.org/the-easy-way-to-set-up-docker-on-a-raspberry-pi-7d24ced073ef):

    curl -fsSL get.docker.com -o get-docker.sh && sh get-docker.sh

----
