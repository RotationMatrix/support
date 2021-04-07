# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/buster64"
  config.vm.network "forwarded_port", guest: 5000, host: 5000, host_ip: "127.0.0.1"
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y python3-dev python3-pip libssl-dev libffi-dev imagemagick gettext python3-babel
    python3 -m pip install Lektor babel
  SHELL
end
