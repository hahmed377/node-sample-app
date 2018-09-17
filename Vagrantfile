required_plugin = ["vagrant-hostsupdater"]

required_plugin.each do |plugin|
  exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? (plugin)

end
# running a Vagrant method. The number 2 is the version of vagrant that is running.
Vagrant.configure("2") do |config|
# what version you want of the virtual machine
  config.vm.box = "ubuntu/xenial64"
  config.vm.network("private_network", ip: "192.168.10.100")
  config.hostsupdater.aliases = ["development.local"]

end
