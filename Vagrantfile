# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.box_check_update = false
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "private_network", ip: "192.168.56.10"
  config.vm.synced_folder "./dc/", "/home/vagrant/dc", type: "rsync"
   config.vm.provider "virtualbox" do |vb|
   vb.memory = "1024"
   end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "dz.yml"
  end
end
