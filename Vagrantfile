# -*- mode: ruby -*-
# vi: set ft=ruby :

$provision_script = <<SCRIPT
set -ex
sudo apt-get update && sudo apt-get install -y docker.io
sudo gpasswd -a vagrant docker
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  config.vm.provision "shell", inline: $provision_script
end
