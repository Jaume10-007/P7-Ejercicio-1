# P7 - Ejercicio 1: Reproducción de audio desde memoria interna por I2S

## Descripción

Este ejercicio reproduce una muestra de audio almacenada en la memoria interna del ESP32-S3.

El audio está guardado como un array en el archivo `sampleaac.h`. El ESP32-S3 lee esa muestra desde memoria, la decodifica en formato AAC y la envía por I2S al amplificador MAX98357A. El MAX98357A convierte la señal digital I2S en una señal de audio que se reproduce por el altavoz.

## Material utilizado

- ESP32-S3-N16R8
- Amplificador I2S MAX98357A
- Altavoz
- Cables Dupont
- PlatformIO / VS Code

## Conexiones

```text
ESP32-S3 GPIO4 -> BCLK del MAX98357A
ESP32-S3 GPIO5 -> LRC / WS del MAX98357A
ESP32-S3 GPIO6 -> DIN / SD del MAX98357A

ESP32-S3 3V3   -> VIN / VCC del MAX98357A
ESP32-S3 GND   -> GND del MAX98357A

Altavoz +      -> salida + del MAX98357A
Altavoz -      -> salida - del MAX98357A
