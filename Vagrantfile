# -*- mode: ruby -*-
# vi: set ft=ruby :
ENV["LC_ALL"] = "en_US.UTF-8"
$nodes = 5

Vagrant.configure(2) do |config|

  config.vm.define "librenms" do |librenms|
    librenms.vm.box = "geerlingguy/ubuntu1604"
    librenms.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"
    librenms.vm.network :public_network, ip: "10.20.30.115",
       :use_dhcp_assigned_default_route => true, bridge: "eth0"
    librenms.vm.network :private_network, ip: "192.168.111.111"
    librenms.vm.hostname = "librenms"
    librenms.vm.provider "virtualbox" do |v|
       v.memory = 2048
       v.cpus = 4
     end
    librenms.vm.provision :ansible do |ansible|
      #  ansible.verbose = "vvv"
       ansible.limit = "service"
       ansible.playbook = "main.yml"
       ansible.inventory_path = "./inventory.ini"
    end
  end
end
