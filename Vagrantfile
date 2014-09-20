# -*- mode: ruby -*-
# vi: set ft=ruby :

require 'yaml'

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

dir = File.dirname(File.expand_path(__FILE__))
configValues = YAML.load_file("#{dir}/vagrant/config.yaml")
data = configValues['vm']

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.private_key_path = "~/.ssh/id_rsa"
  config.vm.hostname = "dubyna.in.ua"
  config.vm.box = "dubyna.in.ua"
  config.vm.provider :digital_ocean do |provider|
    provider.client_id = "#{data['provider']['digitalocean']['client_id']}"
    provider.token = "#{data['provider']['digitalocean']['token']}"
    provider.image = "CentOS 6.5 x64"
    provider.region = "ams2"
    provider.size = '512mb'
  end

#  config.vm.provision "shell", path: "./vagrant/modules/centos-6-5-x64/epel.sh"
#  config.vm.provision "shell", path: "./vagrant/modules/centos-6-5-x64/dev-tools.sh"
#  config.vm.provision "shell", path: "./vagrant/modules/centos-6-5-x64/ruby.sh"
#  config.vm.provision "shell", path: "./vagrant/modules/centos-6-5-x64/mysql.sh"
#  config.vm.provision "shell", path: "./vagrant/modules/centos-6-5-x64/redmine.sh"
#  config.vm.provision "shell", path: "./vagrant/modules/centos-6-5-x64/apache.sh"

end
