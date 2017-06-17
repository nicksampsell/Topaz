# -*- mode: ruby -*-
# vi: set ft=ruby :

$perms = <<PERMS
	chmod a+rx /home/vagrant/bin/siteup
	chmod a+rx /home/vagrant/bin/build
PERMS

site_url = "dev.nicksampsell.com"
ip_address = "192.168.33.10"

Vagrant.configure("2") do |config|
	config.vm.box = "ubuntu/xenial64"
	config.vm.network :private_network, ip: ip_address
	config.vm.synced_folder "./app", "/home/vagrant/public_html/#{site_url}", :extra => 'dmode=777,fmode=777'
	config.vm.synced_folder "./bin", "/home/vagrant/bin/", :extra => 'dmode=777,fmode=777'
	config.vm.provision :shell, :inline => $perms
end
