# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.define 'alerta' do |m|
    m.vm.network 'private_network', ip: '172.17.177.40'
  end

  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    # ansible.verbose = "vvv"
    ansible.extra_vars = { 
      ansible_python_interpreter: "/usr/bin/python3",
    }
  end
end
