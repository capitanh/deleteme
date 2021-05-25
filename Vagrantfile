# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  #config.vm.box = 'roboxes/alpine38'
  config.vm.box = 'ubuntu/groovy64'
  config.vm.network "forwarded_port", host:9000, guest:9000 # k8s dashboard
  config.vm.provider "virtualbox" do |vb|
    vb.name = 'sonar'
    vb.memory = 2048
    vb.cpus = 2
    vb.gui = false
  end

  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = '2.0'
    ansible.playbook = 'site.yml'
    #ansible.verbose = "vvv"
    ansible.galaxy_role_file = 'requirements.yml'
    ansible.galaxy_roles_path = '~/.ansible/roles'
  end

end
