# How to make vagrant box

## Prerequisites
* [Chef](http://www.opscode.com/chef/ "Link to Chef")
* [BERKSHELF](http://berkshelf.com/ "Link to BERKSHELF")
* [Packer](http://www.packer.io/ "Link to Packer")

I used the following versions:

```
$ knife -v
Chef: 11.6.0
$ berks -v | head -1
Berkshelf (2.0.10)
$ packer -v
Packer v0.3.7
```

## CentOS 6.4 x86_64
```
$ git clone https://github.com/keisatou/my_packer_templates.git
$ cd my_packer_templates/

$ berks install --berksfile=centos6.4/chef/Berksfile --path=centos6.4/chef/vendor-cookbooks

$ packer build --only=virtualbox centos6.4/packer/centos_6.4_x86_64.json

$ ls centos6.4/vagrant-box
CentOS-6.4-x86_64-minimal.box
```
