Dotenv.load
Vagrant.configure(2) do |config|
  config.vm.box = "futureys/centos-6"
  config.vm.hostname = "my.localhost"
  config.vm.network :forwarded_port, guest: 80, host: 80
  config.vm.network :forwarded_port, guest: 443, host: 443
  config.vm.synced_folder "./", "/vagrant", type:"nfs"
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.verbose  = "vvv"
    ansible.inventory_path = "./inventories/development"
  end
end
