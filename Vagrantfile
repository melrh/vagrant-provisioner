Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"  
  config.vm.hostname = "test"
  
  # Run Ansible from the Vagrant Host  

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.extra_vars = "ansible/group_vars/vars.yml"
  end

end
