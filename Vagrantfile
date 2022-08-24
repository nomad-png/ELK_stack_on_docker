nodes = [
  { :hostname => 'centos1', :ip => '192.168.1.240', :memory => 512, :cpu => 1, :boxname => "centos/7"},
  { :hostname => 'centos2', :ip => '192.168.1.241', :memory => 2048, :cpu => 2, :boxname => "centos/7"},
]
#Definig some nodes and then configuring them in loop like matter

Vagrant.configure("2") do |config|
  nodes.each do |node|
      config.vm.box_check_update = false
      config.vm.define node[:hostname] do |nodeconfig|
          nodeconfig.vm.box = node[:boxname]
          nodeconfig.vm.hostname = node[:hostname]
	        nodeconfig.vm.network :private_network, ip: node[:ip]
          nodeconfig.vm.provider :virtualbox do |vb|
            vb.memory = node[:memory]
            vb.cpus = node[:cpu]
          end
        end
  end

  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "playbook.yml"
    # ansible.inventory_path = 'inventory'
    # ansible.install_mode = "pip"
    # ansible.version = "2.2.1.0"
  end

end
