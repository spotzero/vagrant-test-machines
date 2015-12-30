# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.require_version ">= 1.7.1"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.forward_agent = true
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end
  #

  config.vm.define "centos7" do |centos7|
    centos7.vm.box = "puppetlabs/centos-7.2-64-nocm"
    centos7.vm.provision :shell, inline: "if [ ! $(grep single-request-reopen /etc/sysconfig/network) ]; then echo RES_OPTIONS=single-request-reopen >> /etc/sysconfig/network && service network restart; fi"
  end

  config.vm.define "centos6" do |centos6|
    centos6.vm.box = "puppetlabs/centos-6.6-64-nocm"
    centos6.vm.provision :shell, inline: "if [ ! $(grep single-request-reopen /etc/sysconfig/network) ]; then echo RES_OPTIONS=single-request-reopen >> /etc/sysconfig/network && service network restart; fi"
  end

  config.vm.define "ubuntu1404" do |ubuntu1404|
    ubuntu1404.vm.box = "puppetlabs/ubuntu-14.04-64-nocm"
  end

  config.vm.define "ubuntu1204" do |ubuntu1204|
    ubuntu1204.vm.box = "puppetlabs/ubuntu-12.04-64-nocm"
  end

  config.vm.define "debian8" do |debian8|
    debian8.vm.box = "puppetlabs/debian-8.2-64-nocm"
  end

  config.vm.define "debian7"do |debian7|
    debian7.vm.box = "puppetlabs/debian-7.8-64-nocm"
  end

end
