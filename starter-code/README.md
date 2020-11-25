# Provisioning with Vagrant

## Core Sections of Provision
There are some actions that are core to provisioning.
- sending in files

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