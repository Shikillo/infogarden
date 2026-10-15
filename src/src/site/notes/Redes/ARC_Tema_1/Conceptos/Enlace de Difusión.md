---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/enlace-de-difusion/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Broadcast Link"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Enlace de Difusión

> [!abstract] En una frase
> Un **canal de comunicación compartido** por todas las máquinas de la red; cada paquete lleva un campo de destino que indica quién debe recibirlo.

## ¿Qué problema resuelve?
Permitir que **todos los nodos** en una red local compartan un mismo medio físico (como un cable coaxial o un medio inalámbrico) sin establecer conexiones individuales entre cada par.

## Qué es
Un enlace de **difusión** (broadcast) usa un **solo canal compartido**. Cada paquete enviado por cualquier máquina se propaga por todo el canal; cada destino **copia el paquete** si reconoce su propia dirección en el campo de destino. Ejemplo típico: redes locales pequeñas (Ethernet, WiFi tradicional).

Características:
- **Canal único y compartido**
- **Campo de dirección** obligatorio para identificar destino
- Sin rutas preconfiguradas: todos reciben físicamente
- Eficiente para redes pequeñas, pero con colisiones si hay mucho tráfico simultáneo

> [!example]
> En una red Ethernet con *hub* (no *switch*), el paquete que envía A llega físicamente a B, C y D; solo la máquina cuyo MAC coincida con la dirección destino procesa el paquete (p. 7).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Red de Área Local (LAN)\|Red de Área Local (LAN)]]: contexto típico de difusión

## Permite entender
- [[Redes/ARC_Tema_1/Conceptos/Enlace Punto a Punto\|Enlace Punto a Punto]]: contraste con enlaces dedicados por par
- [[Redes/ARC_Tema_1/Conceptos/Topología de Red\|Topología de Red]]: difusión se asocia a topologías como bus o estrella con hub

## Errores comunes
> [!warning]
> No confundir difusión con "broadcast como destino a todos" (como un mensaje de red). Aquí la difusión es **propiedad del enlace físico**: todos reciben la señal, aunque el paquete esté dirigido a uno solo.

## Autoevaluación
> [!question]- ¿Por qué un enlace de difusión requiere un campo de dirección en cada paquete?
> Porque todos los nodos reciben físicamente la señal del canal compartido; sin dirección, cada nodo no podría distinguir si el paquete es para él o para otro (p. 7).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 7-8

## Mis notas