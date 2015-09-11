# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
VM_MEMORY_SIZE = ENV['PT_VM_MEMORY'] || 2048

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_url = "https://atlas.hashicorp.com/ubuntu/trusty64"

  config.vm.host_name = "dev"
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :forwarded_port, guest: 3333, host: 3333
  config.vm.network :forwarded_port, guest: 4200, host: 4200
  config.vm.network :forwarded_port, guest: 9292, host: 9292
  config.vm.network :forwarded_port, guest: 49152, host: 49152
  config.vm.network :private_network, ip: "192.168.33.10"

  config.ssh.forward_agent = true

  config.vm.synced_folder "./apps", "/home/vagrant/apps", type: 'nfs'

  config.vbguest.auto_update = true
  config.berkshelf.enabled = true
  config.berkshelf.berksfile_path = "chef/Berksfile"

  config.vm.provider :virtualbox do |vb|
    vb.customize ['modifyvm', :id, '--memory', VM_MEMORY_SIZE.to_i]
  end

  config.vm.provision :chef_solo do |chef|
    chef.roles_path = "chef/roles"
    chef.data_bags_path = "chef/data_bags"
    chef.add_role "server"
    chef.add_role "rails-app"
    chef.add_role "mongo-server"
    chef.add_role "mysql-server"
    chef.add_role "node-js"
  end
end
