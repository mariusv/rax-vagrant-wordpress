# -*- mode: ruby -*-
# vi: set ft=ruby :
#
require 'vagrant-rackspace'

Vagrant.configure("2") do |config|
#Vagrant::Config.run do |config|
  config.vm.hostname = 'vagrant.example.com'
  config.vm.box = "dummy"
  #config.vm.provision :shell, :path => "bootstrap.sh"
  config.vm.provision :shell, :inline =>
    "if [[ ! -f /apt-get-run ]]; then sudo apt-get update && sudo apt-get install -y puppet && sudo touch /apt-get-run; fi"
  config.ssh.private_key_path = "~/.ssh/id_rsa"
  config.vm.provider :rackspace do |os|
    os.username = "mariusvus"
    os.api_key = "7d26cfaa17f1b4cfddac7e81bd000901"
    os.compute_url = "https://lon.identity.api.rackspacecloud.com/v2.0/tcokens"
    os.flavor = /512MB/
    os.image = /Ubuntu 12.04/
    #os.keypair_name = ""
    os.server_name = "vagrant.example.com"
    os.public_key_path = "~/.ssh/id_rsa.pub"
    os.tenant = "10024021"

    #config.vm.share_folder("vagrant-root", "/vagrant", ".", :nfs => true)

    config.vm.provision :puppet do |puppet|
        puppet.manifests_path = "puppet/manifests"
        puppet.module_path = "puppet/modules"
	puppet.manifest_file  = "init.pp"
        puppet.options = ['--verbose --debug']
	end
end
end
