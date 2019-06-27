# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "/Users/Alex/Desktop/EVE-Debian8.box"
  config.vm.define :common do |t|
  end

  # Create a private network, which allows host-only access to the machine
  config.vm.network "private_network", ip: "192.168.1.10"

  # Provider-specific configuration
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = false
    # Set the name of the vm created in VB
    vb.name = "common"
    # Customize the amount of memory and cpu on the VM:
    vb.memory = 1024
    vb.cpus = 1
  end

end
