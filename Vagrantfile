Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-24.04"
  config.vm.hostname = "controlnode"
  config.vm.network "public_network"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.boot_timeout = 600 
  # Скрипт для установки Ansible и acl
  config.vm.provision "shell", inline: <<-SHELL
    # Установка Ansible
    sudo apt install -y ansible
	sudo apt install -y acl
	ansible-galaxy install geerlingguy.postgresql -p /home/vagrant/.ansible/roles
	chown -R vagrant:vagrant /home/vagrant/.ansible/
	

  SHELL
end
