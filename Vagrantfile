# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  #config.vm.box = "ajcarberry/ubuntu1804"
  config.vm.box = "ajcarberry/debian9"

  config.vm.define :packerDebian do |t|
  end

  # Create a private network, which allows host-only access to the machine
  config.vm.network "private_network", ip: "192.168.1.10"

  # Provider-specific configuration
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
    # Set the name of the vm created in VB
    vb.name = "packerDebian"
    # Customize the amount of memory and cpu on the VM:
    vb.memory = 2048
    vb.cpus = 1
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  # Enable provisioning with Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "test/test.yml"
  end
end
