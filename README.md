vagrant-taverna
===============

Vagrant launcher for Taverna (http://www.taverna.org.uk/)

Requirements
------------
* Download and install VirtualBox (https://www.virtualbox.org/)
* Download and install Vagrant (http://www.vagrantup.com/)
* Download and install Fabric (http://fabfile.org/) [optional]

Note - the easiest way to install Fabric is through pip (or easy_install):

```
 pip install fabric
```

Installation
------------
```
 git clone https://github.com/Smithsonian/vagrant-taverna.git
 cd vagrant-taverna
 vagrant up
```

Point your browser at http://localhost:8080/ after starting up the taverna server.  You can do this via fabric (see below), for convenience, or you can do it manually like so:
```
 vagrant ssh -c sudo /etc/init.d/tomcat6 start
```
