# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  # config.vm.box_check_update = false

  config.vm.network "forwarded_port", guest: 80, host: 8989

  config.vm.network "forwarded_port", guest: 80,  host: 8989, auto_correct: true
  config.vm.network "forwarded_port", guest: 3306, host: 3306, auto_correct: true

  #Remeber to change the host port to avoid clashes with different boxes
  config.vm.network "forwarded_port", guest: 22, host: 2223, id: "ssh"
  
  #Same here, increment ip and change it in etc/hosts on host machine
  config.vm.network "private_network", ip: "192.168.33.12"
  config.vm.network "public_network"

  config.vm.synced_folder "www/", "/var/www/html"

  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  config.vm.provision "shell", path: "provision.sh"

end
