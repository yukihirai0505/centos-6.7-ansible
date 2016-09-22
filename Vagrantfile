Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-6.7"
  config.vm.network "private_network", ip: "192.168.33.11"
  config.vm.synced_folder "./httpdStore", "/var/www/html/"
end
