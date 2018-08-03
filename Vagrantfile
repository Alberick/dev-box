# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    # box 
    config.vm.box = "ubuntu/xenial64"
    # box 

    # sync folders
    config.vm.synced_folder "./provisioning", "/home/vagrant/provisioning"
    config.vm.synced_folder "../shared_folder", "/home/vagrant/shared_folder"
    # sync folders
    
    # public network
    config.vm.network "public_network"
    # public network
    
    # forworded ports
    for i in 0..5
	    config.vm.network "forwarded_port", guest: (8000 + i), host: (8000 + i)
    end

    config.vm.network "forwarded_port", guest: 1433, host: 1433 
    config.vm.network "forwarded_port", guest: 8080, host: 8080 
    config.vm.network "forwarded_port", guest: 2376, host: 2376 
    config.vm.network "forwarded_port", guest: 3306, host: 3306 
    config.vm.network "forwarded_port", guest: 5432, host: 5432 
    config.vm.network "forwarded_port", guest: 53703, host: 53703 

    # forworded ports


    # SYNC FOLDERS
    # Ceroic
    config.vm.synced_folder "d:/Documents/Ceroic/cyrious.com", "/home/vagrant/Ceroic/cyrious.com"
    # Ceroic

    # SYNC FOLDERS
    # Tixif
    config.vm.synced_folder "d:/Documents/Tixif/vivasseduction.com", "/home/vagrant/Tixif/vivasseduction.com"
    config.vm.synced_folder "d:/documents/Tixif/scp-api", "/home/vagrant/Tixif/scp-api"
    config.vm.synced_folder "d:/documents/Tixif/scp-api-v2", "/home/vagrant/Tixif/scp-api-v2"
    config.vm.synced_folder "d:/documents/Tixif/custodian-api", "/home/vagrant/Tixif/custodian-api"
    config.vm.synced_folder "d:/documents/Tixif/census-api", "/home/vagrant/Tixif/census-api"
    config.vm.synced_folder "d:/documents/Tixif/oscar-tixif", "/home/vagrant/Tixif/oscar-tixif"
    config.vm.synced_folder "d:/documents/Tixif/legsa-ecommerce", "/home/vagrant/Tixif/legsa-ecommerce"
    config.vm.synced_folder "d:/documents/Tixif/vivas-seduction-api", "/home/vagrant/Tixif/vivas-seduction-api"
    # Tixif
    
    config.vm.synced_folder "d:/documents/Ahinko/geo-tracker", "/home/vagrant/Ahinko/geo-tracker"
    config.vm.synced_folder "d:/documents/Ahinko/dcs-api", "/home/vagrant/Ahinko/dcs-api"
    config.vm.synced_folder "d:/documents/Ahinko/pof-api", "/home/vagrant/Ahinko/pof-api"
    config.vm.synced_folder "d:/documents/Ahinko/fidcrm-api", "/home/vagrant/Ahinko/fidcrm-api"

    # Nexus

    # Django
    config.vm.synced_folder "d:/Documents/Nexus/python/django/django-map-widgets/", "/home/vagrant/Nexus/python/django/django-map-widgets/"
    config.vm.synced_folder "d:/Documents/Nexus/python/django/django-test-bench/", "/home/vagrant/Nexus/python/django/django-test-bench/"
    # config.vm.synced_folder "d:/Documents/Nexus/python/django/ed-questionnaire/", "/home/vagrant/Nexus/python/django/ed-questionnaire/"
    # config.vm.synced_folder "d:/Documents/Nexus/python/django/django-polls/", "/home/vagrant/Nexus/python/django/django-polls/"
    # config.vm.synced_folder "d:/Documents/Nexus/python/django/schooldriver/", "/home/vagrant/Nexus/python/django/schooldriver/"
    # config.vm.synced_folder "d:/Documents/Nexus/python/django/django-scheduler-sample/", "/home/vagrant/Nexus/python/django/django-scheduler-sample/"
    # config.vm.synced_folder "d:/Documents/Nexus/python/django/django-push-notifications", "/home/vagrant/Nexus/python/django/django-push-notifications"
    # config.vm.synced_folder "d:/Documents/Nexus/python/django/django-scheduler", "/home/vagrant/Nexus/python/django/django-scheduler"
    # config.vm.synced_folder "d:/Documents/Nexus/python/django/django-rest-auth", "/home/vagrant/Nexus/python/django/django-rest-auth"
    # config.vm.synced_folder "d:/Documents/Nexus/python/django/django-allauth", "/home/vagrant/Nexus/python/django/django-allauth"
    
    # Geodjango
    # config.vm.synced_folder "d:/Documents/Nexus/python/geo-django/geodjango", "/home/vagrant/Nexus/python/geo-django/geodjango"
    
    # Oscar
    # config.vm.synced_folder "d:/Documents/Nexus/python/django-oscar/frobshop/", "/home/vagrant/Nexus/python/django-oscar/frobshop/"
    #config.vm.synced_folder "d:/Documents/Nexus/python/django-oscar/django-oscar/", "/home/vagrant/Nexus/python/django-oscar/django-oscar/"
    
    # Wagtail
    config.vm.synced_folder "d:/Documents/Nexus/python/wagtail/", "/home/vagrant/Nexus/python/wagtail/"

    # Pelican
    config.vm.synced_folder "d:/Documents/Nexus/python/pelican/jeanguzmancom/", "/home/vagrant/Nexus/python/pelican/jeanguzmancom/"
    # config.vm.synced_folder "d:/Documents/Nexus/python/pelican/guzman-asociadoscom/", "/home/vagrant/Nexus/python/pelican/guzman-asociadoscom/"
    # config.vm.synced_folder "d:/Documents/Nexus/python/pelican/pelican-blog/", "/home/vagrant/Nexus/python/pelican/pelican-blog/"
    # config.vm.synced_folder "d:/Documents/Nexus/python/pelican/pelican-plugins/", "/home/vagrant/Nexus/python/pelican/pelican-plugins/"
    # config.vm.synced_folder "d:/Documents/Nexus/python/pelican/pelican-themes/", "/home/vagrant/Nexus/python/pelican/pelican-themes/"
    
    # Viewflow
    # config.vm.synced_folder "d:/Documents/Nexus/python/django/viewflow/", "/home/vagrant/Nexus/python/django/viewflow/"

    # Nexus
    # SYNC FOLDERS

    # box customization
    config.vm.provider :virtualbox do |vb|
        vb.name = 'dev-box'
        vb.cpus = 2
        vb.customize ["modifyvm", :id, "--memory", "4096"]
    end
    # box customization

    # ansible-local provisioning
    config.vm.provision 'ansible_local' do |ansible|
        ansible.playbook = 'provisioning/playbook.yml'
    end
    # ansible-local provisioning
end
