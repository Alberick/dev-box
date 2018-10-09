# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    # BOX
    config.vm.box = "ubuntu/bionic64"
    config.disksize.size = "50GB"
    # BOX

    config.ssh.forward_agent = true

    # VAGRANT SYNC FOLDERS
    config.vm.synced_folder "./provisioning", "/home/vagrant/provisioning"
    config.vm.synced_folder "../shared_folder", "/home/vagrant/shared_folder"
    # VAGRANT SYNC FOLDERS

    # PUBLIC NETWORK
    config.vm.network "public_network"
    # PUBLIC NETWORK

    # FORWARDED PORTS
    for i in 0..5
	    config.vm.network "forwarded_port", guest: (8000 + i), host: (8000 + i)
    end

    config.vm.network "forwarded_port", guest: 1433, host: 1433 
    config.vm.network "forwarded_port", guest: 2376, host: 2376 
    config.vm.network "forwarded_port", guest: 8080, host: 8080 
    config.vm.network "forwarded_port", guest: 3306, host: 3306 
    config.vm.network "forwarded_port", guest: 5432, host: 5432 
    config.vm.network "forwarded_port", guest: 53703, host: 53703 
    # FORWARDED PORTS

    # BOX CUSTOMIZATION
    config.vm.provider :virtualbox do |vb|
        vb.name = 'dev-box'
        vb.cpus = 2
        vb.customize ["modifyvm", :id, "--memory", "4096"]
    end
    # BOX CUSTOMIZATION

    # ANSIBLE-LOCAL PROVISIONING
    config.vm.provision 'ansible_local' do |ansible|
        ansible.playbook = 'provisioning/playbook.yml'
    end
    # ANSIBLE-LOCAL PROVISIONING
end
