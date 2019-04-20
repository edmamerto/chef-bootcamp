# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "edmamerto/bento-ubuntu-16.04-chef"
  config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  config.vm.synced_folder "./cookbooks", "/chef-repo/cookbooks"
  config.vm.synced_folder "./cookbooks", "/chef-repo/roles"
  config.vm.synced_folder "./.chef", "/chef-repo/.chef"
  config.vm.synced_folder "./secrets", "/home/vagrant/.ssh"
  config.vm.provision "shell", inline: <<-SHELL
    export HOME="/home/vagrant"
    chmod +x $HOME/.ssh/vagrantrc.sh
    cp $HOME/.ssh/vagrantrc.sh $HOME/
    echo '. $HOME/vagrantrc.sh' >>$HOME/.bashrc
    . $HOME/.bashrc
  SHELL
end

