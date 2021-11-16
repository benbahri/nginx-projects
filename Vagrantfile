Vagrant.configure("2") do |config|
  
  config.vm.define "user" do |subconfig|
    subconfig.vm.hostname = "user"
    subconfig.vm.box = "ubuntu/focal64"
    subconfig.vm.network "private_network", ip: "192.168.20.2"
  end

  # Application server
  config.vm.define "backend1" do |subconfig|
    subconfig.vm.hostname = "server1.example.com"
    subconfig.vm.box = "ubuntu/focal64"
    subconfig.vm.network "private_network", ip: "192.168.20.10"
    subconfig.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = "2048"
      vb.name = "backend1"
    end
  end

  config.vm.define "backend2" do |subconfig|
    subconfig.vm.hostname = "server2.example.com"
    subconfig.vm.box = "ubuntu/focal64"
    subconfig.vm.network "private_network", ip: "192.168.20.30"
    subconfig.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = "2048"
      vb.name = "backend2"
    end
  end

    #  Mail  server 1.
  config.vm.define  "mail-server"  do  |app|
    app.vm.hostname  =  "mail.example.com"
    app.vm.box  =  "centos/7"
    app.vm.network  :private_network,  ip:  "192.168.20.40"
    app.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = "2048"
      vb.name = "mail-server"
    end
  end

  #  Authentication  server 1.
  config.vm.define  "auth-server"  do  |app|
    app.vm.hostname  =  "auth.example.com"
    app.vm.box  =  "centos/7"
    app.vm.network  :private_network,  ip:  "192.168.20.50"
    app.vm.provider "virtualbox" do |vb|
      vb.name = "auth"
    end
  end

  # The main proxy server
  config.vm.define  "proxy-server"  do  |app|
    app.vm.hostname  =  "proxy.example.com"
    app.vm.box  =  "ubuntu/focal64"
    app.vm.network  :private_network,  ip:  "192.168.20.254"
    app.vm.provider "virtualbox" do |vb|
      vb.name = "proxy"
    end
  end

end