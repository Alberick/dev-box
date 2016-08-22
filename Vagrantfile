# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    # box 
    config.vm.box = "ubuntu/trusty64"
    # box 

    # sync folders
    config.vm.synced_folder "./provisioning", "/home/vagrant/provisioning"
    config.vm.synced_folder "../shared_folder", "/home/vagrant/shared_folder"
    # sync folders

    # forworded ports
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
    # forworded ports


    # SYNC FOLDERS
    # Tixif
    config.vm.synced_folder "~/Documents/Tixif/django-tixif", "/home/vagrant/Tixif/django-tixif"
    config.vm.synced_folder "~/documents/Tixif/scp-api", "/home/vagrant/Tixif/scp-api"
    config.vm.synced_folder "~/documents/Tixif/scp-web", "/home/vagrant/Tixif/scp-web"
    config.vm.synced_folder "~/documents/Tixif/scp-mobile", "/home/vagrant/Tixif/scp-mobile"
    # Tixif

    # Nexus
    # javascript
    config.vm.synced_folder "~/Documents/Nexus/javaScript/ionicJs/ionic_in_action", "/home/vagrant/Nexus/javaScript/ionicJs/ionic_in_action"
    config.vm.synced_folder "~/Documents/Nexus/javaScript/ionicJs/Ionic_2ndTutorial", "/home/vagrant/Nexus/javaScript/ionicJs/Ionic_2ndTutorial"
    config.vm.synced_folder "~/Documents/Nexus/javaScript/ionicJs/ionic_todo", "/home/vagrant/Nexus/javaScript/ionicJs/ionic_todo"

    # Python
    config.vm.synced_folder "~/Documents/Nexus/python/django/part3_realpython/", "/home/vagrant/Nexus/python/django/part3_realpython/"
    # Nexus
    # SYNC FOLDERS

    # box customization
    config.vm.provider :virtualbox do |vb|
        vb.name = 'dev-box'
        vb.cpus = 2
        vb.customize ["modifyvm", :id, "--memory", "3072"]
    end
    # box customization

    # ansible-local provisioning
    config.vm.provision 'ansible_local' do |ansible|
        ansible.playbook = 'provisioning/playbook.yml'
    end
    # ansible-local provisioning
end
