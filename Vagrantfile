# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.require_version ">= 1.4.0"

BOX_NAME = "ate"

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"

  config.vm.define BOX_NAME do |t| end
  config.vm.hostname = "#{BOX_NAME}.localdomain"
  config.vm.provider :virtualbox do |vbox|
    vbox.name = BOX_NAME
    vbox.memory = 1024
  end

  config.vm.provision :shell, :inline => "apt-get install software-properties-common; apt-add-repository ppa:ansible/ansible; apt-get update"
  config.vm.provision :shell, :inline => "apt-get install -y ansible"
  config.vm.provision :shell, :inline => "apt-get install -y zsh"
  config.vm.provision :shell, :inline => "chsh -s /usr/bin/zsh vagrant"

end
