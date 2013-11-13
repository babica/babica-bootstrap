# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

$script = <<SCRIPT
sudo apt-get -y update
sudo apt-get -y install apache2
gem update --system
gem install compass
SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "lucid32"
    config.vm.network :private_network, ip: "192.168.33.10"
    config.vm.network :forwarded_port, guest: 80, host: 8080, auto_correct: true
    config.vm.synced_folder "../babica-bootstrap/", "/var/www/", id: "babica-bootstrap"
    config.vm.provision "shell", inline: $script
end