---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/topologia-de-red/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Topología LAN","Topologías de Red","Topología física","Topología lógica"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Topología de Red

> [!abstract] En una frase
> **Estructura** —física o lógica— que define **cómo se conectan los nodos** en una red; en LAN las formas básicas son **bus, anillo, estrella, árbol, malla y mixta**.

## ¿Qué problema resuelve?
En cuanto hay más de dos ordenadores en una red surge una pregunta inevitable: *¿cómo los conecto?* No es una decisión trivial, porque de ella dependen el **coste del cableado**, la **tolerancia a fallos**, la **facilidad de administración** y hasta las **colisiones** entre señales. La topología es el vocabulario con el que se describe esa decisión.

## Qué es
Según el material (p. 12), la topología define la **estructura** de la red y se mira desde dos perspectivas:

- **Topología física**: la **disposición real** de los cables y nodos; es "lo que ves" si abres el techo.
- **Topología lógica**: la **forma en que fluye la información** y se accede al medio; es "lo que ocurre dentro del cable", independiente de cómo esté tendido.

Las **seis formas** que lista el PDF para una [[Redes/ARC_Tema_1/Conceptos/Red de Área Local (LAN)\|LAN]] (p. 12) son:

| Topología | Idea básica |
|---|---|
| **Bus** | Un único cable compartido donde todos los nodos se cuelgan. |
| **Anillo** | Nodos conectados en cadena cerrada; el testigo o la señal da la vuelta. |
| **Estrella** | Todos los nodos conectados a un **nodo central** (hub o switch). |
| **Árbol** | Jerarquía de buses o estrellas interconectadas. |
| **Malla** | Nodos interconectados entre sí, con rutas múltiples. |
| **Mixta** | Combinación de las anteriores (lo habitual en edificios reales). |

## Cómo podrías haberlo descubierto
Pon dos ordenadores en una mesa: con **un cable** basta. Añade un tercero y aparecen opciones: ¿otro cable entre A-C y B-C (**malla parcial**)? ¿Un cable común al que se enganchan los tres (**bus**)? Añade más nodos y verás que algunas opciones **escalan mal** (una malla completa necesita *n(n-1)/2* cables), que otras **concentran todo el fallo en un punto** (una estrella se cae si cae el centro) y que otras **reparten carga a cambio de latencia** (el anillo). Esas tensiones —coste, fiabilidad, latencia, administración— son las que **dan nombre** a cada topología. Lo mismo pasa con la distinción física/lógica: en cuanto apareció el **hub**, un cableado en estrella se comportaba por dentro como un bus, y hubo que separar los dos conceptos.

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Red de Área Local (LAN)\|Red de Área Local (LAN)]]: el PDF presenta las topologías como clasificación interna de las LAN.
- [[Redes/ARC_Tema_1/Conceptos/Medios de Transmisión\|Medios de Transmisión]]: el medio físico elegido condiciona qué topologías físicas son viables.

## Permite entender
- [[Redes/ARC_Tema_1/Conceptos/Enlace de Difusión\|Enlace de Difusión]]: las topologías en bus (y en estrella con hub) son típicamente de difusión.
- [[Redes/ARC_Tema_1/Conceptos/Enlace Punto a Punto\|Enlace Punto a Punto]]: la malla se construye con enlaces punto a punto entre pares de nodos.
- Las decisiones de **diseño de red local**: coste, redundancia, tolerancia a fallos.

## Ejemplo
> [!example]
> Una oficina moderna cablea los puestos con un **switch central**: la **topología física es en estrella** (cada PC con su propio cable al switch), pero la **topología lógica** es de **estrella conmutada punto a punto** (cada puerto es un enlace dedicado al switch). Si el mismo cableado se hiciera con un **hub** en lugar de un switch, la **lógica pasaría a ser de bus** (todos reciben todo), aunque la foto del armario fuese idéntica (p. 12).

## Errores comunes
> [!warning]
> **No confundir físico con lógico**. La misma red puede ser estrella por fuera y bus por dentro (hub) o estrella conmutada por dentro (switch). La topología **lógica** es la que determina si hay colisiones y difusión; la **física**, el coste de cableado y la tolerancia a fallos.

> [!warning]
> No existe "la mejor" topología: cada una resuelve un compromiso distinto entre **coste**, **tolerancia a fallos**, **latencia** y **facilidad de administración**. Por eso en la práctica casi todas las redes son **mixtas**.

## Autoevaluación
> [!question]- ¿Qué diferencia hay entre topología física y topología lógica?
> La **física** describe cómo están tendidos los cables y colocados los nodos; la **lógica** describe cómo fluye la información y cómo se accede al medio. Una misma disposición física puede soportar lógicas distintas (p. 12).

> [!question]- Enumera las seis topologías LAN que presenta el material.
> **Bus**, **anillo**, **estrella**, **árbol**, **malla** y **mixta** (p. 12).

## Contraste
> [!success] Verificado
> La clasificación en bus, anillo, estrella, árbol, malla y mixta y la distinción física/lógica se han contrastado con fuentes externas (Wikipedia: *Network topology*). El material es consistente con esas fuentes.

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 11-12

## Mis notas
