---
{"dg-publish":true,"permalink":"/redes/arc-tema-2/conceptos/subcapa-mac/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Media Access Control","MAC","Control de Acceso al Medio"],"tags":["materia/redes","tema/protocolos"],"nivel":0,"fuentes":["[[Redes/ARC_Tema_2/Fuente - ARC_Tema_2]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Subcapa MAC

> [!abstract] En una frase
> Subcapa inferior de la **capa de enlace de datos** que **arbitra quién transmite y cuándo** sobre un canal compartido, para que varias estaciones puedan convivir sin pisarse.

## ¿Qué problema resuelve?
En una red con **enlace de difusión** (un cable coaxial, un medio inalámbrico) todas las estaciones comparten el mismo canal. Si dos emiten a la vez, sus señales se mezclan y ambas tramas se pierden: hay una **colisión**. La subcapa MAC es la pieza que decide **quién habla, cuándo y durante cuánto tiempo** para que el canal se aproveche sin bloqueos ni caos. Es, en el fondo, el "turno de palabra" de la red.

## Qué es
Según el material (p. 4), los enlaces se dividen en dos familias:

1. **Enlaces de difusión** (canal compartido): necesitan protocolo MAC.
2. **Enlaces punto a punto**: no lo necesitan, porque solo hay dos extremos.

La MAC es una **subcapa de la Capa de Enlace de Datos** del [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]] y es *"especialmente importante en LAN y en comunicación inalámbrica"* (p. 4). Las [[Redes/ARC_Tema_1/Conceptos/Red de Área Amplia (WAN)\|WAN]] usan punto a punto **con excepción de los enlaces por satélite**, que también comparten canal (p. 4).

El PDF distingue dos grandes estrategias para asignar el canal (p. 5):

- **Asignación estática**: la capacidad se **reparte a priori** entre usuarios (TDM, FDM). Funciona si el número de usuarios es fijo y el tráfico constante; mal si hay ráfagas o emisores que entran y salen (ejemplo: emisoras de radio FM).
- **Asignación dinámica**: el canal se asigna **según demanda**. El PDF enumera las premisas de este modelo (p. 5): tráfico independiente entre estaciones, **un único canal**, **colisiones observables**, tiempo continuo o ranurado, y con o sin detección de portadora.

Los protocolos de acceso múltiple que trata el tema (p. 6) son todos de asignación **dinámica**:

- [[Redes/ARC_Tema_2/Conceptos/ALOHA\|ALOHA]] (puro y ranurado).
- Acceso múltiple con detección de portadora: [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]].
- Protocolos libres de colisión: [[Redes/ARC_Tema_2/Conceptos/Protocolo de Mapa de Bits\|Protocolo de Mapa de Bits]], [[Redes/ARC_Tema_2/Conceptos/Protocolo de Paso de Testigo\|Protocolo de Paso de Testigo]].
- Protocolos de contención limitada y protocolos inalámbricos.

## Cómo podrías haberlo descubierto
Pon una sola radio en una sala: solo puede hablar uno. Si todos quieren hablar a la vez surgen opciones: *"cada uno habla en un minuto fijo"* (asignación estática, TDM), *"cada uno en una frecuencia"* (FDM), o *"el primero que vea silencio habla"* (asignación dinámica, CSMA). Cada regla trae **ventajas y problemas**: la estática desperdicia si alguien no habla, la dinámica choca cuando dos empiezan a la vez. Esa misma tensión, llevada a tramas de red sobre un cable compartido, es exactamente la que resuelve la MAC.

## Depende de
- *(raíz del tema)*: es el nodo base del que cuelgan todos los protocolos de acceso al medio.

## Permite entender
- [[Redes/ARC_Tema_2/Conceptos/ALOHA\|ALOHA]], [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]], [[Redes/ARC_Tema_2/Conceptos/Protocolo de Mapa de Bits\|Protocolo de Mapa de Bits]], [[Redes/ARC_Tema_2/Conceptos/Protocolo de Paso de Testigo\|Protocolo de Paso de Testigo]]: casos concretos.
- [[Redes/ARC_Tema_2/Conceptos/Ethernet\|Ethernet]]: su protocolo MAC históricamente ha sido CSMA/CD.
- Por qué las [[Redes/ARC_Tema_1/Conceptos/Red de Área Amplia (WAN)\|WAN]] no insisten tanto en la MAC: usan enlaces punto a punto.

## Ejemplo
> [!example]
> En Ethernet clásica (coaxial compartido, p. 20), 10 ordenadores están "colgados del mismo cable". La MAC se encarga de que, cuando dos quieren transmitir simultáneamente, detecten la colisión y vuelvan a intentarlo con esperas aleatorias ([[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]], p. 12-14). Sin MAC, el cable sería ingobernable.

## Errores comunes
> [!warning]
> **MAC no es toda la capa de enlace de datos**. El enlace de datos tiene dos subcapas: la MAC (acceso al medio) y la **LLC** (control de enlace lógico, IEEE 802.2), que se ocupa de direccionamiento y control. Confundirlas lleva a atribuir a la MAC funciones que no son suyas (p. 18).

> [!warning]
> La MAC **no evita** por sí sola todas las colisiones: las **detecta** y las **gestiona**. En CSMA/CD puede haber colisiones durante el período de contención (p. 14).

## Autoevaluación
> [!question]- ¿Por qué el PDF dice que la MAC importa especialmente en LAN e inalámbrico, y no tanto en WAN?
> Porque LAN e inalámbrico usan típicamente **enlaces de difusión** (canal compartido), que exigen arbitrar el acceso. Las WAN se basan en **enlaces punto a punto** entre routers, donde no hay más de dos extremos y la coordinación no es necesaria (p. 4).

> [!question]- Diferencia entre asignación estática y dinámica del canal.
> Estática: se **reparte el canal a priori** (TDM, FDM). Simple, pero ineficiente con tráfico de ráfagas o emisores variables. Dinámica: se **asigna según demanda**, con colisiones observables; necesaria para tráfico independiente y variable (p. 5).

## Contraste
> [!success] Verificado
> La definición de subcapa MAC, el reparto estática/dinámica y los protocolos citados se han contrastado con Wikipedia (*Medium access control*, *Multiple access protocol*) y coinciden con el material.

## Fuentes
- [[Redes/ARC_Tema_2/Fuente - ARC_Tema_2\|Fuente - ARC_Tema_2]], p. 3-6, 12-14, 18

## Mis notas
