VAGRANTFILE_API_VERSION= "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Use the same key for each machine
  config.ssh.insert_key = false

  config.vm.define "lb" do |lb|
    lb.vm.box = "ubuntu/trusty64"
    lb.vm.network "forwarded_port", guest: 80, host: 8084
  end

  config.vm.define "webserver" do |webserver|
    webserver.vm.box = "ubuntu/trusty64"
    webserver.vm.network "forwarded_port", guest: 80, host: 8082
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.sudo = true
  end
end

