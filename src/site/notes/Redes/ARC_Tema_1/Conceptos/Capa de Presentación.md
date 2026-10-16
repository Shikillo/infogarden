---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/capa-de-presentacion/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Presentation Layer","Nivel 6","Capa 6"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Capa de Presentación

> [!abstract] En una frase
> Capa 6 del [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]]: se encarga de la **sintaxis y representación** de los datos (codificaciones de caracteres, cifrado); poco usada en la práctica, hasta el punto de que muchos protocolos la saltan.

## ¿Qué problema resuelve?
Que dos máquinas con representaciones internas distintas (por ejemplo, caracteres en EBCDIC frente a UTF-8, u orden de bytes diferentes) puedan entenderse: la capa de presentación traduce de la sintaxis del emisor a una sintaxis común y a la sintaxis del receptor.

## Qué es
Según el material (p. 27): **"No se utiliza de forma extensa. La encriptación a veces se hace en el nivel 2 o en el 6. Tipos de codificaciones: EBCDIC, UTF-8, etc."**. Es la capa 6 del modelo OSI, entre [[Redes/ARC_Tema_1/Conceptos/Capa de Sesión\|sesión]] (nivel 5) y [[Redes/ARC_Tema_1/Conceptos/Capa de Aplicación\|aplicación]] (nivel 7) (p. 22).

Características:
- Se ocupa de **sintaxis y representación de datos** (p. 29).
- Puede alojar el **cifrado**, aunque éste a menudo se hace en la [[Redes/ARC_Tema_1/Conceptos/Capa de Enlace de Datos\|capa 2]] (p. 27).
- Ejemplos de codificaciones citados: **EBCDIC**, **UTF-8** (p. 27).
- Ejemplos de pila en esta capa: **Presentación ISO**, **UTF-8** (p. 29).

> [!example]
> Un fichero de texto que un servidor codifica en UTF-8 y un cliente antiguo lee como EBCDIC necesitaría una traducción de presentación. En la práctica, los protocolos modernos (HTTP + MIME, por ejemplo) resuelven esto dentro de la propia [[Redes/ARC_Tema_1/Conceptos/Capa de Aplicación\|aplicación]] (p. 27, 30).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Capa de Sesión\|Capa de Sesión]]: le entrega el flujo de datos ya organizado en diálogos.
- [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]]: encaja aquí por ser la capa 6.

## Permite entender
- Por qué en **TCP/IP** no aparece como capa propia: queda absorbida en la [[Redes/ARC_Tema_1/Conceptos/Capa de Aplicación\|Capa de Aplicación]] (p. 30).

## Errores comunes
> [!warning]
> "Presentación" **no significa interfaz gráfica**. No tiene que ver con cómo se ve algo en pantalla; se refiere a cómo se **representa** una secuencia de bytes para que ambos extremos la interpreten igual (p. 27, 29).

## Autoevaluación
> [!question]- Si existe la capa 6, ¿por qué el material dice que "no se utiliza de forma extensa"?
> Porque la mayoría de los protocolos de aplicación (HTTP, SMTP, FTP…) definen ellos mismos su sintaxis y codificación, de modo que la función de presentación queda embebida dentro de la [[Redes/ARC_Tema_1/Conceptos/Capa de Aplicación\|Capa de Aplicación]]; TCP/IP ni siquiera la separa (p. 27, 30).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 22, 27, 29, 30

## Mis notas
