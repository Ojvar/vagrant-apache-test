# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |vb|
    # vb.gui = true
  
    # Customize the amount of memory on the VM:
    vb.memory = "2048"
    vb.cpus = "2"
  end

  config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  # config.vm.network "private_network", ip: "192.168.56.200", :type => 'dhcp'
  # config.vm.network "public_network"
  # config.vm.synced_folder "./html", "/var/www/html", :nfs => { :mount_options => ["dmode=777", "fmode=666"] }
  config.vm.synced_folder "./html", "/var/www/html"

  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL

  config.vm.provision "shell", path: "bootstrap.sh"
end
