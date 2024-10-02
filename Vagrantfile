# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  
  config.vm.box = "hashicorp/bionic64"
  config.vm.box_check_update = false

  # Config network for VM1
  config.vm.define :vm1 do |vm1|
    vm1.vm.network :private_network, ip: "192.168.33.10"
    vm1.vm.synced_folder "./", "/vagrant_data"
  end

  # Configuring VM2 for the application
  config.vm.define :vm2 do |vm2|
    vm2.vm.network :private_network, ip: "192.168.33.11"
    vm2.vm.network "forwarded_port", guest: 5000, host: 5000
  end

  # Configure provider
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "512"
  end

end
