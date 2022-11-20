# Ecaneo de directorios web con dirsearch

<br>

<p align="center">
<img src="./Img/logotipo.png">
</p>

<br>
Dirsearch es un escáner de directorios para aplicaciones web (diseñado en Python), que ayudara a un hacker ético a búscar información de un sitio web.

<br>

## Instalación

```
sudo apt-get install dirsearch
```

<br>

## USO

Para buscar directorios web usamos el siguiente comando:

```
dirsearch -u [url]
```

Ejemplo:

```
dirsearch -u https://www.google.com/ -e txt,php,html -x 404
```

**-u = URL Target / -e = Extensiones / -x = Estados excluidos**

<br>

<p align="center">
<img src="./Img/Ejemplo.png">
</p>

<br>

Una vez que acabe de escanear se generará de manera automática un archivo del escaneo realizado, en la carpeta **reports**, archivado y ordenado por target y fecha.