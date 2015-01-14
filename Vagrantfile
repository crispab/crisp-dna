# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # please see the online documentationgra at vagrantup.com.
  config.vm.define "crispmodel"
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 4000, host: 4000

  config.vm.provider "virtualbox" do |vb|
    vb.name = "crisp-model"
    vb.customize ["modifyvm", :id, "--memory", "1024"]
    #vb.gui = true
    #vb.customize ["modifyvm", :id, "--hwvirtex", "off"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.limit = 'all'
    ansible.playbook = "provisioning/playbook.yml"
    #ansible.verbose = "true"
  end

end
