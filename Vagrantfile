Vagrant.configure("2") do |config|

  config.vm.box = "debian/bookworm64"

  # Control Node
  config.vm.define "control-node" do |control|
    control.vm.hostname = "control-node"
    control.vm.network "private_network", ip: "192.168.56.5"

    control.vm.provider "virtualbox" do |vb|
      vb.name = "UTS-Control-Node"
      vb.memory = 2048
      vb.cpus = 2
    end
  end

  # Web Server
  config.vm.define "web-server" do |web|
    web.vm.hostname = "web-server"
    web.vm.network "private_network", ip: "192.168.56.10"

    web.vm.provider "virtualbox" do |vb|
      vb.name = "UTS-Web-Server"
      vb.memory = 2048
      vb.cpus = 2
    end
  end

  # Database Server
  config.vm.define "db-server" do |db|
    db.vm.hostname = "db-server"
    db.vm.network "private_network", ip: "192.168.56.11"

    db.vm.provider "virtualbox" do |vb|
      vb.name = "UTS-Database-Server"
      vb.memory = 2048
      vb.cpus = 2
    end
  end

end