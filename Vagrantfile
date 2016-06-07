# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.define "dev" do |dev|

        dev.vm.box = "ubuntu/trusty64"

        dev.vm.synced_folder "./provisioning", "/home/vagrant/provisioning"
        dev.vm.synced_folder "../shared_folder", "/home/vagrant/shared_folder"

        dev.vm.provider :virtualbox do |vb|
          vb.customize ["modifyvm", :id, "--memory", "1024"]
        end

        dev.vm.provision 'ansible' do |ansible|
          ansible.playbook = 'provisioning/playbook.yml'
        end

    end

end
