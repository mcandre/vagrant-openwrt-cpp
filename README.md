# vagrant-openwrt-cpp: a Vagrant box for building C/C++ binaries for uClibC/Linux (OpenWrt)

# VAGRANT CLOUD

https://app.vagrantup.com/mcandre/boxes/vagrant-openwrt-cpp

# EXAMPLE

```console
$ cd amd64/test
$ vagrant up
$ vagrant ssh -c "cd /vagrant && g++ -o hello hello.cpp && ./hello"
Hello World!
```

# RUNTIME REQUIREMENTS

* [Vagrant](https://www.vagrantup.com)
* The [VirtualBox](https://www.virtualbox.org) hypervisor provider

## Synced folders note

This box requires an additional explicit chown to fix guest file permissions:

```console
$ vagrant ssh -c "sudo find /vagrant -exec chown vagrant:vagrant {} +"
```

## Recommended

* [vagrant-rsync-back](https://github.com/smerrill/vagrant-rsync-back) assists in copying artifacts from the guest to the host

# BUILDTIME REQUIREMENTS

* [Vagrant](https://www.vagrantup.com)
* The [VirtualBox](https://www.virtualbox.org) hypervisor provider
* [make](https://www.gnu.org/software/make/)

# EXPORT

```console
$ sh -c "cd amd64 && make vagrant-openwrt-cpp-amd64.box"
$ sh -c "cd i386 && make vagrant-openwrt-cpp-i386.box"
```
