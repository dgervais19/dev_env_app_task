# Provisioning with Vagrant

## Core Sections of Provision
There are some actions that are core to provisioning.
- sending in files

* The following is our `Vagrantfile`:
```Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.network "private_network", ip: "192.168.10.100"
  config.hostsupdater.aliases = ["development.local"]

  config.vm.synced_folder "app", "/app"
end
```
* Here we will be providing our VM's with instructions, files, variables etc.

* It ensures that the computer loads in a certain state (specified in provision.sh)

### Core Sections of Provisioning

1. Tool agnostic
2. Language agnostic

Provisioning....
    * Makes files availabke
    * Enables you to run commands/scripts
    * Injects environment variables (global variables)

### Managing Running Servers in Linux
* sudo systemctl <action> <server>

### Running a Bash Script
* A bash script can install packages, alter files, do actions in our Linux servers when we do `vagrant up`
* This enables us to set up our VM in a disired state essenetially automating the pocess of creating a VM with the specific packages installed.

1. Create a `provision.sh` file with the following commands.
```#!/bin/bash

sudo apt-get update
sudo apt-get install nginx -y
```

2. Now include the **provision.sh** file in the **Vagrantfile**. This is by adding another config line.
```Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.network "private_network", ip: "192.168.10.100"
  # config.hostsupdater.aliases = ["development.local"]

  # Synce the app folder (not copying in. it's synching)

  # config.vm.synced_folder "path/origin/folder", "path/to/destination/folder"
  config.vm.synced_folder "app", "/app"

  # run the provision script making sure you're in the correct path
  config.vm.provision "shell", path: "environment/provision.sh"
end
```



### Given new project to create an Environment
**When given a new project, you want to ask a few questions to help you get going. For example:**
* What language is it in?
* Is there a framework to install? (rails, flask, django, wordpress)
* Any specific packages? if so is there a list? (Gemfile, requirements.txt)
* Any tests?

**In this case:**
* A framework to install? No. We only need the testing framework `rspec` (rake spec)
* Any specific packages? Yes. Within the environment folder we have a `Gemfile` which has dependencies
* Any tests? Yes. There are intergration tests to run outside of the machine using `rake spec`. There might also be unit tests to run within the machine for JS.


### Ruby: gem and bundler VS PIP and packages
* `gem` and ` bundler` in Ruby are equivalent to `pip` and `packages` in Python
* `bundler` is Ruby's package manager
* Ruby's testing framework is `rspec`. This needs to be installed
* Gemfiles keep lists of dependencies that need to be installed.
* In order to install gems from a `Gemfile`, do: `bundle install`


### Ruby testing
* Make sure you're in the folder with the gemfile
* Run `bundle` in the terminal to install the tests
* `rake spec` in order to run the tests

### AIMS:
* to run tests
* understand what it is im testing
* solve the failing tests

### WHAT I SHOULD KNOW:
* How to provision my VM with code
* instructions

## JS package manager is npm (node package manager)
npm packages

## Ubuntu package manager
apt-get
