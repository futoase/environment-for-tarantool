# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "bento-Ubuntu-14.04"

  config.vm.network "private_network", ip: "192.168.33.123"

  config.ssh.forward_agent = true

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.customize ["modifyvm", :id, 
                  "--memory", "1024", 
                  "--cpus", "2", 
                  "--ioapic", "on"
                 ]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "app.yml"
    ansible.limit = "all"
  end
end
