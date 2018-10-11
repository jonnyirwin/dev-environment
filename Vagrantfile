Vagrant.configure("2") do |config|
  config.ssh.forward_agent = true
  config.vm.box = "ubuntu/bionic64"
  config.vm.network "private_network", ip: "192.168.38.2"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "24576"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook="playbook.yaml"
    ansible.extra_vars = {
      ansible_python_interpreter: "/usr/bin/python3.6"
    }
  end
end
