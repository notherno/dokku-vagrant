Vagrant.configure('2') do |config|
  config.vm.box = 'debian/jessie64'
  config.vm.hostname = 'dokku.local'
  config.vm.network 'forwarded_port', guest: 80, host: 8088, guest_ip: '192.168.0.30'
  config.vm.network 'private_network', ip: '192.168.0.30'

  config.vm.provision 'ansible' do |ansible|
    ansible.playbook = 'provisioning/site.yaml'
    ansible.inventory_path = 'provisioning/hosts'
    ansible.limit = 'all'
    ansible.verbose = 'true'
  end
end
