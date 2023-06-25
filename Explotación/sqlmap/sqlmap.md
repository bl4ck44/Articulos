# Sqlmap

<br>

<p align="center">
<img src="./Img/Logo.png" width="600px">
</p>

<br>

SQLMap es una herramienta de prueba de penetración de código abierto utilizada para detectar y explotar vulnerabilidades de inyección de SQL en aplicaciones web. Fue desarrollada en Python y se utiliza para automatizar el proceso de detección y explotación de vulnerabilidades en bases de datos relacionales.

La inyección de SQL es una técnica común utilizada por los hackers para obtener acceso no autorizado a una base de datos o para extraer información sensible de un sistema. SQLMap ayuda a identificar y explotar estas vulnerabilidades al analizar la estructura de una aplicación web y realizar una serie de pruebas automatizadas para detectar cualquier punto de inyección de SQL.

Algunas de las características de SQLMap incluyen la capacidad de enumerar bases de datos, tablas y columnas, extraer datos de la base de datos, obtener el sistema de gestión de bases de datos (SGBD) subyacente, ejecutar comandos en el sistema operativo subyacente, entre otras. También puede realizar ataques de fuerza bruta en credenciales de bases de datos y ejecutar scripts personalizados durante el proceso de prueba.

## Instalación:

```
sudo apt-get install sqlmap
```


## USO:

Enumerar todas las opciones y parámetros disponibles de SQLMap:

```mathematica
sqlmap --help
```

<br>

Detectar automáticamente la inyección de SQL en una URL específica:

```mathematica
sqlmap -u <URL>
```

<br>

Especificar un parámetro vulnerable en una URL:

```mathematica
sqlmap -u <URL> --param=<PARAMETER>
```

<br>

Probar diferentes tipos de inyección de SQL (booleano, tiempo, basado en errores, etc.):

```mathematica
sqlmap -u <URL> --technique=<TECHNIQUE>
```

<br>

Obtener información sobre la base de datos:

```mathematica
sqlmap -u <URL> --dbs
```

<br>

Enumerar todas las tablas de una base de datos:

```mathematica
sqlmap -u <URL> -D <DATABASE> --tables
```

<br>

Enumerar columnas de una tabla:

```mathematica
sqlmap -u <URL> -D <DATABASE> -T <TABLE> --columns
```

<br>

Extraer datos de una columna específica:

```mathematica
sqlmap -u <URL> -D <DATABASE> -T <TABLE> -C <COLUMN> --dump
```

<br>

Usar un archivo de carga útil personalizado:

```mathematica
sqlmap -u <URL> --payload-file=<FILE>
```