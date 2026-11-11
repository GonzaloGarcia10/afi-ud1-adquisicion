# AFI - UD1: Adquisición de evidencias digitales

**Nombre:** Gonzalo García Vega  
**Actividad:** Adquisición de evidencias digitales  
**Objetivo:** Adquirir, preservar, verificar y documentar evidencias digitales de un equipo comprometido, manteniendo su integridad y garantizando la cadena de custodia.

---

## Índice

1. [Descripción del proyecto](#1-descripción-del-proyecto)
2. [Documentación de la adquisición](#2-documentación-de-la-adquisición)
3. [Cadena de custodia](#3-cadena-de-custodia)
4. [Hashes e integridad](#4-hashes-e-integridad)
5. [Capturas del procedimiento](#5-capturas-del-procedimiento)
6. [Evidencias adquiridas](#6-evidencias-adquiridas)
7. [Procedimientos realizados](#7-procedimientos-realizados)
8. [Incidencias y observaciones](#8-incidencias-y-observaciones)

---

## 1. Descripción del proyecto

Durante la actividad se realizaron diferentes procedimientos de adquisición y análisis de evidencias digitales, incluyendo la captura de memoria RAM, la adquisición de imágenes forenses de disco y USB, la recopilación de artefactos del sistema y la comprobación de la integridad mediante hashes SHA-256.

También se documentaron los procedimientos utilizados, las incidencias encontradas y los resultados obtenidos durante la práctica.

## 2. Documentación de la adquisición

Documentación correspondiente al proceso de adquisición de las evidencias:

- [Acta de adquisición](acta-adquisicion.pdf)

## 3. Cadena de custodia

Se han elaborado registros individuales para documentar la adquisición, las transferencias, los accesos y las devoluciones de cada evidencia.

- [Cadena de custodia - Imagen del disco](registro-cadena-custodia-imagendisco-EV03.pdf)
- [Cadena de custodia - Memoria RAM](registro-cadena-custodia-memoria-ram-EV01.pdf)
- [Cadena de custodia - Tráfico de red](registro-cadena-custodia-red-EV02.pdf)
- [Cadena de custodia - Pendrive USB](registro-cadena-custodia-usbencontrado-EV04.pdf)

## 4. Hashes e integridad

Se calcularon hashes SHA-256 de los archivos recopilados para permitir comprobar su integridad.

- [Manifiesto de hashes SHA-256](hashes/hashes.sha256)
- [Registro de bloqueo USB](hashes/bloqueo-usb.log)

Los hashes permiten verificar que los archivos no han sufrido modificaciones respecto al momento en el que se calcularon.

## 5. Capturas del procedimiento

Las capturas del desarrollo de la práctica se encuentran organizadas en dos carpetas:

- [Capturas del procedimiento](capturas/)
- [Capturas personales](capturasmias/)

Entre ellas se incluyen:

- Estado inicial del entorno.
- Comprobaciones relacionadas con el cifrado.
- Protección contra escritura del pendrive.
- Adquisición de las imágenes forenses.
- Localización de la marca en memoria RAM.
- Análisis del triaje.
- Localización de la marca en las imágenes del disco y del USB.

## 6. Evidencias adquiridas

Durante la práctica se obtuvieron las siguientes evidencias:

| Evidencia | Descripción |
|---|---|
| `PC-ADMIN.raw` | Imagen forense del disco del equipo analizado. |
| `FORENSE-06-20261031-181741.raw` | Volcado de memoria RAM. |
| `usbencontrado.E01` - `E05` | Imagen forense segmentada del pendrive adquirido. |
| `red.pcap` | Captura del tráfico de red. |
| `Prefetch/` | Artefactos relacionados con la ejecución de programas en Windows. |
| `SAM.hiv`, `SYSTEM.hiv`, `SOFTWARE.hiv` | Hives del Registro de Windows. |
| `Security.evtx`, `System.evtx` | Registros de eventos de Windows. |
| `config.plist` | Archivo de configuración recopilado durante la actividad. |

## 7. Procedimientos realizados

### 7.1. Recopilación de información y datos volátiles

Se realizó la recopilación de información del equipo mediante los procedimientos y scripts proporcionados para la actividad, obteniendo diferentes artefactos del sistema.

### 7.2. Adquisición de memoria RAM

Se obtuvo un volcado de memoria RAM mediante la herramienta utilizada durante la práctica.

Posteriormente, se analizaron las cadenas almacenadas en memoria para localizar la marca personal.

### 7.3. Adquisición de la imagen del disco

Se realizó la adquisición de la imagen forense del disco del equipo, obteniendo el archivo `PC-ADMIN.raw`.

La imagen se examinó desde CAINE, montando la partición correspondiente en modo de solo lectura.

### 7.4. Adquisición del pendrive

Se utilizó FTK Imager para adquirir una imagen forense del pendrive en formato E01.

La adquisición se dividió en cinco segmentos (`E01` a `E05`) y se verificó mediante las opciones de comprobación de FTK Imager.

También se documentó el procedimiento de protección contra escritura del dispositivo USB.

### 7.5. Búsqueda de la marca personal

Se realizaron búsquedas para localizar el fichero de marca en las diferentes evidencias:

- **Memoria RAM:** se localizó la marca `AFI-GonzaloGarcia-20261031`.
- **Imagen del disco:** se encontró el fichero `marca-gonzalogarcia.txt.txt` en el escritorio del usuario Administrador.
- **Imagen del pendrive:** se localizó el mismo fichero y se comprobó su contenido.
- **Artefactos del triaje:** se encontraron referencias al nombre del fichero en los archivos `Trace3.fx`, `Trace4.fx`, `Trace5.fx`, `Trace6.fx` y `Trace7.fx`, pertenecientes a `Prefetch/ReadyBoot`.

## 8. Incidencias y observaciones

No fue posible realizar la comprobación específica del `$MFT`, debido a que no se obtuvo este archivo durante la recopilación de artefactos.

Se documentaron las incidencias encontradas con KAPE y Velociraptor en Windows 7 y se realizó una búsqueda alternativa en los artefactos disponibles.

Asimismo, se prepararon copias de trabajo de las imágenes forenses originales para su utilización durante la siguiente unidad didáctica, manteniendo las imágenes maestras preservadas.

---

**Fin de la documentación - AFI UD1**