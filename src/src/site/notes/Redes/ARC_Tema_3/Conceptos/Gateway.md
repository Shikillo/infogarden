---
{"dg-publish":true,"permalink":"/redes/arc-tema-3/conceptos/gateway/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Pasarela","Puerta de Enlace","Voice Gateway"],"tags":["materia/redes","tema/protocolos"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_3/Fuente - ARC_Tema_3]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Gateway

> [!abstract] En una frase
> Dispositivo que **traduce entre redes completamente distintas** —diferentes protocolos, formatos de datos, lenguajes o arquitecturas— y, por su rol, se sitúa por **encima de la capa de transporte** del modelo OSI/TCP/IP.

## ¿Qué problema resuelve?
Comunicar dos redes **que no comparten pila de protocolos**. Un router basta mientras ambos lados usen IP, pero cuando los extremos hablan "idiomas" distintos (p. ej. Internet IP de un lado y red telefónica conmutada del otro) se necesita algo que **traduzca mensajes de un sistema a mensajes del otro**, no un simple reenvío de paquetes.

## Qué es
Según el material (p. 47): **"No se considera un dispositivo de interconexión LAN. Actúa como traductor entre sistemas que no utilizan los mismos protocolos de comunicaciones, formatos de estructuras de datos, lenguajes y/o arquitecturas. Se utilizan cuando las redes son completamente distintas; por ejemplo, una pasarela de telefónica conmutada"**. Es decir, va un paso más allá del [[Redes/ARC_Tema_3/Conceptos/Router\|Router]]: éste encamina paquetes IP; el gateway **convierte**.

Características que indica el material:
- **Nivel OSI/TCP/IP: ≥ 4 (transporte o superior)** (p. 47, 48).
- **Dominio de colisión**: lo **divide**. **Dominio de difusión**: también lo **divide** (tabla de p. 48).
- Ejemplo canónico citado: una **pasarela de VoIP** entre Internet (IP) y la **red telefónica conmutada (PSTN)** (p. 47).
- Formalmente **no es un dispositivo de interconexión LAN** (p. 47): su sitio son los límites entre tecnologías.

> [!example]
> Un **Voice Gateway** recibe una llamada de VoIP (RTP/UDP/IP sobre Ethernet) por un lado y, por el otro, la transforma en señalización y voz PCM sobre la PSTN. No reenvía los mismos paquetes: los **traduce** de una representación a otra, por eso opera a nivel transporte o superior (p. 47).

## Depende de
- [[Redes/ARC_Tema_3/Conceptos/Router\|Router]]: a menudo el gateway se usa junto a un router que mete el tráfico IP hasta el punto de traducción.
- [[Redes/ARC_Tema_1/Conceptos/Capa de Transporte\|Capa de Transporte]] / [[Redes/ARC_Tema_1/Conceptos/Capa de Aplicación\|Capa de Aplicación]] (Tema 1): el gateway necesita entender el contenido a este nivel para traducirlo.

## Permite entender
- Por qué muchas puertas de enlace **llevan en el nombre "pasarela"**: no reenvían, convierten.
- Por qué en la tabla resumen de p. 48 el gateway es el **único junto al router** que divide dominio de colisión *y* difusión (los dispositivos de nivel 2 expanden difusión).
- La diferencia entre "default gateway" (uso coloquial, que suele ser un router) y el gateway en sentido estricto como traductor de protocolos.

## Errores comunes
> [!warning]
> En configuración de red se llama "gateway por defecto" al **router de salida** de una LAN. Eso es un uso **coloquial** del término. En la clasificación del material, el gateway en sentido estricto es un **traductor entre protocolos distintos** (p. 47), no un simple enrutador IP.

## Autoevaluación
> [!question]- ¿Por qué el gateway opera "a nivel 4 o superior" cuando el router opera a nivel 3?
> Porque el router solo necesita leer la cabecera IP (nivel 3) para encaminar; el gateway tiene que **entender el contenido** para traducirlo (p. ej. convertir voz IP en voz PCM de PSTN), lo que requiere interpretar las capas de transporte, sesión y aplicación (p. 47, 48).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_3/Fuente - ARC_Tema_3\|Fuente - ARC_Tema_3]], p. 1, 7, 47, 48

## Mis notas
