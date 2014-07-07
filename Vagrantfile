# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrant configuration file, simplified from:
# https://github.com/pjan/the-ansibles/blob/master/contrib/vagrant/Vagrantfile

BOX_IMAGE     = ENV['BOX_IMAGE']     || "ubuntu/trusty64"
BOX_IP_ZONE   = ENV['BOX_IP_ZONE']   || "192.168.111"
BOX_FORWARDED_PORT = ENV['BOX_FORWARDED_PORT'] || 22

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Set up multiple servers for different services
  # NOTE: Make sure all IPs are on the same subnet, e.g. begin with 22

  config.vm.define "webserver" do |webserver|
    ip_end = "222"
    webserver.vm.box = BOX_IMAGE
    webserver.vm.network :private_network, ip: BOX_IP_ZONE + "." + ip_end
  end


  config.vm.define "elasticsearch" do |elastic|
    ip_end = "223"
    elastic.vm.box = BOX_IMAGE
    elastic.vm.hostname = "vagrant-elasticsearch"
    elastic.vm.network :private_network, ip: BOX_IP_ZONE + "." + ip_end
  end

  config.vm.define "znc" do |znc|
    ip_end = "224"
    ssh_port = '5001'

    znc.vm.box = BOX_IMAGE
    znc.vm.hostname = "vagrant-znc"
    znc.vm.network :private_network, ip: BOX_IP_ZONE + "." + ip_end
  end
  
end
