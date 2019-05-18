# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.provision "shell", path: "bootstrap.sh"

  # Kubernetes Master Server
  config.vm.define "kmaster" do |kmaster|
    kmaster.vm.box = "ubuntu/xenial64"
    kmaster.vm.hostname = "kmaster.example.com"
    kmaster.vm.network "private_network", ip: "172.42.42.100"
    kmaster.vm.provider "virtualbox" do |v|
      v.name = "kmaster"
      v.memory = 2048
      v.cpus = 2
    end
    kmaster.vm.provision "shell", path: "bootstrap_kmaster.sh"
  end

end
