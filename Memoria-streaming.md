# Memoria de servicio de streaming

![Radio](img/radio.png)

Carlos Durán Román

2ASIR

# Índice



# Icecast2

### Introducción

# FFmpeg

### Introducción

Para esta práctica con FFmpeg, vamos a descargarnos un video y luego vamos a ver los datos que tenemos del video descargardo, luego cambiaremos los codecs y crearemos un fichero con un bitrate determinado.

### Ejercicio 1 Instalación de FFmpeg

Para instalar FFmpeg, vamos a utilizar el siguiente comando en nuestra máquina ubuntu

```
apt-get install ffmpeg
```

Una vez instalado, vamos a descargarnos un video y vamos a utilizar el siguinte comando para localizar la información que tiene el video descargado

```
ffprobe -v error -show_streams fichero.mp4
```

Y al usar el comando nos mostrará toda la información del video [Imágen](#ffprobe)

# Anexo

## ffprobe

<p align="center">
  <img src="img/ffprobe.png"  width="700px">
</p>
