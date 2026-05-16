# P7 Ejercicio 1

## Salida por el puerto serie

Al arrancar, el monitor serie a 115200 baudios muestra el titulo del ejercicio,
los pines usados para el MAX98357A y un mensaje indicando que empieza la
reproduccion de la muestra AAC guardada en memoria interna.

Cuando termina la reproduccion, el programa escribe repetidamente:

```text
Sound Generator
```

## Funcionamiento

El archivo `sampleaac.h` contiene una muestra de audio AAC convertida a una
matriz de bytes en memoria de programa. `AudioFileSourcePROGMEM` lee esa
matriz como si fuera un fichero, `AudioGeneratorAAC` la decodifica y
`AudioOutputI2S` envia las muestras digitales al amplificador MAX98357A por el
bus I2S.

La conexion usada es:

```text
ESP32-S3 GPIO4 -> BCLK del MAX98357A
ESP32-S3 GPIO5 -> LRC/WS del MAX98357A
ESP32-S3 GPIO6 -> DIN/SD del MAX98357A
GND          -> GND
3V3/VIN      -> alimentacion del modulo
```
