# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  # specify the box to use 
  config.vm.box = "geerlingguy/ubuntu2004"

  # Network configuration
  config.vm.network "private_network", type: "dhcp"

  # Provider configuration
  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "2048"
  end

  # Provisioning with Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
  end

  # Sync folders
  config.vm.synced_folder ".", "/vagrant"

  
end
