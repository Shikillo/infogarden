---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/enlace-punto-a-punto/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Point-to-Point Link"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Enlace Punto a Punto

> [!abstract] En una frase
> Una **conexión individual** entre exactamente dos máquinas; cada paquete sigue una ruta determinada por estas conexiones directas o a través de nodos intermedios.

## ¿Qué problema resuelve?
Permitir redes de gran extensión donde cada par de máquinas no puede compartir un mismo canal físico, habilitando múltiples rutas posibles entre origen y destino.

## Qué es
Un enlace de **punto a punto** conecta **dos nodos específicos**; no hay canal compartido con terceros. Las redes más grandes (como WAN) usan enlaces punto a punto entre routers, que a su vez conectan con otros routers, formando una red de nodos conectados por pares.

Características:
- **Conexión individual**: un enlace = dos nodos
- **Varias rutas posibles**: si hay varios pares conectados, los datos pueden atravesar diferentes nodos
- No requiere campo de dirección de difusión (cada enlace ya sabe su destino inmediato)
- Escala mejor en redes geográficamente distribuidas

> [!example]
> Una red WAN con routers conectados entre sí por enlaces de fibra o satélite. Si dos routers no comparten enlace directo, se comunican a través de otros routers (p. 7, 9).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Red de Área Amplia (WAN)\|Red de Área Amplia (WAN)]]: el contexto típico

## Permite entender
- [[Redes/ARC_Tema_1/Conceptos/Enlace de Difusión\|Enlace de Difusión]]: contraste con canal compartido
- [[Redes/ARC_Tema_1/Conceptos/Red de Área Metropolitana (MAN)\|Red de Área Metropolitana (MAN)]]: puede combinar ambos tipos

## Errores comunes
> [!warning]
> No confundir con "enlace directo sin intermediarios". Un enlace punto a punto es **directo entre dos nodos**, pero los datos pueden pasar por varios nodos (cada salto es otro enlace punto a punto).

## Autoevaluación
> [!question]- ¿Por qué las redes grandes (WAN) tienden a usar enlaces punto a punto en lugar de difusión?
> Porque la difusión requiere un canal compartido entre todos, impracticable a escala geográfica grande. El punto a punto permite conectar pares específicos a través de enlaces físicos dedicados, formando rutas flexibles (p. 7-9).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 7, 9

## Mis notas