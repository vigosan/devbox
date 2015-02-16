# devbox

## Introduction

This project automates the setup of a development environment for Ruby on Rails, Node.js and Ember.js

## Requirements

* [VirtualBox](https://www.virtualbox.org)
* [Vagrant](http://vagrantup.com)

## How To Build The Virtual Machine

```zsh
$ git clone git@github.com:vigosan/rails-dev-box.git
$ cd devbox
$ vagrant plugin install vagrant-berkshelf
$ vagrant plugin install vagrant-vbguest
$ vagrant up
$ vagrant provision
$ vagrant ssh
Linux dev 3.2.0-4-amd64 #1 SMP Debian 3.2.46-1 x86_64
...
vagrant@dev:~$
```

## Roles

- server: Install common server packages
- rails-app: Install Rbenv and Rails ecosystem
- memcached-server: Install Memcached server
- mongo-server: Installs Mongo DB server
- nginx-server: Installs Nginx server
- redis-cache-server: Installs Redis cache server

## What's In The Box

* Git
* Ruby 2.2.0 via rbenv
* Bundler
* SQLite3, MySQL, and Postgres
* Memcached
* Redis
* PhantomJS
