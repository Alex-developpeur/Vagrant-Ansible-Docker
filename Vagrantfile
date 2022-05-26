# -*- mode: ruby -*-
# vi: set ft=ruby :

$vmw_name = "va-ansibles"
$vmw_gui = false
$vmw_memory = 1024
$vmw_cpus = 1

Vagrant.configure("2") do |config|
  config.vm.box = "bento/debian-11"
  config.vm.network :private_network, ip: "192.168.44.4"
  config.vm.hostname = $vmw_name

  config.vm.provider "vmware_desktop" do |v|
    v.gui = $vmw_gui
    v.vmx['memsize'] = $vmw_memory
    v.vmx['numvcpus'] = $vmw_cpus
  end

  config.vm.provision "ansible_local" do |ansible|    
    ansible.playbook = "playbook.yml"
  end

end
