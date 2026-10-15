---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/capa-de-red/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Network Layer","Nivel 3","Capa 3"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Capa de Red

> [!abstract] En una frase
> Capa 3 del [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]]: **enrutamiento de paquetes** entre redes distintas; es donde vive **IP** en TCP/IP. Unidad de datos: el **paquete**.

## ¿Qué problema resuelve?
Hacer llegar un paquete de origen a destino **cuando el origen y el destino no están en la misma red**: elegir por qué nodos pasar (encaminamiento) y usar un direccionamiento global que funcione aunque las redes atravesadas sean de tecnologías distintas.

## Qué es
Según el material (p. 25): **"Define el protocolo IP en el modelo TCP/IP. Especifica el enrutado de los paquetes. Hay otros protocolos de nivel 3: IPX. IP e IPX pueden coexistir en la misma red. La unidad de datos son los paquetes"**. Es la capa 3 del modelo OSI, por encima de la [[Redes/ARC_Tema_1/Conceptos/Capa de Enlace de Datos\|Capa de Enlace de Datos]] (nivel 2) y por debajo de la [[Redes/ARC_Tema_1/Conceptos/Capa de Transporte\|Capa de Transporte]] (nivel 4) (p. 22).

Características que indica el material:
- Protocolos típicos: **IP** (TCP/IP) y **IPX** (p. 25); **X.25 Pkt** se cita como ejemplo en p. 29.
- Puede haber **varios protocolos de nivel 3 coexistiendo** en la misma red (IP + IPX) (p. 25).
- Su misión descriptiva en p. 29 es **"Enrutamiento no fiable"**: la fiabilidad extremo a extremo la añade la capa superior ([[Redes/ARC_Tema_1/Conceptos/Capa de Transporte\|transporte]]).
- Unidad de datos: **paquetes** (p. 25).

> [!example]
> Un host envía un paquete IP a una dirección de otra red. La capa de red consulta su tabla de rutas, elige el **router** vecino al que entregar el paquete, y así hasta llegar al destino, con decisiones independientes en cada salto (p. 25).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Capa de Enlace de Datos\|Capa de Enlace de Datos]]: le proporciona un canal libre de errores entre nodos vecinos; sobre ese enlace, la red hace saltos.
- [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]]: encaja aquí por ser la capa 3.

## Permite entender
- **[[Redes/ARC_Tema_3/Conceptos/Router\|Router]]** (Tema 3): es el dispositivo que opera en esta capa, mirando la dirección IP destino para decidir por qué interfaz reenvía.
- **[[Redes/ARC_Tema_3/Conceptos/IP y ARP\|IP y ARP]]** (Tema 3): IP es el protocolo canónico de esta capa; ARP la conecta hacia abajo con la capa 2.
- Por qué TCP/IP mantiene esta capa con el mismo nombre y función que OSI (p. 30).

## Errores comunes
> [!warning]
> La capa de red **no garantiza la entrega**: en p. 29 se describe como "enrutamiento **no fiable**". Confundir esto es asumir que IP entrega siempre; es TCP (en la [[Redes/ARC_Tema_1/Conceptos/Capa de Transporte\|capa 4]]) quien añade esa garantía, no la capa de red.

## Autoevaluación
> [!question]- ¿Qué diferencia hay entre lo que decide la [[Redes/ARC_Tema_1/Conceptos/Capa de Enlace de Datos\|capa 2]] y lo que decide la capa 3?
> La capa 2 mueve una trama **entre dos nodos vecinos** (saltos de un enlace); la capa 3 decide la **ruta de nodos** entre el origen y el destino globales. Capa 2: salto; capa 3: trayecto completo (p. 24, 25).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 22, 25, 29, 30

## Mis notas
