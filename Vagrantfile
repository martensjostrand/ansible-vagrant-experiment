# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"
BOX = "hashicorp/precise64"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "loadbalancer0" do |loadbalancer0|
    loadbalancer0.vm.box = BOX
    loadbalancer0.vm.network "private_network", ip: "192.168.100.100"
  end

  config.vm.define "loadbalancer1" do |loadbalancer1|
    loadbalancer1.vm.box = BOX
    loadbalancer1.vm.network "private_network", ip: "192.168.100.101"
  end

  config.vm.define "webbfront0" do |webbfront0|
    webbfront0.vm.box = BOX
    webbfront0.vm.network "private_network", ip: "192.168.100.110"
  end

  config.vm.define "webbfront1" do |webbfront1|
    webbfront1.vm.box = BOX
    webbfront1.vm.network "private_network", ip: "192.168.100.111"

    webbfront1.vm.provision "ansible" do |ansible|
      ansible.sudo = true
      ansible.limit = 'all'
      ansible.inventory_path = "ansible/vagrant_inventory"
      ansible.host_key_checking = false
      ansible.playbook = "ansible/cluster.yml"
    end

  end

end
