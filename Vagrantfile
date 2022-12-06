# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"

  config.vm.provision "ansible" do |ansible|
#   ansible.verbose = "vvv"
    ansible.playbook = "myfirstPB.yml"
    ansible.become = "true"
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 256
    v.cpus = 1
  end

  config.vm.define "rpm" do |rpm|
    rpm.vm.network "private_network", ip: "192.168.50.10", virtualbox__intnet: "net1"
    rpm.vm.hostname = "rpm"
#   rpm.vm.provision "shell", path: "rpm_script.sh"
  end

end
