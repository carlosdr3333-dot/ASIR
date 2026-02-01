# Memoria de servicio de streaming

![Radio](img/radio.png)

Carlos Durán Román

2ASIR

# Índice

- [Icecast2](#Icecast2)
  - [Introducción](#Introducción)
  - [Servidor de streaming](#Servidor-de-streaming)
- [FFmpeg](#FFmpeg)
  - [Introducción](#Introducción)
  - [Instalación-FFmpeg](#Instalación-de-FFmpeg)
  - [Cambio de contenedor](Cambio-de-contenedor)
- [Anexo](#Anexo)

# Icecast2

### Introducción

Para esta práctica vamos a utilizar icecast2, el objetivo es crear una radio online para que todos los oyentes que se conecten escuches lo que yo quiera

### Servidor-de-streaming

Para instalar icecast2 vamos a utilizar el siguiente comando en nuestro ubuntu

```
apt-get install icecast2
```

Al poner este comando, nos aparecerá una pantalla morada, en la primera pantalla le daremos que si, en la segunda nos saldrá que pongamos un nombre al servidor, lo dejaremos por defecto o también lo podemos cambiar, la tercera pantalla será la contraseña, eso pondremos la que queramos, nos lo pedirá 3 veces mas, una vez hecho todo esto, se instalará icecast2

# FFmpeg

### Introducción

Para esta práctica con FFmpeg, vamos a descargarnos un video y luego vamos a ver los datos que tenemos del video descargardo, luego cambiaremos los codecs y crearemos un fichero con un bitrate determinado.

### Ejercicio1-Instalación-de-FFmpeg

Para instalar FFmpeg, vamos a utilizar el siguiente comando en nuestra máquina ubuntu

```
apt-get install ffmpeg
```

Una vez instalado, vamos a descargarnos un video y vamos a utilizar el siguinte comando para localizar la información que tiene el video descargado

```
ffprobe -v error -show_streams fichero.mp4
```
<a name="vuelta1"></a>

Y al usar el comando nos mostrará toda la información del video [Imágen](#ffprobe) 

### Cambio-de-contenedor

Ahora vamos a cambiar el contenedor de .mp4 a .mkv con el siguiente comando

```
ffmpeg -i big-buck-bunny-1080p-30sec.mp4 -c:v copy -c:a copy big-buck-bunny-1080p-30sec.mkv
```

# Anexo

## ffprobe

<p align="center">
  <img src="img/ffprobe.png"  width="700px">
</p>

