# -*- mode: ruby -*-
# vi: set ft=ruby :
IMAGE_NAME = "centos/7"


Vagrant.configure("2") do |config|
    config.vm.box = IMAGE_NAME
    config.vm.network "forwarded_port", guest: 80, host: 8080
    config.vm.network "forwarded_port", guest: 8043, host: 8043
    config.vm.network "forwarded_port", guest: 22, host: 8022
    config.vm.provider "virtualbox" do |v|
        v.memory = 1024
        v.cpus = 2
    end
    config.vm.hostname = "podman-host"
    $script = <<-SCRIPT
    yum update -y
    yum install podman -y
    yum install skopeo -y
    yum install buildah -y
    date > /etc/vagrant_provisioned_at
    bash -c 'echo 10000 > /proc/sys/user/max_user_namespaces'
    bash -c "echo vagrant:110000:65536 > /etc/subuid"
    bash -c "echo vagrant:110000:65536 > /etc/subgid"

    SCRIPT
    config.vm.provision "shell", inline: $script
end

