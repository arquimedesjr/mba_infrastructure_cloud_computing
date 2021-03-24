Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.define "mysqlserver" do |mysqlserver|
    mysqlserver.vm.network "private_network", ip: "10.80.4.10"
    mysqlserver.vm.network "forwarded_port", guest: 3306, host:3306

    mysqlserver.vm.provider "virtualbox" do |vb|
      vb.name = "mysqlserver"
      vb.memory = 1024
      vb.cpus = 1
    end
  end

  
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2
  SHELL
end
