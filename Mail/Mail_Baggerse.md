La machine virtuelle baggersee vous a été affectée pour le projet de Cloud et Virtualisation.

Votre clé SSH privée :

    -----BEGIN OPENSSH PRIVATE KEY-----
    b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAaAAAABNlY2RzYS
    1zaGEyLW5pc3RwMjU2AAAACG5pc3RwMjU2AAAAQQQsDkVr314r4XOVdgR70UzOhN8a2cd/
    5LqWmc7acpxuJJLcCNRum0+WhFqfaA0ZPHFPSyuptBT/g6f+ewi+hDzvAAAAsI+MHKmPjB
    ypAAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBCwORWvfXivhc5V2
    BHvRTM6E3xrZx3/kupaZztpynG4kktwI1G6bT5aEWp9oDRk8cU9LK6m0FP+Dp/57CL6EPO
    8AAAAhANJ29ryO4O1f6FYIUoTRO4u74OxNiO0xPUvPjVraDxfbAAAAEHVidW50dUBiYWdn
    ZXJzZWUBAgMEBQYH
    -----END OPENSSH PRIVATE KEY-----

Ajoutez cette clé à votre agent SSH via la commande ssh-add :

    ssh-add ./id_ecdsa

La machine virtuelle n'est accessible que depuis le réseau de l'Université.
Connectez-vous à votre machine virtuelle via la machine bastion :

    ssh -J student@185.155.93.67 ubuntu@192.168.70.101

Pour simplifier la connexion par SSH, ajoutez cette section à votre fichier ~/.ssh/config

    Host bastion-cloud
      Hostname 185.155.93.67
      User student

    Host baggersee
      Hostname 192.168.70.101
      User ubuntu
      ProxyJump bastion-cloud

Vous pourrez ensuite vous connecter à la machine via :

    ssh baggersee

IP de l'interface VXLAN : 172.16.1.1/16
IP interne : 192.168.70.101
Nom d'hôte interne : baggersee.internal.100do.se

Les adresses suivantes proxy le traffic vers votre machine virtuelle sur le port 8080 (172.16.1.1:8080) :

 - https://baggersee.100do.se
 - https://*.baggersee.100do.se