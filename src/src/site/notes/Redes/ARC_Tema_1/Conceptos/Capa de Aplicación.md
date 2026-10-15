---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/capa-de-aplicacion/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Application Layer","Nivel 7","Capa 7"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Capa de Aplicación

> [!abstract] En una frase
> Capa 7 del [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]]: la capa superior donde reside toda la funcionalidad visible al usuario y donde los programas de red (correo, web, transferencia de ficheros) producen la interacción con las personas.

## ¿Qué problema resuelve?
Dar a los programas (navegador, cliente de correo, FTP…) una interfaz uniforme para comunicarse por la red sin preocuparse de rutas, errores de línea ni formato binario: todo eso lo resuelven las capas inferiores.

## Qué es
Según el material (p. 27): **"Reside la funcionalidad de toda la comunicación. Gestiona los datos a un nivel mayor y produce la interacción con el usuario"**. Es la capa más alta del modelo OSI. En ella viven los **protocolos de aplicación** que usan los programas de usuario; por eso también se la llama **Nivel 7**.

Características que indica el material:
- Es la capa superior del modelo OSI (p. 22).
- Los datos se tratan al nivel más alto (mensajes de usuario, no bits ni paquetes).
- Es donde ocurre la **interacción con el usuario** (p. 27).
- Algunos de sus protocolos **asumen la gestión de la [[Redes/ARC_Tema_1/Conceptos/Capa de Sesión\|Capa de Sesión]]**, por lo que ésta puede quedar sin usar (p. 27).

> [!example]
> Según p. 29, protocolos típicos de esta capa: **Telnet**, **FTP**, **Mail**. En TCP/IP esta capa agrupa lo que en OSI se reparte entre aplicación, [[Redes/ARC_Tema_1/Conceptos/Capa de Presentación\|presentación]] y [[Redes/ARC_Tema_1/Conceptos/Capa de Sesión\|sesión]] (p. 30).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Capa de Presentación\|Capa de Presentación]]: le entrega los datos ya codificados en una sintaxis común.
- [[Redes/ARC_Tema_1/Conceptos/Capa de Sesión\|Capa de Sesión]]: le proporciona el diálogo, aunque muchas aplicaciones no la usan.
- [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]]: encaja aquí por ser la capa 7.

## Permite entender
- La correspondencia **OSI ↔ TCP/IP**: en TCP/IP, "Aplicación" absorbe las capas 5, 6 y 7 (p. 30).

## Errores comunes
> [!warning]
> La capa de aplicación **no es la aplicación del usuario** (el navegador, Outlook…), sino el **protocolo** que estas usan (HTTP, SMTP, FTP). El programa es el *proceso*; la capa de aplicación es el *lenguaje de red* que ese proceso habla.

## Autoevaluación
> [!question]- ¿Por qué en TCP/IP la capa de aplicación es más "ancha" que en OSI?
> Porque fusiona las capas 5, 6 y 7 del OSI (sesión, presentación y aplicación): TCP/IP delega la codificación de datos y la gestión de sesiones a los propios protocolos de aplicación (p. 27, 30).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 22, 27, 29, 30

## Mis notas
