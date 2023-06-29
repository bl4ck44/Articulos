# Sytem OS

El campo TTL se utiliza principalmente para evitar que los paquetes circulen indefinidamente en la red en caso de que haya algún problema en la ruta de entrega. Cuando se envía un paquete, se establece un valor inicial en el campo TTL.

Un sistema operativo, TTL (Time To Live) se refiere a un campo que se encuentra en el encabezado de los paquetes IP (Internet Protocol). El campo TTL indica la cantidad máxima de saltos o enrutadores que un paquete puede realizar antes de ser descartado o eliminado de la red.

## Como identificar un sistema operativo mediante TTL

Primero creamos un script en bash con el siguiente codigo para identificar el sistema operativo:

```bash
#!/bin/bash

# ctrl_c
trampa ctrl_c INT
function ctrl_c(){
	echo -e "\n[+] Saliendo... "
	Salida 1
}

# comprobar args
if [ $# != '1' ];  entonces
	echo -e "\n[!] Uso: $0 HOST"
	Salida 1
Fi

# comprobar el análisis del valor TTL de la conexión
ping -c 1 $1 &>/dev/null
si [ $?  -ne 0 ];  entonces
	echo -e "\n[!] Comprueba tu conexión a Internet. "
	Salida 1
Fi

ttl=$(ping -c 1 $1 | awk '{print $2}' FS="ttl=" |  awk '{print $1}' | xargs)

# Guess OS por su IP
si [ $ttl -gt 0 ] && [ $ttl -lt 65 ];   entonces
	echo -e "$1 -> Linux"

ELIF [ $ttl -GT 64 ] && [ $ttl -LT 129 ];   entonces
	echo -e "$1 -> Windows"
	
más
    echo -e "$1 -> Sistema Desconocido"
Fi
```

## USO:

Para ejecutar el script:

```
./script.sh example.org
```