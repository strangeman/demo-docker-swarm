# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/8"
  config.vm.box_check_update = false
  config.vm.synced_folder './app', '/vagrant'
  
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
  end

  N = 3
  (1..N).each do |node_id|
    config.vm.define "node#{node_id}" do |node|
      node.vm.hostname = "node#{node_id}"
      node.vm.network "private_network", ip: "192.168.56.#{20+node_id}"
      if node_id == N
        node.vm.provision :ansible do |ansible|
          # Disable default limit to connect to all the machines
          ansible.limit = "all"
          ansible.playbook = "ansible/playbook.yml"
        end
      end
    end
  end
end
