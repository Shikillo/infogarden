---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/red-de-area-amplia-wan/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["WAN","Wide Area Network","Red de Área Extensa"],"tags":["materia/redes","tema/introduccion"],"nivel":2,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Red de Área Amplia (WAN)

> [!abstract] En una frase
> Red de **gran extensión geográfica** (país, continente o planeta) que interconecta redes locales distantes mediante **routers** y **enlaces de larga distancia**.

## ¿Qué problema resuelve?
Las [[Redes/ARC_Tema_1/Conceptos/Red de Área Local (LAN)\|LANs]] cubren a lo sumo un edificio o un campus. Cuando dos ordenadores están en ciudades, países o continentes distintos, hace falta una infraestructura capaz de **transportar datos a miles de kilómetros** manteniendo rutas, direcciones y fiabilidad razonable. La WAN es la respuesta a esa escala: no se trata ya de compartir un cable, sino de **encaminar paquetes** entre nodos distribuidos por el mundo.

## Qué es
Una **WAN (Wide Area Network)** cubre distancias de **~100 km (país)**, **~1 000 km (continente)** y **~10 000 km (planeta)** (p. 8). Según el material (p. 9), se descompone en:

- **Hosts**: los equipos finales (ordenadores, servidores) que generan o consumen los datos.
- **Subredes**: las redes locales conectadas a la WAN.
- **Nodos de enrutamiento (routers)**: los equipos que deciden por qué camino viaja cada paquete.
- **Enlaces**: las líneas (punto a punto) que unen pares de routers.

La regla operativa que da el PDF es (p. 9): *si dos routers no comparten enlace directo, se comunican a través de otros routers*. Es decir, los paquetes **saltan de router en router** hasta llegar a la subred de destino. Esto solo es posible porque internamente la WAN usa [[Redes/ARC_Tema_1/Conceptos/Conmutación de Paquetes\|Conmutación de Paquetes]] (típicamente con [[Redes/ARC_Tema_1/Conceptos/Circuito Virtual\|Circuito Virtual]], como ATM, o con datagrama, como IP).

Ejemplos que cita el material (p. 8): **ATM**, **SONET** e **Internet** (como WAN global, a escala planetaria).

## Cómo podrías haberlo descubierto
Imagina que ya tienes LANs funcionando en edificios aislados. Para unir dos LANs lejanas no puedes tirar un cable directo: inviable y antieconómico. La solución natural es **colocar un nodo intermedio** que reciba un paquete por una interfaz y lo reenvíe por otra. Si repites el truco con muchos nodos, aparece una **malla de routers conectados por enlaces** sobre la que viajan los paquetes. Esa malla es, por definición, una WAN. El salto conceptual clave frente a la LAN es que ya **no hay un medio compartido**, sino **enlaces individuales** entre pares de nodos ([[Redes/ARC_Tema_1/Conceptos/Enlace Punto a Punto\|Enlace Punto a Punto]]).

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Red de Área Local (LAN)\|Red de Área Local (LAN)]]: las LANs son las "hojas" que la WAN conecta.
- [[Redes/ARC_Tema_1/Conceptos/Conmutación de Paquetes\|Conmutación de Paquetes]]: el modelo de red interno (datagrama o circuito virtual).
- [[Redes/ARC_Tema_1/Conceptos/Enlace Punto a Punto\|Enlace Punto a Punto]]: la WAN se construye con enlaces individuales entre routers, no con difusión.

## Permite entender
- [[Redes/ARC_Tema_3/Conceptos/Router\|Router]] (Tema 3): el nodo cuya razón de ser es encaminar paquetes en WAN.
- La **jerarquía LAN → MAN → WAN**: cada escala resuelve un problema distinto con compromisos distintos de velocidad, coste y propiedad.
- Internet: entendido como la WAN mundial resultante de interconectar WANs regionales.

## Ejemplo
> [!example]
> Un usuario en Madrid abre una página alojada en un servidor de Tokio. Su ordenador está en una LAN doméstica; el servidor, en otra LAN del centro de datos. Entre medias, el paquete atraviesa **decenas de routers** por **enlaces transoceánicos de fibra**, saltando entre operadores hasta llegar al destino: esa infraestructura intermedia es la WAN (en este caso, Internet; p. 8-9).

## Errores comunes
> [!warning]
> **No confundir** WAN con MAN (ciudad, ~10 km) ni con LAN (edificio o campus, ≤10 km). La clave no es solo la **distancia**, sino el **modelo**: la WAN se basa en **routers y enlaces punto a punto**, mientras que la LAN se basa típicamente en **difusión sobre un medio compartido** (p. 7-8).

> [!warning]
> **Internet no es "una" WAN única**: es el resultado de interconectar muchas WANs (de operadores, de universidades, de empresas) mediante acuerdos de intercambio de tráfico. El material usa Internet como ejemplo a escala planetaria (p. 8).

## Autoevaluación
> [!question]- ¿Cuál es la diferencia esencial de modelo entre una LAN y una WAN según el material?
> La LAN suele basarse en un **medio compartido con difusión** y pocos usuarios (p. 11), mientras que la WAN se basa en una **malla de routers conectados por enlaces punto a punto** sobre la que se encaminan paquetes (p. 7, 9).

> [!question]- Si dos routers de una WAN no comparten un enlace directo, ¿cómo se comunican?
> A través de **otros routers intermedios** que reenvían los paquetes salto a salto hasta la subred de destino (p. 9).

## Contraste
> [!success] Verificado
> Las afirmaciones de esta nota (definición, ejemplos ATM/SONET/Internet, estructura hosts-subredes-routers) han sido contrastadas con fuentes externas (Wikipedia: *Wide area network*) y coinciden con el material. No se han detectado discrepancias.

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 8-9

## Mis notas
