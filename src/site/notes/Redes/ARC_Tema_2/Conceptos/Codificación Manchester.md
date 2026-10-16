---
{"dg-publish":true,"permalink":"/redes/arc-tema-2/conceptos/codificacion-manchester/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Manchester Encoding","Codificación Manchester"],"tags":["materia/redes","tema/protocolos"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_2/Fuente - ARC_Tema_2]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Codificación Manchester

> [!abstract] En una frase
> Codificación de línea usada por la **[[Redes/ARC_Tema_2/Conceptos/Ethernet\|Ethernet clásica]]**: cada bit se envía como una **transición en mitad del intervalo**, de modo que la propia señal lleva su reloj y receptor y emisor quedan sincronizados sin un cable extra.

## ¿Qué problema resuelve?
Cuando dos máquinas transmiten en banda base por un cable, el receptor necesita saber **dónde empieza y termina cada bit**. Si se envían ceros y unos como niveles planos de voltaje, una ráfaga larga de ceros parece "silencio" y los relojes se desincronizan. Hace falta que cada bit traiga su propio "tictac".

## Qué es
Según el material (p. 23), la **Ethernet clásica usa codificación Manchester**. En ella cada **tiempo de bit** contiene siempre una **transición en el centro**: un flanco de bajo a alto codifica un valor (p. ej. "1") y un flanco de alto a bajo el contrario ("0"). Como siempre hay una transición por bit, el receptor extrae **el reloj a partir de la propia señal de datos** (recuperación de reloj) y no necesita un canal separado para sincronización.

Características relevantes para la asignatura:
- Es una codificación de **capa física** ([[Redes/ARC_Tema_1/Conceptos/Capa Física\|Capa Física]]); se aplica después de que la [[Redes/ARC_Tema_2/Conceptos/Subcapa MAC\|Subcapa MAC]] forme la trama.
- Está asociada específicamente a la **Ethernet clásica** sobre coaxial / thick / thin descrita en p. 20-23.
- Al requerir **dos niveles por bit**, su eficiencia es la mitad: para transmitir B bits/s necesita 2B baudios de señal. Por eso Ethernet a 10 Mbps ocupa 20 Mbaudios de línea.

> [!example]
> La diapositiva de p. 23 muestra el patrón de niveles para una secuencia de bits: cada intervalo tiene siempre un cambio en el centro, nunca una barra plana. En **Ethernet clásica a 10 Mbps**, ese flanco central es lo que permite al adaptador del receptor engancharse al reloj del emisor sin un cable extra (p. 20, 23).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Capa Física\|Capa Física]]: Manchester vive en esta capa.
- [[Redes/ARC_Tema_2/Conceptos/Ethernet\|Ethernet]]: Ethernet clásica es la red que la emplea.
- [[Redes/ARC_Tema_1/Conceptos/Medios de Transmisión\|Medios de Transmisión]] (Tema 1): la codificación cambia según el medio; en coaxial de Ethernet clásica, Manchester.

## Permite entender
- Por qué las **Ethernet modernas** (Fast / Gigabit) **ya no usan Manchester**: a velocidades altas su coste en ancho de banda es demasiado grande y se sustituye por codificaciones más eficientes (4B/5B, 8B/10B).
- Por qué el cable Ethernet clásico no necesita un hilo de reloj separado.

## Errores comunes
> [!warning]
> La convención del flanco (ascendente = 1 o descendente = 1) **no es universal**: hay dos convenciones habituales, y lo importante es la existencia de la transición central, no su dirección concreta. Confundir Manchester con "simple cambio al principio del bit" (NRZ-I) es un error típico (p. 23).

## Autoevaluación
> [!question]- ¿Por qué Manchester permite al receptor recuperar el reloj aunque llegue una ráfaga larga del mismo bit?
> Porque cada intervalo de bit **siempre** tiene una transición en el centro, independientemente del valor transmitido. Esa transición periódica es el "tictac" del que el receptor extrae el reloj; con niveles planos (NRZ) una secuencia larga de ceros perdería la sincronización (p. 23).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_2/Fuente - ARC_Tema_2\|Fuente - ARC_Tema_2]], p. 20, 23

## Mis notas
