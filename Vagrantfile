# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "geerlingguy/ubuntu1604"
    # config.vm.box = "ubuntu/trusty64"
    config.vm.network :private_network, ip: "192.168.153.54"
    config.ssh.insert_key = false
    config.vm.hostname = "docker.test"

    config.vm.provider :virtualbox do |v|
        v.customize ["modifyvm", :id, "--name", "docker.test"]
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--memory", 1024]
        v.customize ["modifyvm", :id, "--cpus", 2]
        v.customize ["modifyvm", :id, "--ioapic", "on"]
    end
  # Enable provisioning with Ansible.
    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "provisioning/main.yml"
    end
end
