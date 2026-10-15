---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/capa-de-sesion/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Session Layer","Nivel 5","Capa 5"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Capa de Sesión

> [!abstract] En una frase
> Capa 5 del [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]]: permite a dos usuarios establecer una **sesión** entre sus aplicaciones para servicios como **control de diálogo**, **administración de testigos** y **sincronización**.

## ¿Qué problema resuelve?
Dar a dos aplicaciones una conversación con **estado**: quién habla ahora, dónde se quedó la conversación si se corta, cómo reanudarla desde el último punto de sincronización. Sin esta capa, cada mensaje sería independiente y recuperarse de una caída obligaría a empezar de cero.

## Qué es
Según el material (p. 27): **"Permite a usuarios establecer sesiones para servicios como control de diálogo, administración de testigos o sincronización"**. Es la capa 5 del modelo OSI, por encima del [[Redes/ARC_Tema_1/Conceptos/Capa de Transporte\|transporte]] y por debajo de la [[Redes/ARC_Tema_1/Conceptos/Capa de Presentación\|presentación]] (p. 22).

Características que indica el material:
- Ofrece **control de diálogo**, **administración de testigos** y **sincronización** (p. 27).
- Permite **identificar la sesión de forma independiente a la aplicación** utilizada (p. 27).
- **Algunos protocolos de nivel de aplicación gestionan las sesiones sin necesidad de esta capa** (p. 27): por eso en TCP/IP la capa de sesión no existe como tal (p. 30).
- Se asocia a **TCP, no a UDP**: TCP la aprovecha; UDP no la usa (p. 27).
- Ejemplos de pila citados en p. 29: **Sesiones ISO**, con la frase "Sync Points and Dialogs".

> [!example]
> En una transferencia larga protegida por puntos de sincronización, si se corta la conexión se puede reanudar desde el último punto de sync en lugar de retransmitir desde el principio: ese servicio lo da, en modelo OSI, la capa de sesión (p. 27, 29).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Capa de Transporte\|Capa de Transporte]]: le proporciona un canal extremo a extremo fiable (TCP).
- [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]]: encaja aquí por ser la capa 5.

## Permite entender
- La diferencia **TCP/IP ↔ OSI**: en TCP/IP esta capa queda absorbida en la [[Redes/ARC_Tema_1/Conceptos/Capa de Aplicación\|Capa de Aplicación]] (p. 30).

## Errores comunes
> [!warning]
> Una "sesión" en esta capa **no es** la sesión de un usuario en una web (cookies, login). Es un servicio de nivel 5 del modelo OSI entre dos entidades de aplicación. La "sesión HTTP" la gestiona la propia aplicación, no esta capa (p. 27).

## Autoevaluación
> [!question]- ¿Por qué TCP usa capa de sesión pero UDP no?
> Porque UDP está pensado para ser mínimo (sin estado, sin orden, sin entrega garantizada); añadir diálogo o sincronización rompería ese diseño. TCP, en cambio, mantiene un flujo con estado al que la capa de sesión encaja de forma natural (p. 26-27).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 22, 27, 29, 30

## Mis notas
