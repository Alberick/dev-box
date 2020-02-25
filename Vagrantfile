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
    config.vm.synced_folder "../shared_folder", "/home/vagrant/shared_folder"
    # VAGRANT SYNC FOLDERS

    # PUBLIC NETWORK
    config.vm.network "private_network", ip: "192.168.2.10"
    # PUBLIC NETWORK

    # FORWARDED PORTS
    for i in 0..5
      config.vm.network "forwarded_port", guest: (8000 + i), host: (8000 + i)
    end

    config.vm.network "forwarded_port", guest: 1433, host: 1433
    config.vm.network "forwarded_port", guest: 5432, host: 5432
    config.vm.network "forwarded_port", guest: 8080, host: 8080
    # FORWARDED PORTS
    
    if Vagrant.has_plugin?("vagrant-vbguest")
	    config.vbguest.auto_update = false  
    end

    # BOX CUSTOMIZATION
    config.vm.provider "virtualbox" do |vb|
        vb.name = 'dev-box'
        vb.cpus = 4
        vb.customize ["modifyvm", :id, "--memory", "4096"]
        vb.linked_clone = true
    end
    # BOX CUSTOMIZATION

    # ANSIBLE-LOCAL PROVISIONING
    config.vm.provision 'ansible_local' do |ansible|
        ansible.playbook = 'provisioning/playbook.yml'
        ansible.install_mode = "default"
    end
    # ANSIBLE-LOCAL PROVISIONING
end
