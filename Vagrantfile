Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true

  ### Database Virtual Machine ###
  config.vm.define "db" do |db|
    config.vm.box = "eurolinux-vagrant/centos-stream-9"
    db.vm.box_version = "9.0.45"
    db.vm.hostname = "db"
    db.vm.network "private_network", ip:"192.168.40.10"
    db.vm.provider "virtualbox" do |vb|
      vb.memory="600"
    end
  end

  ### Memcache Virtual Machine ###
  config.vm.define "mc" do |mc|
    config.vm.box = "eurolinux-vagrant/centos-stream-9"
    db.vm.box_version = "9.0.45"
    db.vm.hostname = "mc"
    db.vm.network "private_network", ip:"192.168.40.11"
    db.vm.provider "virtualbox" do |vb|
      vb.memory="600"
    end
  end

  ### Rabbit MQ Virtual machine ###
  config.vm.define "rm" do |rm|
    config.vm.box = "eurolinux-vagrant/centos-stream-9"
    db.vm.box_version = "9.0.45"
    db.vm.hostname = "rm"
    db.vm.network "private_network", ip:"192.168.40.12"
    db.vm.provider "virtualbox" do |vb|
      vb.memory="600"
    end
  end

  ### Web Server Virtual Machine ###
  config.vm.define "sv" do |sv|
    config.vm.box = "eurolinux-vagrant/centos-stream-9"
    db.vm.box_version = "9.0.45"
    db.vm.hostname = "sv"
    db.vm.network "private_network", ip:"192.168.40.13"
    db.vm.provider "virtualbox" do |vb|
      vb.memory="800"
    end
  end

  ### Load balancer Virtual Machine ###
  config.vm.define "lb" do |lb|
    config.vm.box = "ubuntu/jammy64"
    db.vm.hostname = "lb"
    db.vm.network "private_network", ip:"192.168.40.14"
    db.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.memory="800"
    end
  end
  
