Vagrant.configure("2") do |config|
  ip = 1
  [
    "ds210-node1",
    "ds210-node2",
    "ds210-node3"
  ].each do |host|
      config.vm.define "#{host}" do |dse|
        dse.vm.box = "ubuntu/trusty64"
        dse.vm.network "private_network", ip: "192.168.44.#{100 + ip}"
        ip += 1
        dse.vm.provider :virtualbox do |vb|
          vb.customize [
            "modifyvm", :id,
            "--name", "#{host}",
            "--memory", "1024"
          ]
          vb.cpus = 2
        end
        config.vm.hostname = "#{host}"
        if host == "ds210-node3"
          config.vm.provision :ansible do |ansible|
            ansible.limit = "all"
            ansible.playbook = "ds210.yml"
          end
        end
      end
  end
end
