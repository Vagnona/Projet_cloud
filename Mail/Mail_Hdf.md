Un serveur Consul et un serveur Nomad ont été provisionnés pour vous.
Cette machine est accessible par SSH :

    ssh -J student@185.155.93.67 ubuntu@192.168.70.118

Clé SSH privée pour accéder à la machine :

    -----BEGIN OPENSSH PRIVATE KEY-----
    b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAaAAAABNlY2RzYS
    1zaGEyLW5pc3RwMjU2AAAACG5pc3RwMjU2AAAAQQR0Pa8gnTcuLvDuazg0gG8WFMpgl7RB
    WKl4+Im1dbyk33hAPzC8OWKM2G0pLZ3veN9N23Xpq1pyajpdhcAg5wa1AAAAqFkjykFZI8
    pBAAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBHQ9ryCdNy4u8O5r
    ODSAbxYUymCXtEFYqXj4ibV1vKTfeEA/MLw5YozYbSktne94303bdemrWnJqOl2FwCDnBr
    UAAAAgdNKwDEIvqNjEnxFUdW1UgXDVqTOU3zvknMUEIvcAtWcAAAAPdWJ1bnR1QGtyaW1t
    ZXJpAQ==
    -----END OPENSSH PRIVATE KEY-----

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

Test:

    export CONSUL_HTTP_ADDR=https://consul-homme-de-fer.100do.se
    export NOMAD_ADDR=https://nomad-homme-de-fer.100do.se
    consul members
    nomad server members

Liste des proxy HTTPS:

    https://consul-homme-de-fer.100do.se -> http://172.16.2.5:8500
    https://nomad-homme-de-fer.100do.se -> http://172.16.2.5:4646
    https://homme-de-fer.100do.se -> http://172.16.3.5:8081
    https://*.homme-de-fer.100do.se -> http://172.16.3.5:8081
    https://baggersee.100do.se -> http://172.16.1.1:8080
    https://*.baggersee.100do.se -> http://172.16.1.1:8080
    https://elmerforst.100do.se -> http://172.16.1.10:8080
    https://*.elmerforst.100do.se -> http://172.16.1.10:8080
    https://krimmeri.100do.se -> http://172.16.1.18:8080
    https://*.krimmeri.100do.se -> http://172.16.1.18:8080