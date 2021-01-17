# infra_polytech
Infrastructure à attaquer

## Dépendances

- VirtualBox
- vagrant

## Instructions d'utilisation

Sur un système linux : 

1. Cloner le repository : `git clone https://github.com/pveutin/infra_polytech`
2. Lancement de l'infrastructure : `vagrant up`
3. La machine **kali** dispose d'une interface réseau *bridgée* sur l'interface réseau de l'hôte, il faut donc choisir (en saisissant le nombre correspondant la bonne interface durant le déploiement) 
    - Exemple avec l'interface *enxa4bb6df64b59* (**choix 1**) ci-dessous : 
```
$user@machine:~$ vagrant up kali     
Bringing machine 'kali' up with 'virtualbox' provider...
==> kali: Importing base box 'kalilinux/rolling'...
==> kali: Matching MAC address for NAT networking...
==> kali: Checking if box 'kalilinux/rolling' version '2020.4.0' is up to date...
==> kali: Setting the name of the VM: infra_kali_1610894690184_68874
==> kali: Clearing any previously set network interfaces...
==> kali: Available bridged network interfaces:
1) enxa4bb6df64b59
2) wlo1
3) virbr0
==> kali: When choosing an interface, it is usually the one that is
==> kali: being used to connect to the internet.
    kali: Which interface should the network bridge to? 1
==> kali: Preparing network interfaces based on configuration...
    kali: Adapter 1: nat
    kali: Adapter 2: hostonly
    kali: Adapter 3: bridged
==> kali: Forwarding ports...
    kali: 22 (guest) => 2222 (host) (adapter 1)
==> kali: Running 'pre-boot' VM customizations...
==> kali: Booting VM...
==> kali: Waiting for machine to boot. This may take a few minutes...
    kali: SSH address: 127.0.0.1:2222
    kali: SSH username: vagrant
    kali: SSH auth method: private key
    kali: 
    kali: Vagrant insecure key detected. Vagrant will automatically replace
    kali: this with a newly generated keypair for better security.
    kali: 
    kali: Inserting generated public key within guest...
    kali: Removing insecure key from the guest if it's present...
    kali: Key inserted! Disconnecting and reconnecting using new SSH key...
==> kali: Machine booted and ready!
==> kali: Checking for guest additions in VM...
==> kali: Setting hostname...
==> kali: Configuring and enabling network interfaces...
==> kali: Mounting shared folders...
    kali: /vagrant => /home/rooxy/Documents/Polytech/infra
==> kali: Running provisioner: shell...
    kali: Running: inline script

==> kali: Machine 'kali' has a post `vagrant up` message. This is a message
==> kali: from the creator of the Vagrantfile, and not from Vagrant itself:
==> kali: 
==> kali: VM kali Ok

```
