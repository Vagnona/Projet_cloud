# VM

## Baggersee
Pour le cloud et virt

    ssh baggersee

IP de l'interface VXLAN : 172.16.1.1/16  
IP interne : 192.168.70.101  
Nom d'hôte interne : baggersee.internal.100do.se  

Les adresses suivantes proxy le traffic vers votre machine virtuelle sur le port 8080 (172.16.1.1:8080) :  

 - https://baggersee.100do.se
 - https://*.baggersee.100do.se

## Homme de fer
Un serveur Consul et un serveur Nomad nous on été attribué.

    ssh hdf

    IP interne utilisée par Consul et Nomad : 172.16.2.5/16
    Console Nomad : <https://nomad-homme-de-fer.100do.se/>
    Console Consul : <https://consul-homme-de-fer.100do.se/>

    Un bucket S3 a été provisionné pour vous :
        Serveur : <https://s3.100do.se/>
        Console : <https://s3-console.100do.se/>
        Access Key ID : homme-de-fer
        Secret Access Key : XIbckNFkdxqc7AtzrxnP

    Un accès à RabbitMQ a été provisionné pour vous :
    URL : <amqp://queue.internal.100do.se:5672/homme-de-fer>
        Console : <https://queue.100do.se/>
        Username : homme-de-fer
        Password : Fs1QBVZO3yTvzbbwdPFH


    IP flottante: 172.16.3.5/16

    Proxy HTTPS vers l'IP flottante: <https://homme-de-fer.100do.se/> et <https://nimporte.homme-de-fer.100do.se/>

## VPN 
    
    sudo openfortivpn vpn.unistra.fr:443 -u vandrianandrasan  
    while [ 1 ]; do sl ; done 
    

