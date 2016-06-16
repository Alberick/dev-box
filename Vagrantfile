# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.box = "ubuntu/trusty64"

    config.vm.synced_folder "./provisioning", "/home/vagrant/provisioning"
    config.vm.synced_folder "../shared_folder", "/home/vagrant/shared_folder"
    
    for i in 0..5
        config.vm.network "forwarded_port", guest: (3000 + i), host: (3000 + i)
        config.vm.network "forwarded_port", guest: (4000 + i), host: (4000 + i)
        config.vm.network "forwarded_port", guest: (8000 + i), host: (8000 + i)
        config.vm.network "forwarded_port", guest: (8100 + i), host: (8100 + i)
    end

    config.vm.network "forwarded_port", guest: 5432, host: 5432
    config.vm.network "forwarded_port", guest: 5555, host: 5555
    config.vm.network "forwarded_port", guest: 5672, host: 5672
    config.vm.network "forwarded_port", guest: 8111, host: 8111
    config.vm.network "forwarded_port", guest: 9000, host: 9000
    config.vm.network "forwarded_port", guest: 15672, host: 15672
    config.vm.network "forwarded_port", guest: 35729, host: 35729

    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2048"]
    end

    config.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'provisioning/playbook.yml'
    end

end
