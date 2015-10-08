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

- memcached-server: Install Memcached server
- mongo-server: Installs Mongo DB server
- mysql-server: Installs MySQL server
- nginx-server: Installs Nginx server
- node-js: Install Rbenv and Rails ecosystem
- rails-app: Install Rbenv and Rails ecosystem
- redis-cache-server: Installs Redis cache server
- server: Install common server packages

## What's In The Box

* Git
* Ruby 2.2.3 via rbenv
* Bundler
* SQLite3, MySQL, and Postgres
* Memcached
* Redis
* PhantomJS
* Node.js
