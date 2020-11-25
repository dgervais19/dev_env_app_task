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
* A bash script can install packages, alter files, do actions in our Linux servers when we do "vagrant up"
* This enables us to set up our VM in a disired state essenetially automating the pocess of creating a VM with the specific packages installed.



## Given new project to create an Environment
**When given a new project, you want to ask a few questions to help you get going. For example:**
* What language is it in?
* Is there a framework to install? (rails, flask, django, wordpress)
* Any specific packages? if so is there a list? (Gemfile, requirements.txt)
* Any tests?


## gem and bundler VS PIP and packages
Gems are packages in ruby pr dependencies

bundler is ruby's package manager

Gemfile keeps a list of dependencies to be installed

To install gems from the Gemfile, you run:
    - `bundle install`

* Let's install bundler

## Ruby's testing framework is rspec
rspec needs to be installed

## JS package manager is npm (node package manager)
npm packages

## Ubuntu package manager
apt-get

## Installing test
* to to folder with Gemfile
* run `bundle`

## Running tests
* rake spec