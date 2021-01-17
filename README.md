# infra_polytech
Infrastructure à attaquer

## Dépendances

- VirtualBox
- vagrant

## Instructions d'utilisation

Sur un système linux : 

1. Cloner le repository à l'aide de la commande suivante :  `git clone https://github.com/pveutin/infra_polytech.git`

    ``` console
    user@machine:~/Documents/Polytech $ git clone https://github.com/pveutin/infra_polytech.git                                            
    Clonage dans 'infra_polytech'...
    remote: Enumerating objects: 22, done.
    remote: Counting objects: 100% (22/22), done.
    remote: Compressing objects: 100% (21/21), done.
    remote: Total 22 (delta 8), reused 0 (delta 0), pack-reused 0
    Dépaquetage des objets: 100% (22/22), 10.22 Kio | 550.00 Kio/s, fait.
    ```
2. Entrer dans le dossier **infra_polytech** : 

    ``` console
    user@machine:~/Documents/Polytech $ cd infra_polytech
    user@machine:~/Documents/Polytech/infra_polytech $
    ```
    
3. Lancement de l'infrastructure à l'aide de la commande `vagrant up`
    > La machine **kali** dispose d'une interface réseau *bridgée* sur l'interface réseau de l'hôte, il faut donc choisir (en saisissant le nombre correspondant la bonne interface durant le déploiement). Dans l'exemple ci-dessous, elle est connectée sur l'interface *enxa4bb6df64b59* (**choix 1**).
    ``` console
    user@machine:~/Documents/polytech/infra_polytech $ vagrant up                                                                376  18:37:29  
    Bringing machine 'kali' up with 'virtualbox' provider...
    Bringing machine 'dvwa' up with 'virtualbox' provider...
    Bringing machine 'juiceshop' up with 'virtualbox' provider...
    ==> kali: Importing base box 'kalilinux/rolling'...
    ==> kali: Matching MAC address for NAT networking...
    ==> kali: Checking if box 'kalilinux/rolling' version '2020.4.0' is up to date...
    ==> kali: Setting the name of the VM: infra_polytech_kali_1610905200533_12559
    ==> kali: Clearing any previously set network interfaces...
    ==> kali: Available bridged network interfaces:
    1) enxa4bb6df64b59
    2) wlo1
    3) virbr0
    ==> kali: When choosing an interface, it is usually the one that is
    ==> kali: being used to connect to the internet.
        kali: Which interface should the network bridge to? 1

    [ Cropped ]
    [ Cropped ]
    [ Cropped ]

    ==> kali: Machine 'kali' has a post `vagrant up` message. This is a message
    ==> kali: from the creator of the Vagrantfile, and not from Vagrant itself:
    ==> kali: 
    ==> kali: VM kali Ok

    ==> dvwa: Machine 'dvwa' has a post `vagrant up` message. This is a message
    ==> dvwa: from the creator of the Vagrantfile, and not from Vagrant itself:
    ==> dvwa: 
    ==> dvwa: VM dvwa Ok

    ==> juiceshop: Machine 'juiceshop' has a post `vagrant up` message. This is a message
    ==> juiceshop: from the creator of the Vagrantfile, and not from Vagrant itself:
    ==> juiceshop: 
    ==> juiceshop: VM juiceshop Ok
    ```
