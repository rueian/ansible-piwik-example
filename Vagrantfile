VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.insert_key = false

  config.vm.box = 'ubuntu/trusty64'

  config.vm.synced_folder '.', '/vagrant'

  config.vm.provider 'virtualbox' do |v|
    v.memory = 512
    v.cpus = 4
  end

  config.vm.define 'piwik' do |node|
    node.vm.hostname = 'piwik'
    node.vm.network :private_network, ip: '10.10.10.10'

    node.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'main.yml'
      ansible.limit = 'all'
      ansible.inventory_path = 'inventory.ini'
      ansible.extra_vars = {
        ansible_ssh_user: 'vagrant',
        ansible_ssh_pass: 'vagrant'
      }
    end
  end
end
