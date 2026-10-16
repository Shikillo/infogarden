---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/conmutacion-de-paquetes/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Packet Switching","Datagram","Datagrama"],"tags":["materia/redes","tema/introduccion"],"nivel":0,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Conmutación de Paquetes

> [!abstract] En una frase
> Los datos se **fragmentan en paquetes** que comparten dinámicamente los recursos de la red según sea necesario; cada paquete busca ruta independientemente.

## ¿Qué problema resuelve?
Maximizar la utilización de la capacidad de red para tráfico de datos intermitente, permitiendo que muchos usuarios compartan los mismos enlaces en cualquier momento.

## Qué es
En la **conmutación de paquetes**, los datos se envían en **paquetes** (o datagramas). Cada paquete contiene **cabecera** (dirección destino, salto) y **datos**. Los paquetes se enrutan individualmente en cada nodo; múltiples conexiones comparten los mismos enlaces. Sin necesidad de reservar circuito completo.

Características:
- **Dos variantes**: **Circuito Virtual** (toda la comunicación sigue ruta reservada tras primer paquete) y **Datagrama** (cada paquete elige ruta independently)
- Multiplexación estadística: los huecos dejan aprovechar otros usuarios
- Flexibilidad: permite rutas alternativas ( tolerancia a fallos)
- Bajo retardo (no hay fase de establecimiento)

> [!example]
> **Redes de datos modernas**: Internet usa conmutación de datagramas; redes privadas ATM usan circuito virtual. Ambas se basan en paquetes (p. 5-6).

## Depende de
- (raíz: no depende de otros conceptos de esta materia)

## Permite entender
- [[Redes/ARC_Tema_1/Conceptos/Conmutación de Circuitos\|Conmutación de Circuitos]]: contraste
- [[Redes/ARC_Tema_1/Conceptos/Circuito Virtual\|Circuito Virtual]] / [[Datagrama\|Datagrama]]: variantes específicas

## Errores comunes
> [!warning]
> Conmutación de paquetes ≠ simplemente enviar muchos paquetes pequeños. El *direccionamiento*, *enrutamiento* y *procesamiento* en cada nodo son fundamentales; también requiere *protocolo* para gestionar errores y flujo.

## Autoevaluación
> [!question]- ¿Cuál es la principal ventaja de la conmutación de paquetes frente a la conmutación de circuitos para servicios como Internet?
> Permite **multiplexación estadística**: muchos usuarios comparten enlaces, aprovechando los huecos que dejaría inútiles un circuito dedicado. Permite más conexiones simultáneas en el mismo ancho de banda (p. 5-6).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 3-6

## Mis notas