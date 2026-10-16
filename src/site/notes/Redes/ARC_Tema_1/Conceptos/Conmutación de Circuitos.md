---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/conmutacion-de-circuitos/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Circuit Switching"],"tags":["materia/redes","tema/introduccion"],"nivel":0,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Conmutación de Circuitos

> [!abstract] En una frase
> Se establece un **circuito dedicado** entre emisor y receptor para toda la duración de la comunicación, reservando recursos fijos en la ruta.

## ¿Qué problema resuelve?
Permitir comunicaciones en tiempo real (voz, vídeo) con latencia constante y garantía de ancho de banda, sin competir por recursos con otras conexiones.

## Qué es
En la **conmutación de circuitos** se crea un camino físico (o lógico con reserva de recursos) extremo a extremo antes de transmitir datos. El circuito permanece abierto aunque no se envíen datos (silencio en una llamada). Ejemplo clásico: **red telefónica conmutada (RTC)**.

Características:
- **3 fases**: establecimiento → transmisión → liberación
- Recursos reservados en nodos y enlaces durante toda la sesión
- Latencia y *jitter* predecibles
- Ineficiente para tráfico *bursty* (datos intermitentes) porque desperdicia capacidad en silencios

> [!example]
> Una llamada telefónica tradicional: al descolgar se reserva un circuito de 64 kbps por cada sentido; aunque nadie hable, el circuito sigue ocupado (p. 4).

## Depende de
- (raíz: no depende de otros conceptos de esta materia)

## Permite entender
- [[Redes/ARC_Tema_1/Conceptos/Conmutación de Paquetes\|Conmutación de Paquetes]]: contraste fundamental
- [[Redes/ARC_Tema_1/Conceptos/Circuito Virtual\|Circuito Virtual]]: variante que reserva ruta pero multiplexa paquetes

## Errores comunes
> [!warning]
> No confundir "circuito dedicado" con "línea alquilada". En conmutación de circuitos la reserva es **dinámica** por llamada; una línea alquilada es un contrato permanente.

## Autoevaluación
> [!question]- ¿Por qué la conmutación de circuitos es ineficiente para tráfico de datos típico (web, correo)?
> Porque el tráfico de datos es *bursty* (ráfagas cortas separadas por silencios largos). Reservar un circuito fijo desperdicia ancho de banda durante los silencios; la conmutación de paquetes multiplexa estadísticamente esos huecos.

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 3-5

## Mis notas