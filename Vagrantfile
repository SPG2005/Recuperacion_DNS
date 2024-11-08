# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure("2") do |config|
  config.vm.define "DNSA" do |dns_a|
    dns_a.vm.box = "debian/bookworm64"
    dns_a.vm.network "private_network", ip: "192.168.57.10"
    dns_a.vm.hostname = "dnsa"
    dns_a.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y bind9 dnsutils
    SHELL
  end

  config.vm.define "DNSB" do |dns_b|
    dns_b.vm.box = "debian/bookworm64"
    dns_b.vm.network "private_network", ip: "192.168.57.11"
    dns_b.vm.hostname = "dnsb"
    dns_b.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y bind9 dnsutils
    SHELL
  end
end

end
