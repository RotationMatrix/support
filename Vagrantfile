# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/buster64"
  config.vm.network "forwarded_port", guest: 5000, host: 5000, host_ip: "127.0.0.1"
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y python3-dev python3-pip libssl-dev libffi-dev imagemagick gettext python3-babel
    python3 -m pip install Lektor babel

    # Recreate our symlinks so this works on Windows hosts.
    cd /vagrant
    ln -sf lego/packages packages
    ln -srf lego/assets/javascript assets/javascript
    ln -srf lego/assets/scss/ assets/scss
    ln -srf lego/assets/static/css/ assets/static/css
    ln -srf lego/assets/static/fonts/ assets/static/fonts
    ln -srf lego/assets/static/js/ assets/static/js
    ln -srf lego/databags/links.ini databags/links.ini
    ln -srf lego/databags/menu.ini databags/menu.ini
    ln -srf lego/databags/menu_footer.ini databags/menu_footer.ini
    ln -srf lego/models/redirect.ini models/redirect.ini
    ln -srf lego/templates/banner.html templates/banner.html
    ln -srf lego/templates/footer.html templates/footer.html
    ln -srf lego/templates/navbar.html templates/navbar.html
    ln -srf lego/templates/redirect.html templates/redirect.html
    ln -srf lego/templates/secure-connections.html templates/secure-connections.html
    ln -srf lego/templates/macros/footer.html templates/macros/footer.html
  SHELL
end
