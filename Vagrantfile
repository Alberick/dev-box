# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define 'devserver' do |devserver|
    devserver.vm.box = "ubuntu/trusty64"

    devserver.vm.network "private_network", ip: "192.168.33.10"

    devserver.vm.synced_folder "./provisioning", "/home/vagrant/provisioning"

    devserver.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "1024"]
    end
  end
end