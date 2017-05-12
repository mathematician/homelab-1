# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "packer/build/ubuntu-16.04.2-server-amd64-docker.box"
  config.vm.provision "shell", path: "vagrant_provision.sh"
  config.vm.network "public_network"
  #config.vm.network :forwarded_port, guest: 22, host: 2222, id: 'ssh'
  #config.vm.network :forwarded_port, guest: 80, host: 8080, id: 'http'
  #config.vm.network :forwarded_port, guest: 443, host: 8443, id: 'https'
  #config.vm.network :forwarded_port, guest: 67, host: 67, id: 'dhcp', protocol: 'udp'
  config.vm.synced_folder ".", "/vagrant"

  config.vm.provider "virtualbox" do |vb| 
     # Use VBoxManage to customize the VM. For example to change name, memory and DNS resolution:
     vb.name = "devlab"
     vb.customize ["modifyvm", :id, "--memory", "768"]
	   vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end
end
