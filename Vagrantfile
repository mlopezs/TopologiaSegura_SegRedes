# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # - - - - - Router - - - - - #

  config.vm.define "router" do |router|

    router.vm.box = "debian/jessie64"
    router.vm.hostname = "router"

    router.vm.network "public_network", bridge: "wlp5s0", use_dhcp_assigned_default_route: true # Asegurarse que el sistema nativo y el router están en la misma subred.
    router.vm.network "private_network", ip: "10.0.0.1", virtualbox__intnet: "DMZ_Network"
    router.vm.network "private_network", ip: "192.168.0.1", virtualbox__intnet: "MZ_Network"

    router.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbook-router.yml"
    end

  end

  # - - - - - Servidor - - - - - #

  config.vm.define "servidor_dmz" do |servidor_dmz|

    servidor_dmz.vm.box = "debian/jessie64"
    servidor_dmz.vm.hostname = "servidordmz"

    servidor_dmz.vm.network "private_network", ip: "10.0.0.2", virtualbox__intnet: "DMZ_Network"

    servidor_dmz.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbook-servdmz.yml"
    end

  end

  # - - - - - Host MZ - - - - - #

  config.vm.define "pc_mz" do |pc_mz|

    pc_mz.vm.box = "debian/jessie64"
    pc_mz.vm.hostname = "empleadopcmz"

    pc_mz.vm.network "private_network", type: "dhcp", virtualbox__intnet: "MZ_Network"

    pc_mz.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbook-pcmz.yml"
    end

  end

end
