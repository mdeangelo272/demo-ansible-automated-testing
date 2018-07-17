# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  #config.vm.network "forwarded_port", guest: 22, host: 3022

	config.vm.provision "ansible" do |ansible|
		ansible.playbook = "main.yml"
		ansible.compatibility_mode = "2.0"

    # supporte tags: 'install', 'test'
    #
    # ansible.tags = ['test']
    # ansible.skip_tags = ['install']
	end
end
