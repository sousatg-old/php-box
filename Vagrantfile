# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.network "private_network", ip: "192.168.33.10"

  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provision "ansible" do | ansible |
    ansible.inventory_path = "hosts"
    ansible.playbook = "ansible/deploy.yml"
    ansible.verbose = "-vv"
    ansible.become = true
    ansible.limit = "all"
  end
end
