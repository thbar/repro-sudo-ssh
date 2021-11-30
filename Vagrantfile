# vagrant up
# ssh vagrant@192.168.34.10

# TODO: edit /etc/sudoers to require pass for sudo groups (to which vagrant user belongs)

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end
  config.vm.define :repro_ssh do |node|
    node.vm.network "private_network", ip: "192.168.34.10"
    # TODO: edit instead of delete, because deleting
    # apparently forbids SSH'ing into the box
    # node.vm.provision "shell",
    #   inline: "sudo rm /etc/sudoers.d/99_vagrant",
    #   run: "once"
  end
end
