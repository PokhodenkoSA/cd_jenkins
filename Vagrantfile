# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision "docker" do |d|
    d.pull_images "pokhodenkosa/cd_jenkins"
    d.run "pokhodenkosa/cd_jenkins",
	  args: "-d -p 0.0.0.0:49153:8080"
  end
  config.vm.network "forwarded_port", guest: 49153, host: 4567
end
