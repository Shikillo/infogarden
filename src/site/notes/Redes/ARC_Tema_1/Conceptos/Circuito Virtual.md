---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/circuito-virtual/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Virtual Circuit","VC"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Circuito Virtual

> [!abstract] En una frase
> **Variante de conmutación de paquetes** que **reserva una ruta** para toda la comunicación tras establecer una conexión lógica (VC), siguiendo la misma ruta para cada paquete.

## ¿Qué problema resuelve?
Ofrecer la **determinación de ruta** y **garantía de QoS** de conmutación de circuitos, pero sin desperdiciar ancho de banda en silencios; los paquetes comparten enlace pero siguen orden.

## Qué es
En un **circuito virtual (VC)**, tras el **primer paquete** el nodo crea una entrada de tabla que asocia origen y destino con un identificador de VC y reserva recursos de QoS (ancho de banda). Todos los paquetes subsiguientes llevan el identificador VC; cada nodo reenvía según tabla, sin necesidad de volver a calcular ruta.

Características:
- **Fases**: 1) Establecimiento de conexión (primer paquete) 2) Transmisión 3) Liberación (cerramiento)
- **Identificador** común a todos los paquetes del mismo circuito lógico
- **Reservación** de recursos (coloque, retardo)
- **Estable**: más predecible que datagrama, pero menos flexible

> [!example]
> **ATM** (Asynchronous Transfer Mode) usa circuitos virtuales. El host establece VC antes de la transferencia de datos para servicios con requerimientos de retardo (voz, vídeo) (p. 5-6).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Conmutación de Paquetes\|Conmutación de Paquetes]]: es una variante
- [[Redes/ARC_Tema_1/Conceptos/Conmutación de Circuitos\|Conmutación de Circuitos]]: el modelo de los recursos reservados

## Permite entender
- [[Redes/ARC_Tema_1/Conceptos/Conmutación de Paquetes\|Datagrama]]: la variante contraria, donde cada paquete elige ruta sin reservar circuito.
- La idea general de **establecimiento de conexión** antes de transmitir datos (p. 5).

## Errores comunes
> [!warning]
> Circuito Virtual ≠ Conmutación de Circuitos. El VC **multiplica paquetes** en el mismo enlace (comunica con otros en ese enlace), pero reserva ruta; el circuito de circuitos ocupa enlace entero.

## Autoevaluación
> [!question]- ¿Qué etapa del protocolo de circuito virtual reserva recursos en nodos y destino?
> **Establecimiento de conexión**: un primer paquete fija la ruta y reserva recursos de QoS en nodos y destino; los paquetes siguientes reutilizan esta reserva (p. 5).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 5-6

## Mis notas