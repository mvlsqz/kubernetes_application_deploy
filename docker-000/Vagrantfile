# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = 'centos/8'
  config.disksize.size = '50GB'
  config.vm.network 'public_network', bridge: 'wlp1s0'
  # config.vm.synced_folder './code', '/code' 
  config.vm.provision "shell", inline: <<-SHELL 
    yum install -y yum-utils
    yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    yum install -y docker-ce docker-ce-cli containerd.io
  SHELL

  config.vm.provider 'virtualbox' do |v|
    v.memory = 2048
    v.cpus = 2
  end
end
