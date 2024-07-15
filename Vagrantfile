Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true

  ### Database Virtual Machine ###
  config.vm.define "db" do |db|
    db.vm.box = "eurolinux-vagrant/centos-stream-9"
    db.vm.box_version = "9.0.45"
    db.vm.hostname = "db"
    db.vm.network "private_network", ip:"192.168.40.10"
    db.vm.provider "virtualbox" do |vb|
      vb.memory="600"
    end
    db.vm.provision "shell", path: "db.sh"
  end

  ### Memcache Virtual Machine ###
  config.vm.define "mc" do |mc|
    mc.vm.box = "eurolinux-vagrant/centos-stream-9"
    mc.vm.box_version = "9.0.45"
    mc.vm.hostname = "mc"
    mc.vm.network "private_network", ip:"192.168.40.11"
    mc.provider "virtualbox" do |vb|
      vb.memory="600"
    end
    mc.vm.provision "shell", path: "mc.sh"
  end

  ### Rabbit MQ Virtual machine ###
  config.vm.define "rm" do |rm|
    rm.vm.box = "eurolinux-vagrant/centos-stream-9"
    rm.vm.box_version = "9.0.45"
    rm.vm.hostname = "rm"
    rm.vm.network "private_network", ip:"192.168.40.12"
    rm.vm.provider "virtualbox" do |vb|
      vb.memory="600"
    end
    rm.vm.provision "shell", path: "rm.sh"
  end

  ### Web Server Virtual Machine ###
  config.vm.define "sv" do |sv|
    sv.vm.box = "eurolinux-vagrant/centos-stream-9"
    sv.vm.box_version = "9.0.45"
    sv.vm.hostname = "sv"
    sv.vm.network "private_network", ip:"192.168.40.13"
    sv.vm.provider "virtualbox" do |vb|
      vb.memory="800"
    end
    sv.vm.provision "shell", path: "sv.sh"
  end

  ### Load balancer Virtual Machine ###
  config.vm.define "lb" do |lb|
    lb.vm.box = "ubuntu/jammy64"
    lb.vm.hostname = "lb"
    lb.vm.network "private_network", ip:"192.168.40.14"
    lb.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.memory="800"
    end
  end
end
  
