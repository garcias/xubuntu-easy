# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  # config.vm.network "private_network", ip: "10.0.9.222"
  config.ssh.forward_agent = true
  config.vm.provider :virtualbox do |v|
    v.name = "Xubuntu"
    v.memory = 1024
    v.gui = true
    # v.customize ["modifyvm", :id, '--audio', 'coreaudio', '--audiocontroller', 'hda']
  end
  
  config.vm.provision "shell", privileged: false, inline: $BOOTSTRAP

end

$BOOTSTRAP = <<SCRIPT

# Install desktop
sudo apt-get update -qq
sudo apt-get install -y --no-install-recommends xubuntu-desktop
# After this operation, 213 MB of additional disk space will be used.

# Add Chrome and VS Code to APT sources
wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
sudo sh -c 'echo "deb https://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list'
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'

# Install Chrome and VS Code
sudo apt-get update -qq
sudo apt-get install -y -f google-chrome-stable 
sudo apt-get install -y -f code 

SCRIPT
