# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.synced_folder "/tmp", "/tmp/src"

  if Vagrant.has_plugin? "vagrant-vbguest"
    config.vbguest.no_install  = true
    config.vbguest.auto_update = false
    config.vbguest.no_remote   = true
  end

  config.vm.define :servidorUbuntu do |servidorUbuntu|
    servidorUbuntu.vm.box = "bento/ubuntu-22.04"
    servidorUbuntu.vm.box_download_insecure = true
    servidorUbuntu.vm.network :private_network, ip: "192.168.100.3"
    servidorUbuntu.vm.provision "shell", path:"scriptnodoserver.sh" #Aprovisionador con shell
    servidorUbuntu.vm.hostname = "servidorUbuntu"
  end

  config.vm.define :clienteUbuntu do |clienteUbuntu|
    clienteUbuntu.vm.box = "bento/ubuntu-22.04"
    clienteUbuntu.vm.box_download_insecure = true
    clienteUbuntu.vm.network :private_network, ip: "192.168.100.2"
    clienteUbuntu.vm.provision "shell", path:"scriptclient.sh" #Aprovisionador con shell    
    clienteUbuntu.vm.hostname = "clienteUbuntu"
  end

  config.vm.define :nodo2Ubuntu do |nodo2Ubuntu|
    nodo2Ubuntu.vm.box = "bento/ubuntu-22.04"
    nodo2Ubuntu.vm.box_download_insecure = true
    nodo2Ubuntu.vm.network :private_network, ip: "192.168.100.4"
    nodo2Ubuntu.vm.provision "shell", path:"scriptnodo2.sh" #Aprovisionador con shell
    nodo2Ubuntu.vm.hostname = "nodo2Ubuntu"
  end

  
  
  
  
  
  
  

  # config.vm.define :clienteUbuntu do |vbclienteUbuntu|
  #  vbclienteUbuntu.customize = ['modifyvm', :id, '--memory', '1024']
  #  vbclienteUbuntu.customize = ['modifyvm', :id, '--cpus', '2']
  # end

  #config.vm.provision "shell" do |s|
  #  s.inline = "echo $1"
  #  s.args = ["Hellom, wold!"]
  #end

end

