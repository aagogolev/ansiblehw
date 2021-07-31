# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  #глобальные значения в в данном сдучае отключено автообновление
  config.vm.box_check_update = false

#------------------------------UBUNTU------------------------------------------

  config.vm.define "ubuntu_db" do |ubuntu_db|
    ubuntu_db.vm.box = "generic/ubuntu2010"
    ubuntu_db.vm.network  "public_network", ip: "192.168.0.160", bridge: "wlp2s0"
    ubuntu_db.vm.hostname = "ubuntu-db"
    ubuntu_db.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      ubuntu_db.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook-db.yml"
        ansible.become = true
      end
    end
  end

  config.vm.define "ubuntu_nginx" do |ubuntu_nginx|
    ubuntu_nginx.vm.box = "generic/ubuntu2010"
    ubuntu_nginx.vm.network  "public_network", ip: "192.168.0.161", bridge: "wlp2s0"
    ubuntu_nginx.vm.hostname = "ubuntu-nginx"
    ubuntu_nginx.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      ubuntu_nginx.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook-nginx.yml"
        ansible.become = true
      end
    end
  end

  config.vm.define "ubuntu_app" do |ubuntu_app|
    ubuntu_app.vm.box = "generic/ubuntu2010"
    ubuntu_app.vm.network  "public_network", ip: "192.168.0.162", bridge: "wlp2s0"
    ubuntu_app.vm.hostname = "ubuntu-app"
    ubuntu_app.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      ubuntu_app.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook-app.yml"
        ansible.become = true
      end
    end
  end

#-----------------------------CENTOS------------------------------------------

  config.vm.define "centos_app" do |centos_app|
    centos_app.vm.box = "centos/8"
    centos_app.vm.network "public_network", ip: "192.168.0.165", bridge: "wlp2s0"
    centos_app.vm.hostname = "centos-app"
    centos_app.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      centos_app.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook-app.yml"
        ansible.become = true
      end
    end
  end

end
