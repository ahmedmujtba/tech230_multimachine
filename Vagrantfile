# Configure 2 so that 2 virtual machines are created. NOTE: we need a new do block.

Vagrant.configure("2") do |config|

  config.vm.define "app" do |app|
  # configures vm settings
    app.vm.box = "ubuntu/bionic64"
    app.vm.network "private_network", ip:"192.168.1.110"

  # provision the VM to have nginx
    app.vm.provision "shell", path: "provision.sh"

  # put the app folder from local machine to the VM
    app.vm.synced_folder "app", "/home/vagrant/app/app"
  end


  config.vm.define "db" do |db|
  
    db.vm.box = "ubuntu/bionic64"
    db.vm.network "private_network", ip: "192.168.1.150"
  
    db.vm.provision "shell", path: "provisiondb.sh"

    db.vm.synced_folder "environment", "/home/vagrant/environment"
  end

end
