# -*- mode: ruby -*-
# vim: set ft=ruby :
home = ENV['HOME']
ENV["LC_ALL"] = "en_US.UTF-8"


Vagrant.configure(2) do |config|
  # ПЕРВАЯ ВИРТУАЛЬНАЯ МАШИНА
    config.vm.define "server" do |server|
    # имя виртуальной машины
    server.vm.box = 'vedoff/centos-7-5' 
    server.vm.provider "virtualbox" do |vb|
      vb.name = "server"
    end
    # hostname виртуальной машины
    server.vm.hostname = "server"
    # настройки сети
    server.vm.network "private_network", ip: "192.168.56.105"
    server.vm.synced_folder ".", "/vagrant",  
          type: "rsync",
          rsync_auto: "true",
          rsync_exclude: [".git/",".vagrant/",".gitignore","Vagrantfile"]
#          server.vm.provision "shell", path: "provision-server/nfs-server.sh"
    end
end
