# -*- mode: ruby -*-
# vi: set ft=ruby :

require 'yaml'

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

dir = File.dirname(File.expand_path(__FILE__))
configValues = YAML.load_file("#{dir}/config.yaml")
data = configValues['vm']

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.private_key_path = "~/.ssh/id_rsa"
  config.vm.hostname = "dubyna"
  config.vm.box = "dubyna"
  config.vm.provider :digital_ocean do |provider|
    provider.client_id = "#{data['provider']['digitalocean']['client_id']}"
    provider.token = "#{data['provider']['digitalocean']['token']}"
    provider.image = "Ubuntu 14.04 x64"
    provider.region = "ams2"
    provider.size = '512mb'
  end
end
