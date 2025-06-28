# -- mode: ruby --
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "perk/ubuntu-2204-arm64"

    config.vm.network "forwarded_port", guest: 80, host: 8080

    config.vm.synced_folder ".", "/vagrant", type: "rsync"

    config.vm.provider "qemu" do |qe|
      qe.memory = "1024"
      qe.cpus = 1
      qe.name = "nginx - webserver"
    end

    config.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yml"
    end
end