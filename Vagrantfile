# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.box_url = "https://atlas.hashicorp.com/ubuntu/boxes/xenial64"
  config.vm.box_check_update = true
  config.vm.network "private_network", ip: "10.10.10.30"
  config.vm.synced_folder "apps", "/var/apps",
    type: "rsync",
    rsync__args: ['--verbose', '--archive', '-z', '--copy-links'],
    rsync__exclude: ['.DS_Store', '.git/', 'deps/', '_build/', 'node_modules/', 'priv/static/']

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.cpus = 2
    vb.memory = "2048"
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible_provision/vagrant.yml"
    ansible.inventory_path = "ansible_provision/inventories/vagrant"
    ansible.limit = 'vagrant'
    ansible.extra_vars = { ansible_ssh_user: 'ubuntu' }
  end
end
