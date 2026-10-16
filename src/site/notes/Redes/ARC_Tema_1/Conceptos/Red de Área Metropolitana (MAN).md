---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/red-de-area-metropolitana-man/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["MAN","Metropolitan Area Network","Red MAN"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Red de Área Metropolitana (MAN)

> [!abstract] En una frase
> Red de **extensión media** (del orden de **~10 km**, una **ciudad**) situada entre la [[Redes/ARC_Tema_1/Conceptos/Red de Área Local (LAN)\|Red de Área Local (LAN)]] y la [[Redes/ARC_Tema_1/Conceptos/Red de Área Amplia (WAN)\|Red de Área Amplia (WAN)]]; históricamente nació de las redes de TV por cable y hoy su ejemplo típico es **FTTH**.

## ¿Qué problema resuelve?
Conectar varios edificios o toda una ciudad con una sola infraestructura: ni cada edificio sacado por su propia LAN aislada, ni cruzar un país entero por una [[Redes/ARC_Tema_1/Conceptos/Red de Área Amplia (WAN)\|WAN]]. Es el tamaño "ciudad".

## Qué es
Según el material (p. 10): **"Abarcan extensiones como ciudades (~10 km). Originalmente redes de TV por cable en ciudades. Actualmente las redes FTTH (*Fiber to the Home*) es el ejemplo más extendido"**. Según la tabla de clasificación por extensión geográfica (p. 8), la MAN cubre la escala **10 km → Ciudad**, entre LAN (hasta ~1 km, campus) y WAN (100 km o más).

Características que indica el material:
- **Distancia típica**: ~10 km (p. 8, 10).
- **Ejemplos citados**: **FTTH**, **FDDI** (p. 8); históricamente, **TV por cable** urbana (p. 10).
- Suele usar **[[Redes/ARC_Tema_1/Conceptos/Enlace Punto a Punto\|enlaces punto a punto]]** entre nodos, como las redes grandes (p. 7).

> [!example]
> Una operadora que lleva fibra óptica desde su central hasta cada hogar de una ciudad (FTTH) está desplegando una red MAN: el salto de kilómetros entre central y abonado es demasiado grande para una LAN y demasiado pequeño para una WAN (p. 8, 10).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Red de Área Local (LAN)\|Red de Área Local (LAN)]]: a menudo una MAN agrega varias LANs de edificio o barrio.
- [[Redes/ARC_Tema_1/Conceptos/Conmutación de Paquetes\|Conmutación de Paquetes]]: tecnología subyacente de la mayoría de MANs modernas.

## Permite entender
- [[Redes/ARC_Tema_1/Conceptos/Red de Área Amplia (WAN)\|Red de Área Amplia (WAN)]]: la escala inmediatamente superior.
- Por qué el **tipo de enlace** cambia con el tamaño: a esta escala predomina el enlace punto a punto, no el enlace de difusión (p. 7).

## Errores comunes
> [!warning]
> "Metropolitana" no significa **administrada por el ayuntamiento**: se refiere al **tamaño** (una ciudad). También es un error pensar que FTTH es siempre una MAN; depende del alcance real del operador y de cómo se defina la frontera con la WAN (p. 10).

## Autoevaluación
> [!question]- ¿Qué distingue a una MAN de una LAN grande (p. ej. un campus) y de una WAN?
> El **tamaño** (~10 km, una ciudad), el **tipo de enlace** (ya predomina punto a punto, no difusión) y los **ejemplos tecnológicos** (FTTH, FDDI, TV por cable), frente a Ethernet/WiFi (LAN) o ATM/SONET (WAN) (p. 7, 8, 10).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 7, 8, 10

## Mis notas
