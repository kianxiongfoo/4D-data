# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  # load up the box for centos 6.6
  # This will take long to download the os, hold up there
  # Or go for a coffee
  config.vm.box = "ubuntu/trusty64"

  # pass a private network IP
  config.vm.network "private_network", ip:"172.28.128.5"
  #config.vm.network "forwarded_port", guest: 80, host: 8080
  #config.vm.network "forwarded_port", guest: 3306, host: 3307
  #config.vm.network "public_network", type:"dhcp"
  
  # your host name for the application
  config.vm.hostname = "scrapy.foo.com"
  

  config.vm.provider :virtualbox do |vb|
	vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
	vb.customize ["modifyvm", :id, "--ioapic", "on"]
	#vb.customize ["modifyvm", :id, "--nictype1", "on"]
	#vb.customize ["modifyvm", :id, "--cpuexecutioncap", "90"]
	vb.customize ["modifyvm", :id, "--memory", "1536"]
	vb.customize ["modifyvm", :id, "--cpus", 2]
  end

  #Vagrant.configure('2') do |config|
  # config.winnfsd.uid = 1
  # config.winnfsd.gid = 1
  #end

  # Call our deployment shell script
  #config.vm.provision "shell", path: "shell_provisioners/build.sh"
  #config.vm.provision "shell", path: "shell_provisioners/go.sh"


  # Sync the folders
  config.vm.synced_folder "src", "/var/www/sync" , type: "nfs"
  #config.vm.synced_folder "../siva", "/var/www/siva" , :mount_options => ["dmode=777", "fmode=666"]
  #config.vm.synced_folder "../papi", "/var/www/papi" , :mount_options => ["dmode=777", "fmode=666"]
  #config.vm.synced_folder "../sivarc", "/var/www/sivarc" , :mount_options => ["dmode=777", "fmode=666"]
  #config.vm.synced_folder "html", "/var/www/go/src"
end
