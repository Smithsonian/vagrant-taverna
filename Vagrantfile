# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  #config.vm.box = "precise64"
  config.vm.box = "centos65x64"

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  # config.vm.box_url = "http://domain.com/path/to/above.box"
  config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.1/centos65-x86_64-20131205.box"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network :forwarded_port, guest: 8080, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network :private_network, ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network :public_network

  config.vm.provision :shell, :inline => "sudo yum -y update"
  config.vm.provision :shell, :inline => "sudo yum -y upgrade"
  config.vm.provision :shell, :inline => "sudo yum -y install puppet"
  config.vm.provision :shell, :inline => "sudo yum install java-1.6.0-openjdk.x86_64 -y"
  config.vm.provision :shell, :inline => "sudo yum -y install wget mlocate"
  config.vm.provision :shell, :inline => "sudo yum -y install tomcat6-webapps"
  config.vm.provision :shell, :inline => "sudo wget -P /var/lib/tomcat6/webapps/ https://launchpad.net/taverna-server/2.x/2.4.4/+download/server-webapp-2.4.4.war"
  config.vm.provision :shell, :inline => "sudo mv /var/lib/tomcat6/webapps/server-webapp-2.4.4.war /var/lib/tomcat6/webapps/taverna.war"
  config.vm.provision :shell, :inline => "sudo /etc/init.d/tomcat6 start"
  config.vm.provision :shell, :inline => "sudo /etc/init.d/tomcat6 stop"
  config.vm.provision :shell, :inline => "sudo cp /vagrant/conf/web.xml /var/lib/tomcat6/webapps/taverna/WEB-INF/web.xml"
  config.vm.provision :shell, :inline => "sudo /etc/init.d/tomcat6 start"

end
