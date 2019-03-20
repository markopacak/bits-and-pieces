# Wisdom coming straight from First Father Internet

A collection of code snippets / commands I often use, all enclosed in this project. This repo is often updated 

**I always cite original authors!**

----

##### 1. Install `VirtualBox Guest Additions` in a `Debian` host

Taken from [this answer](https://unix.stackexchange.com/a/286937/273498) by [Stephen Kitt](https://unix.stackexchange.com/users/86440/stephen-kitt).

From within your host run:

```bash
echo deb http://ftp.debian.org/debian stretch-backports main contrib > /etc/apt/sources.list.d/stretch-backports.list
apt update
apt install virtualbox-guest-dkms virtualbox-guest-x11 linux-headers-$(uname -r)
```

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

Taken from [this article](https://medium.freecodecamp.org/the-easy-way-to-set-up-docker-on-a-raspberry-pi-7d24ced073ef) by [Ryan Gordon](https://medium.freecodecamp.org/@ryangordon210):

```bash
curl -fsSL get.docker.com -o get-docker.sh && sh get-docker.sh
```

*Tags: `raspberry` `raspberry-pi` `raspbian` `linux` `docker`*

----

##### 4. Save the `git` password for your repo

Taken from [this answer](https://stackoverflow.com/a/35942890/8524301) by StackOverflow user [Neetika](https://stackoverflow.com/users/5574889/neetika):

```bash
git config credential.helper store
```

At the next `pull`, you'll be asked the password and it will be stored afterwards.

*Tags: `git`*

----

##### 5. Have variadic template arguments be all of the same type

Taken from Jonathan Boccara's [fluencpp.com blog post](https://www.fluentcpp.com/2019/01/25/variadic-number-function-parameters-type/):

```c++
template <typename ... Ts>
using all_strings = typename std::enable_if<std::conjunction<std::is_convertible<Ts, std::string>...>::value>::type;

template <typename ... Ts, typename = all_strings<Ts...>>
void function(Ts const& ... ts)
{
    // ...
}

```
*Tags: `c++` `c++17` `variadic-templates`*

----

##### 6. Add headers to a CURL request

Taken from [this answer](https://stackoverflow.com/a/356714/8524301) by StackOverflow user [Tader](https://stackoverflow.com/users/30700/tader):

```bash
curl --header "X-mysecrettoken: blablablabla" 127.0.0.1
```
*Tags: `curl` `http` `linux`*

----

##### 7. mkdir: create nested folders

Taken from [this answer](https://unix.stackexchange.com/a/84192/273498) by StackOverflow user [Braiam](https://unix.stackexchange.com/users/41104/braiam):

```bash
mkdir -p /var/www/mysite/static
```

All the parent folders of `static` will be created if they don't exist.

*Tags: `mkdir` `file-system` `linux`*

----

##### 8. Stop last running Docker container without having to `docker ps -a` first

Taken from [this answer](https://stackoverflow.com/a/34899613/8524301) by StackOverflow user [Koekiebox](https://stackoverflow.com/users/158288/koekiebox):

```bash
docker stop $(docker ps -q --filter ancestor=<image-name>)
```


*Tags: `docker` `linux`*

----

##### 9. Have variadic template arguments be all of the same type (using a dynamic type this time)

Extending [bit number 9](https://github.com/markopacak/bits-and-pieces/blob/master/README.md#L65). 

```c++
template <class _Type, typename ... Ts>
using all_of_type = typename std::enable_if <std::conjunction <std::is_convertible <Ts, _Type> ...>::value>::type;

template <typename _Type, typename ... Ts, typename = all_of_type <_Type, Ts ...>>
void function (Ts const & ... ts)
{
	// ...
}

// ... e.g. in main.cpp
function <std::string>("Hello", ",", "world", "!");	


```
*Tags: `c++` `c++17` `variadic-templates`*

----
