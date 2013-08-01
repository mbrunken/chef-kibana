# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  config.vm.box = "squeeze64"
  config.vm.box_url = "http://debbuild.bigpoint.net/squeeze64.box"

  # Assign this VM to a host-only network IP, allowing you to access it
  # via the IP. Host-only networks can talk to the host machine as well as
  # any other machines on the same network, but cannot be accessed (through this
  # network interface) by any external networks.
  config.vm.network :private_network, ip: "33.33.33.10"


  config.vm.network :forwarded_port, guest: 5601, host: 5601



  config.vm.provision :chef_solo do |chef|
    chef.json = {
      "kibana" => {

      }
    }

    chef.run_list = [
        "recipe[apt::default]",
        "recipe[kibana::default]"
    ]
  end
end
