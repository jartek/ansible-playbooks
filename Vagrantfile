# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 2
  end

  config.vm.network :forwarded_port, guest: 3000, host: 3000

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "config/ansible-playbooks/site.yml"
    ansible.sudo = true
    ansible.host_key_checking = false
  end
end
