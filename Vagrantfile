# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.box_url = "https://atlas.hashicorp.com/ubuntu/boxes/xenial64"
  config.vm.box_check_update = true
  config.vm.network "private_network", ip: "10.10.10.30"
  config.vm.synced_folder "apps", "/var/apps", type: "rsync", rsync__exclude: [".vagrant/", ".git/", "node_modules"]

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.cpus = 2
    vb.memory = "2048"
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
  end
end
