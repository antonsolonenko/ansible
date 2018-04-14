# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  config.vm.box_version = "9.2.0"
  config.ssh.insert_key = false

  config.vm.define "wpserver" do |t|
  end

  config.vm.provider "virtualbox" do |v|
    v.name = "wpserver"
    v.memory = 512
    v.cpus = 2
  end

  config.vm.hostname = "wpserver"
  config.vm.network "private_network", ip: "192.168.13.2"
  config.vm.network "private_network", ip: "192.168.13.3"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.inventory_path = "provisioning/inventory"
    ansible.sudo = true
  end

end
