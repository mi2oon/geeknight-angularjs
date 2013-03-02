# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "lucid64"
  config.vm.box_url = "http://files.vagrantup.com/lucid64.box"

  config.vm.provision :puppet, :module_path => "modules" do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file = "site.pp"
  end

  config.vm.define :www do |config|
    config.vm.host_name = "www.mwl.dk"
    config.vm.network :hostonly, "192.168.33.10"
    config.vm.share_folder "wwwroot", "/var/wwwroot", "wwwroot"
  end
end
