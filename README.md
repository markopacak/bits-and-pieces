# Wisdom coming straight from father internet

A collection of code snippets / commands I often use, all enclosed in this project. This repo is often updated 

**I always cite original authors!**

----

##### 1. Install `VirtualBox Guest Additions` in `Debian`

Taken from [this answer](https://unix.stackexchange.com/a/286937/273498) by [Stephen Kitt](https://unix.stackexchange.com/users/86440/stephen-kitt):

    echo deb http://ftp.debian.org/debian stretch-backports main contrib > /etc/apt/sources.list.d/stretch-backports.list
    apt update
    apt install virtualbox-guest-dkms virtualbox-guest-x11 linux-headers-$(uname -r)
    
That's it. Just restart your VM. 

*Tags: `debian` `linux` `virtualbox` `vboxmanage`*

----
    
##### 2. Jump to the EOF when using `nano`

Taken from [my answer](https://unix.stackexchange.com/a/420892/273498) on [Unix StackExchange](https://unix.stackexchange.com/users/273498/marko-pacak):

Open the file with `nano file.txt`.
Now type `Ctrl + _` and then `Ctrl + V`


*Tags: `nano` `linux`*

----

##### 3. Install and set-up docker on `Raspbian`

Taken from [medium.freecodecamp.org](https://medium.freecodecamp.org/the-easy-way-to-set-up-docker-on-a-raspberry-pi-7d24ced073ef):

    curl -fsSL get.docker.com -o get-docker.sh && sh get-docker.sh

*Tags: `raspberry` `raspberry-pi` `raspbian` `linux` `docker`*

----

##### 4. Save the `git` password for your repo

Taken from [this answer](https://stackoverflow.com/a/35942890/8524301) by StackOverflow user [Neetika](https://stackoverflow.com/users/5574889/neetika):

    git config credential.helper store


At the next `pull`, you'll be asked the password and it will be stored afterwards.

*Tags: `git`*

----

##### 5. Have variadic template arguments be all of the same type

Taken from Jonathan Boccara's [fluencpp.com blog post](https://www.fluentcpp.com/2019/01/25/variadic-number-function-parameters-type/):

    template <typename ... Ts>
    using all_strings = typename std::enable_if<std::conjunction<std::is_convertible<Ts, std::string>...>::value>::type;

    template <typename ... Ts, typename = all_strings<Ts...>>
    void function(Ts const& ... ts)
    {
        // ...
    }

*Tags: `c++` `c++17` `variadic-templates`*
