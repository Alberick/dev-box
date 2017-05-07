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
    
    # public network
    config.vm.network "public_network", ip: "192.168.1.99"
    # public network
    
    # forworded ports
    for i in 0..5
	    config.vm.network "forwarded_port", guest: (8000 + i), host: (8000 + i)
    end

    config.vm.network "forwarded_port", guest: 8080, host: 8080 
    config.vm.network "forwarded_port", guest: 2376, host: 2376 
    config.vm.network "forwarded_port", guest: 5432, host: 5432 

    # forworded ports


    # SYNC FOLDERS
    # Ceroic
    config.vm.synced_folder "~/Documents/Ceroic/cyrious.com", "/home/vagrant/Ceroic/cyrious.com"
    # Ceroic

    # SYNC FOLDERS
    # Tixif
    config.vm.synced_folder "~/Documents/Tixif/django-tixif", "/home/vagrant/Tixif/django-tixif"
    config.vm.synced_folder "~/Documents/Tixif/vivasseduction", "/home/vagrant/Tixif/vivasseduction"
    config.vm.synced_folder "~/Documents/Tixif/vivasseduction.com", "/home/vagrant/Tixif/vivasseduction.com"
    config.vm.synced_folder "~/documents/Tixif/scp-api", "/home/vagrant/Tixif/scp-api"
    config.vm.synced_folder "~/documents/Tixif/scp-web", "/home/vagrant/Tixif/scp-web"
    config.vm.synced_folder "~/documents/Tixif/tixif-com", "/home/vagrant/Tixif/tixif-com"
    config.vm.synced_folder "~/documents/Tixif/scp-mobile", "/home/vagrant/Tixif/scp-mobile"
    config.vm.synced_folder "~/documents/Tixif/dcs-api", "/home/vagrant/Tixif/dcs-api"
    config.vm.synced_folder "~/documents/Tixif/custodian-api", "/home/vagrant/Tixif/custodian-api"
    # Tixif

    # Nexus

    # 	Python
    #config.vm.synced_folder "~/Documents/Nexus/python/django/part3_realpython/", "/home/vagrant/Nexus/python/django/part3_realpython/"
    #config.vm.synced_folder "~/Documents/Nexus/python/django/ed-questionnaire/", "/home/vagrant/Nexus/python/django/ed-questionnaire/"
    #config.vm.synced_folder "~/Documents/Nexus/python/django-oscar/frobshop/", "/home/vagrant/Nexus/python/django-oscar/frobshop/"
    config.vm.synced_folder "~/Documents/Nexus/python/wagtail/", "/home/vagrant/Nexus/python/wagtail/"
    config.vm.synced_folder "~/Documents/Nexus/python/django/django-polls/", "/home/vagrant/Nexus/python/django/django-polls/"
    config.vm.synced_folder "~/Documents/Nexus/python/django/schooldriver/", "/home/vagrant/Nexus/python/django/schooldriver/"

    #	Pelican
    config.vm.synced_folder "~/Documents/Nexus/python/pelican/jeanguzmancom/", "/home/vagrant/Nexus/python/pelican/jeanguzmancom/"
    config.vm.synced_folder "~/Documents/Nexus/python/pelican/guzman-asociadoscom/", "/home/vagrant/Nexus/python/pelican/guzman-asociadoscom/"
    config.vm.synced_folder "~/Documents/Nexus/python/pelican/pelican-blog/", "/home/vagrant/Nexus/python/pelican/pelican-blog/"
    config.vm.synced_folder "~/Documents/Nexus/python/pelican/pelican-plugins/", "/home/vagrant/Nexus/python/pelican/pelican-plugins/"
    config.vm.synced_folder "~/Documents/Nexus/python/pelican/pelican-themes/", "/home/vagrant/Nexus/python/pelican/pelican-themes/"

    # Nexus
    # SYNC FOLDERS

    # box customization
    config.vm.provider :virtualbox do |vb|
        vb.name = 'dev-box'
        vb.cpus = 2
        vb.customize ["modifyvm", :id, "--memory", "2096"]
    end
    # box customization

    # ansible-local provisioning
    config.vm.provision 'ansible_local' do |ansible|
        ansible.playbook = 'provisioning/playbook.yml'
    end
    # ansible-local provisioning
end
