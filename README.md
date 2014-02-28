# Cozy Manager

Cozy Manager is a tool for Cozy Web Application developers. It makes easy to
start with building an application for the Cozy Cloud Platform.

    npm install cozy -g
    cozy new myapp --github myaccount
    cd myapp

Add some features, then:

    cozy deploy
    

# Virtual Machine

Because Cozy Stack requires quite a few things to be installed, it's a good idea to not
put it all on your personal machine.

In order to achieve this, we used Valgrind to prepare et pre-configure a working 
development for you: quickly and painlessly.

Once installed, the virtual machine will be working in background and you'll get all
necessary ports forwared from localhost.

That means, that after a cozy dev:start command, if you want to go the the cozy home in 
your VM, you simply go to

	http://127.0.0.1:9104/



# Managing your virtual machine

The Cozy Manager helps you to manage a virtual machine through Vagrant.

	cozy dev:init


Initialises the VM in VirtualBox, configures it for you.

	cozy dev:start


Starts the VM

	cozy dev:stop


Stops (freezes the machine, keeps the memory on disk)

	cozy dev:stop --halt


Stops properly (shuts down) the machine

	cozy dev:destroy


Destroys the machine permanently.


More information about CozyCloud and virtual machines in [the documentation](https://github.com/mycozycloud/cozy-setup/wiki/Setup-cozy-cloud-development-environment-via-a-virtual-machine).


# What's in the box ?

From the Vagrant file:

	config.vm.network :forwarded_port, guest: 9101, host: 9101 # Cozy Data System
	config.vm.network :forwarded_port, guest: 9102, host: 9102 # Cozy Data Indexer
	config.vm.network :forwarded_port, guest: 9104, host: 9104 # Cozy Proxy
	config.vm.network :forwarded_port, guest: 9105, host: 9105 # Realtime socket
	config.vm.network :forwarded_port, guest: 5984, host: 5984 # CouchDB
	config.vm.network :forwarded_port, guest: 9099, host: 9099 # Cozy Log Reader


So, home is available here:

	http://127.0.0.1:9104/


And CouchDB's Fusion:

	http://127.0.0.1:5984/_utils/


# About Cozy

Cozy is a private pesronal cloud solution that allows you to host all your
personnal application in a single place you control.
This way, you can manage your data from anywhere while protecting your privacy.

https://cozycloud.cc

# Cozy on IRC

Feel free to check out our IRC channel (#cozycloud on irc.freenode.org) if you have any technical issues/inquiries or simply to speak about Cozy cloud in general.
