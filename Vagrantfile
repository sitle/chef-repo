# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define :proxy do |c|
    # Personnalisation de la box (OS)
    c.vm.box = "ubuntu12.04-chef"
    c.vm.box_url = "http://repository.srv.gov.pf/box/ubuntu12.04-chef-vb.box"

    # Personnalisation du hostname dans la VM
    c.vm.hostname = "proxy.toriki.os.gov.pf"

    # Configuration réseau
    c.vm.network "private_network", ip: "192.168.250.2"

    # Configuration du provisionner CHEF
    c.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["cookbooks", "site-cookbooks"]
      chef.roles_path = "roles"
      chef.data_bags_path = ["data_bags"]
      chef.encrypted_data_bag_secret_key_path = 'data_bags/secret_key'
      chef.custom_config_path = "Vagrantfile.chef"

      # Application des recipes/roles
      #chef.add_role("base-servers")
    end

    # Personnalisation du provider : virtualbox
    c.vm.provider "virtualbox" do |v|
      v.gui = false
      v.name = "proxy"
      v.memory = 512
      v.cpus = 1
    end
  end

  config.vm.define :node1 do |c|
    # Personnalisation de la box (OS)
    c.vm.box = "ubuntu14.04-chef"
    c.vm.box_url = "http://repository.srv.gov.pf/box/ubuntu14.04-chef-vb.box"

    # Personnalisation du hostname dans la VM
    c.vm.hostname = "node1.toriki.os.gov.pf"

    # Configuration réseau
    c.vm.network "private_network", ip: "192.168.250.10"

    # Configuration du provisionner CHEF
    c.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["cookbooks", "site-cookbooks"]
      chef.roles_path = "roles"
      chef.data_bags_path = ["data_bags"]
      chef.encrypted_data_bag_secret_key_path = 'data_bags/secret_key'
      chef.custom_config_path = "Vagrantfile.chef"

      # Application des recipes/roles
      #chef.add_role("base-servers")
    end

    # Personnalisation du provider : virtualbox
    c.vm.provider "virtualbox" do |v|
      v.gui = false
      v.name = "node1"
      v.memory = 1024
      v.cpus = 2
    end
  end

  config.vm.define :node2 do |c|
    # Personnalisation de la box (OS)
    c.vm.box = "ubuntu14.04-chef"
    c.vm.box_url = "http://repository.srv.gov.pf/box/ubuntu14.04-chef-vb.box"

    # Personnalisation du hostname dans la VM
    c.vm.hostname = "node2.a1a2.os.gov.pf"

    # Configuration réseau
    c.vm.network "private_network", ip: "192.168.250.11"

    # Configuration du provisionner CHEF
    c.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["cookbooks", "site-cookbooks"]
      chef.roles_path = "roles"
      chef.data_bags_path = ["data_bags"]
      chef.encrypted_data_bag_secret_key_path = 'data_bags/secret_key'
      chef.custom_config_path = "Vagrantfile.chef"

      # Application des recipes/roles
      #chef.add_role("base-servers")
    end

    # Personnalisation du provider : virtualbox
    c.vm.provider "virtualbox" do |v|
      v.gui = false
      v.name = "node2"
      v.memory = 512
      v.cpus = 1
    end
  end

  config.vm.define :node3 do |c|
    # Personnalisation de la box (OS)
    c.vm.box = "ubuntu14.04-chef"
    c.vm.box_url = "http://repository.srv.gov.pf/box/ubuntu14.04-chef-vb.box"

    # Personnalisation du hostname dans la VM
    c.vm.hostname = "node3.daf.os.gov.pf"

    # Configuration réseau
    c.vm.network "private_network", ip: "192.168.250.12"

    # Configuration du provisionner CHEF
    c.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["cookbooks", "site-cookbooks"]
      chef.roles_path = "roles"
      chef.data_bags_path = ["data_bags"]
      chef.encrypted_data_bag_secret_key_path = 'data_bags/secret_key'
      chef.custom_config_path = "Vagrantfile.chef"

      # Application des recipes/roles
      #chef.add_role("base-servers")
    end

    # Personnalisation du provider : virtualbox
    c.vm.provider "virtualbox" do |v|
      v.gui = false
      v.name = "node3"
      v.memory = 512
      v.cpus = 1
    end
  end
end