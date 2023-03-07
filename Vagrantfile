Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "public_network"
  config.vm.synced_folder "./website", "/var/www/html"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "server-website"
    vb.memory = "4096"
    vb.cpus = "4"
  end
  config.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install -y nginx
  SHELL
end
