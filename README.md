#Hanad
# Instruction to using virtualbox

This will be steps that the developer can follow and go through to use this environment

## Install VirtualBox

To install virtualbox you'll need to select the correct operating system you would want. The latest virtualbox platform packages is the 5.2.18 https://www.virtualbox.org/wiki/Downloads

## Install Vagrant



To install vagrant you need to select the right operating system that you would like to install it on. https://www.vagrantup.com/downloads.html

Once you've completed installation successfully, to verify completion on Terminal enter

`` Vagrant``

and this will list the commands you can enter with vagrant

## Setting up a virtual environment through the terminal on a macOS

The first command would be

``Vagrant init ubuntu/xenial64 ``

This will initialise vagrant with the version ubuntu xenial64.


Once you initialise vagrant open up atom. and type in the following command as this will allow the user to chose which version of linux they would run on their virtual machine

``Vagrant.configure("2") do |config| ``
``config.vm.box = "ubuntu/xenial64"``        ``config.vm.network("private_network", ip: "192.168.10.100")``
``config.hostsupdater.aliases = ["development.local"] end ``

The next command would then be typed up in the terminal

``Vagrant up``

This command would spin up the server for the virtualbox.

The next command that would need to be run is

``vagrant plugin install vagrant-hostsupdater ``

The next command that would be run is

``Vagrant ssh ``

This allows the user into the secure shell of the virtual machine's terminal.

This would update all the latest package inside the shell.

``sudo apt-get update``

After the virtual machine has successfully installed all the plugins it needs. The next step is to install Nginx and this can be done with the following command inside the vagrant ssh.

``Sudo apt-get install nginx ``

Nginx is a web server which can also be used as a reverse proxy.

Nginx is a web server that will run on the virtual machine allowing you to host the web application.

To see if the server is running correctly you would type in http://development.local/ in the url of the web browser.

# Sparta Node Sample App

## Description

This app is intended for use with the Sparta Global Devops Stream as a sample app. You can clone the repo and use it as is but no changes will be accepted on this branch.

To use the repo within your course you should fork it.

The app is a node app with three pages.

### Homepage

``localhost:3000``

Displays a simple homepage displaying a Sparta logo and message. This page should return a 200 response.

### Blog

``localhost:3000/posts``

This page displays a logo and 100 randomly generated blog posts. The posts are generated during the seeding step.

This page and the seeding is only accessible when a database is available and the DB_HOST environment variable has been set with it's location.

### A fibonacci number generator

``localhost:3000/fibonacci/{index}``

This page has be implemented poorly on purpose to produce a slow running function. This can be used for performance testing and crash recovery testing.

The higher the fibonacci number requested the longer the request will take. A very large number can crash or block the process.


### Hackable code

``localhost:3000/hack/{code}``

There is a commented route that opens a serious security vulnerability. This should only be enabled when looking at user security and then disabled immediately afterwards

## Usage

Clone the app

```
npm install
npm start
```

You can then access the app on port 3000 at one of the urls given above.

## Tests

There is a basic test framework available that uses the Mocha/Chai framework

```
npm test
```

The test for posts will fail ( as expected ) if the database has not been correctly setup.

testing jenkins.
