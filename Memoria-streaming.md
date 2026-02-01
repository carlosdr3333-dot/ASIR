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
  - [Instalación FFmpeg](#Instalación-de-FFmpeg)
  - [Metadatos con FFmpeg](#Metadatos-con-FFmpeg)
  - [Cambio de contenedor](#Cambio-de-contenedor)
  - [Cambio de códecs](#Cambio-de-códecs-y-comparación)
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

### Instalación-de-FFmpeg

Para instalar FFmpeg, vamos a utilizar el siguiente comando en nuestra máquina ubuntu

```
apt-get install ffmpeg
```

### Metadatos-con-FFmpeg

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

Aqui podemos comprobar que ha funcionado correctamente [Imágen](#Cambio-contenedor)

Podemos comprobar mediante esta imágen, que al cambiar de contenedor el video que tenemos, no ha vaariado el tamañao de este [Imágen](#Peso-imagenes)

Este comando no me ha tardado y no me ha consumido casi nada de CPU, porque este comando se encarga de copiar los datos del video MP4 y los vuelve a guardar como MKV. Como no tiene que descomprimir ni volver a comprimir, solo tiene que leer y escribir datos en el disco.

### Cambio-de-códecs-y-comparación

Primero vamos a crear un archivo en H.264 con un bitrate de 2Mbps del video anterior con el siguiente comando

```
ffmpeg -i big-buck-bunny-1080p-30sec.mp4 -c:v libx264 -b:v 2M -c:a copy big-buck-bunny-1080p-30sec-h264_2mbps.mp4
```

Con este imagen se puede comprobar que ha funcionado correctamente [Imágen](#h264.png)

Y ahora vamos a hacer lo mismo, pero con H.265

```
ffmpeg -i big-buck-bunny-1080p-30sec.mp4 -c:v libx265 -b:v 2M -c:a copy big-buck-bunny-1080p-30sec-h265_2mbps.mp4
```

Con este imagen se puede comprobar que ha funcionado correctamente [Imágen](#h265.png)

Ahora, vamos a comparar varios archivos, el video h.264 va a tirones, pero el h.265 va mucho mejor, esto es así ya que h.265 es un códec más eficiente, porque utiliza una compresión que permite aprovechar el bitrate. Como tienen la misma tasa de bits, H.265 reduce los artefactos visibles, sobretodo en las escenas con mucho movimiento, esto mantiene más detalle y una imagen más limpia.

Ahora vamos a comparar el peso de los dos archivos, podemos observar que el video H.265 pesa un poco mas que el H.264, aunque la diferencia sea muy mínima [Imágen](#Peso-codec)

### Simulacion-streaming



# Anexo

## ffprobe

<p align="center">
  <img src="img/ffprobe.png"  width="700px">
</p>

## Cambio-contenedor

<p align="center">
  <img src="img/Cambio-contenedor.png"  width="700px">
</p>

## Peso-imagenes

<p align="center">
  <img src="img/Peso-imagenes.png"  width="700px">
</p>

## H264

<p align="center">
  <img src="img/h264.png"  width="700px">
</p>

## H265

<p align="center">
  <img src="img/h265.png"  width="700px">
</p>

## Peso-codec

<p align="center">
  <img src="img/Peso-codec.png"  width="700px">
</p>
