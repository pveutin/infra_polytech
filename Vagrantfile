# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

Vagrant.configure("2") do |config|
  # Configuration de la VM KALI
  config.vm.define "kali" do |kali|
    kali.vm.hostname = "kali"
    kali.vm.box = "kalilinux/rolling"
    
    kali.vm.network "private_network", ip: "192.168.33.42"
    kali.vm.network "public_network"

    kali.vm.provision "shell", inline: <<-SHELL
	sed -ie '/^XKBLAYOUT=/s/\".*\"/\"fr\"/' /etc/default/keyboard && udevadm trigger --subsystem-match=input --action=change
        timedatectl set-timezone Europe/Paris
        ln -sf /usr/share/zoneinfo/Europe/Paris /etc/localtime                 
        export $(dbus-launch)
        xfconf-query -c xfce4-desktop -p /backdrop/screen0/monitorVirtual1/workspace0/last-image -s /vagrant/kali_files/wallpaper.jpg
    SHELL

    kali.vm.post_up_message = "VM kali Ok"
  end
  # Fin de la config de KALI


  # Configuration de la VM DVWA
  config.vm.define "dvwa" do |dvwa|
    dvwa.vm.hostname = "dvwa"
    dvwa.vm.box = "mmckinst/dvwa"
    dvwa.vm.provider "virtualbox" do |v|
	v.cpus = 2
    end
    dvwa.vm.provision "file", source: "crontab", destination:"~/crontab"
    dvwa.vm.provision "shell", inline: <<-SHELL2
        echo "www-data ALL=(ALL, !root) NOPASSWD:/bin/bash">> /etc/sudoers 
        mv crontab /etc/crontab
        chown root:root /etc/crontab
        chmod 600 /etc/crontab
	service cron restart
    SHELL2 
    dvwa.vm.network "private_network", ip: "192.168.33.11"
    dvwa.vm.post_up_message = "VM dvwa Ok"  
  end
  # Fin de la config VM DVWA


  # Configuration de la VM Juice Shop
  config.vm.define "juiceshop" do |juiceshop|
    juiceshop.vm.hostname = "juice.sh"
    juiceshop.vm.box = "ubuntu/xenial64"
  
    juiceshop.vm.network "private_network", ip: "192.168.33.10"
    
    juiceshop.vm.provision "file", source: "./juice_files/default.conf", destination: "/tmp/juice-shop/default.conf"
    juiceshop.vm.provision :shell, path: "./juice_files/bootstrap.sh"

    juiceshop.vm.post_up_message = "VM juiceshop Ok"
  end
  # Fin de la config Juice Shop

end

