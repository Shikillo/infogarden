---
{"dg-publish":true,"permalink":"/redes/arc-tema-3/conceptos/repetidor-y-hub/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Repetidor","Hub","Repeater","Concentrador"],"tags":["materia/redes","tema/protocolos"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_3/Fuente - ARC_Tema_3]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Repetidor y Hub

> [!abstract] En una frase
> Dispositivos de **nivel 1 (físico)** que **amplifican y regeneran los bits** que reciben, sin entender tramas; el **hub** es simplemente un **repetidor multipuerto**, y ambos **expanden el dominio de colisión y el de difusión**.

## ¿Qué problema resuelve?
Un cable Ethernet largo atenúa la señal: a partir de cierta distancia los bits llegan demasiado débiles o deformados para ser leídos. El **repetidor** regenera la señal; el **hub** generaliza la idea a varios puertos para construir redes en topología estrella sin tener que correr un cable larguísimo entre máquinas.

## Qué es

**Repetidor** (p. 8): **"Dispositivo hardware encargado de amplificar, regenerar y retemporizar los bits. Permite que los bits viajen a mayor distancia a través de los medios. No entiende de formatos, trabaja a nivel de bit. No filtra tráfico de Red"**. Trabaja en el **Nivel 1 (Físico)** (p. 8).

**Hub** (p. 9): **"Posee diferentes puertos, retransmitiendo cada bit recibido por uno de los puertos a los demás puertos. El Hub se considera un repetidor multipuerto. Se utiliza para implementar redes de topología estrella y ampliación de la red LAN. Es un dispositivo con topología en estrella pero con lógica de Bus. Proporcionan un ancho de banda compartido (10M, 100M). No entiende de formatos, trabaja a nivel de bit"**. También opera en **Nivel 1 (Físico)** (p. 9).

Comportamiento resumido (p. 10 y tabla p. 48):
- **Dominio de colisión**: lo **expanden**. Varias estaciones conectadas al mismo hub comparten el mismo medio lógico y pueden colisionar.
- **Dominio de difusión**: lo **expanden**. Un hub replica cualquier trama por todos sus puertos.
- **Ancho de banda compartido**: con un hub de 100 Mbps, los 100 Mbps se **reparten** entre todas las estaciones activas, no cada una tiene su propia capacidad.

> [!example]
> Dos ramas de cable Ethernet unidas por un repetidor forman **un solo** [[Redes/ARC_Tema_3/Conceptos/Dominio de Colisión\|dominio de colisión]]: si A (rama 1) y B (rama 2) transmiten a la vez, colisionan igual que si estuvieran en el mismo cable (p. 10). Si en su lugar hubiera un switch, cada rama sería un dominio distinto (p. 16).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Capa Física\|Capa Física]] (Tema 1): es la capa en la que operan.
- [[Redes/ARC_Tema_1/Conceptos/Medios de Transmisión\|Medios de Transmisión]] (Tema 1): el repetidor existe por culpa de la atenuación del medio.

## Permite entender
- Por qué el **ancho de banda de un hub se degrada** al añadir estaciones: "a medida que se agregaron más estaciones, el rendimiento de cada estación se deterioró" (ARC_Tema_2 p. 27).
- Por qué los hubs han sido sustituidos por **[[Redes/ARC_Tema_3/Conceptos/Puente y Switch\|switches]]**: estos sí dividen el dominio de colisión y dan ancho de banda dedicado por puerto.
- La frase del material "**topología estrella pero con lógica de bus**" (p. 9): físicamente parece estrella, lógicamente se comporta como un medio compartido.

## Errores comunes
> [!warning]
> **Un hub no es un switch**. A simple vista pueden parecer iguales (una caja con muchos RJ-45), pero el hub trabaja **a nivel 1** y **replica bits por todos los puertos**, mientras que el switch opera **a nivel 2**, aprende MACs y reenvía solo por el puerto correcto (p. 9, 13). Confundirlos lleva a esperar aislamiento de colisiones donde no lo hay.

## Autoevaluación
> [!question]- ¿Por qué un hub de 100 Mbps con 5 estaciones no da 100 Mbps a cada una?
> Porque el hub proporciona **ancho de banda compartido** (p. 9): los 100 Mbps son los del medio común. En cualquier instante solo una estación transmite sin colisión; si hay 5 muy activas, la capacidad útil por estación es una fracción de los 100 Mbps y empeora con las colisiones (p. 9, 10).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_3/Fuente - ARC_Tema_3\|Fuente - ARC_Tema_3]], p. 7, 8, 9, 10, 48

## Mis notas
