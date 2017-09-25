Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|

  config.vm.box = "hashicorp/precise64"
  
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.network "forwarded_port", guest: 5000, host: 7070
  config.vm.network "forwarded_port", guest: 80, host: 6060  
  config.vm.network "forwarded_port", guest: 80, host: 90  
  config.ssh.insert_key = false

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yaml"
  end
end
