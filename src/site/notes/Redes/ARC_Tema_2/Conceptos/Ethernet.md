---
{"dg-publish":true,"permalink":"/redes/arc-tema-2/conceptos/ethernet/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["IEEE 802.3","Ethernet Standard","Ethernet clásica"],"tags":["materia/redes","tema/protocolos"],"nivel":2,"fuentes":["[[Redes/ARC_Tema_2/Fuente - ARC_Tema_2]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Ethernet

> [!abstract] En una frase
> Estándar dominante de **LAN cableada** (**IEEE 802.3** desde 1983) nacido en Xerox PARC (1976) sobre **cable coaxial** con [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]] a 3 Mbps, y evolucionado hasta las versiones **conmutadas** actuales a **1 y 10 Gbps**.

## ¿Qué problema resuelve?
Antes de Ethernet, interconectar ordenadores dentro de un edificio implicaba cableados **propietarios**, lentos y poco interoperables. Ethernet aportó una receta **sencilla, barata y abierta** —un cable coaxial, un protocolo MAC bien definido y un formato de trama común— sobre la que se podía **escalar en velocidad sin cambiar el modelo**. Esa combinación de **compatibilidad hacia atrás** y **crecimiento ordenado** es la razón por la que acabó barriendo a Token Ring, FDDI y las demás alternativas.

## Qué es
### Origen y evolución
Según el material (p. 20):

- **1976**: Bob Metcalfe y David Boggs implementan la **primera LAN** en el **Xerox Palo Alto Lab**, sobre **cable coaxial largo y grueso**, a **3 Mbps**. El nombre viene de **"éter luminífero"**.
- **1978**: estandarizada como **DIX** (Xerox, DEC, Intel) a **10 Mbps**.
- **1983**: adoptada como **IEEE 802.3**.

### Ethernet clásica (p. 20-23)
Topología de **bus** sobre coaxial compartido. Dos variantes de cableado (p. 21):

| Variante | Longitud máxima de segmento | PCs por segmento |
|---|---|---|
| **Thick Ethernet** | **500 m** | hasta **100** |
| **Thin Ethernet** (conectores **BNC**) | **185 m** | hasta **30** |

Para extensiones mayores se conectan segmentos mediante **repeaters** (p. 21): dispositivos de **[[Redes/ARC_Tema_1/Conceptos/Capa Física\|capa física]]** que **reciben, amplifican y retransmiten** la señal en ambas direcciones.

Elementos adicionales:
- **Protocolo MAC**: [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]].
- **Codificación de línea**: [[Redes/ARC_Tema_2/Conceptos/Codificación Manchester\|Codificación Manchester]] (p. 23).
- **Formato de trama**: ver [[Redes/ARC_Tema_2/Conceptos/Protocolo Subcapa MAC - Formato Trama\|Protocolo Subcapa MAC - Formato Trama]].

### Ethernet conmutada
A medida que se añadían estaciones, el rendimiento por estación en la Ethernet clásica se **deterioraba**: todas comparten el canal (p. 27-29). La solución fue sustituir el **cable largo compartido** o el **hub** (equivalente al cable largo) por un **switch** (p. 28):

- Cada estación tiene un **cable dedicado** al switch.
- El switch sabe **qué trama va a qué puerto** y la reenvía solo ahí.
- Resultado: **no hay colisiones**, mayor capacidad **agregada** y beneficios de **seguridad** (p. 29).

Esto permitió escalar la velocidad: **Ethernet** (10 Mbps) → **Fast Ethernet** (100 Mbps) → **Gigabit** (1 Gbps) → **10 Gigabit**. Ver [[Redes/ARC_Tema_2/Conceptos/Ethernet Conmutada Fast Gigabit\|Ethernet Conmutada Fast Gigabit]].

## Cómo podrías haberlo descubierto
Un cable coaxial largo, un montón de ordenadores enganchados a él y un protocolo que diga *"escucha, habla si está libre, retira si chocas"* es la red local **más barata que se puede imaginar**. Esa simplicidad conceptual permitió que Metcalfe la construyera con lo que había a mano. Al añadir estaciones aparece el límite —**más colisiones**, **menos rendimiento**— y la solución natural es **separar físicamente** los dominios de colisión: nace el **switch**. A partir de ahí, subir velocidad es un problema de **capa física** (mejor codificación, mejor cable), no de modelo: por eso Ethernet puede ir de 10 Mbps a 10 Gbps **manteniendo el formato de trama**.

## Depende de
- [[Redes/ARC_Tema_2/Conceptos/Subcapa MAC\|Subcapa MAC]]: Ethernet clásica es un caso típico de protocolo MAC.
- [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]]: protocolo de acceso al medio.
- [[Redes/ARC_Tema_2/Conceptos/Codificación Manchester\|Codificación Manchester]]: codificación de línea en la versión clásica.
- [[Redes/ARC_Tema_2/Conceptos/Protocolo Subcapa MAC - Formato Trama\|Protocolo Subcapa MAC - Formato Trama]]: formato de trama MAC.

## Permite entender
- [[Redes/ARC_Tema_2/Conceptos/Ethernet Conmutada Fast Gigabit\|Ethernet Conmutada Fast Gigabit]]: la evolución hacia 100 Mbps, 1 y 10 Gbps.
- Por qué Ethernet barrió a sus competidores: la **misma trama** y el **mismo direccionamiento** sobreviven a cada aumento de velocidad.
- La relación entre **retardo de propagación**, **tamaño mínimo de trama** y **longitud máxima del cable** (p. 25-26).

## Ejemplo
> [!example]
> Una Ethernet clásica thick (coaxial de 500 m) con 20 ordenadores en una planta: todas las estaciones comparten el cable; cuando dos emiten a la vez, CSMA/CD aborta ambas y las reintenta tras un *backoff* aleatorio (p. 20-21). Si en lugar del cable largo se instalara un switch con cables UTP cat 5 de 100 m a cada estación, la red se convertiría en **Ethernet conmutada**: cada puerto es un enlace dedicado y no hay colisiones (p. 27-29).

## Errores comunes
> [!warning]
> *Hub* y *switch* **no son equivalentes**. El hub es *"equivalente al cable largo único de la Ethernet clásica"* (p. 27): no aumenta capacidad y preserva el dominio de colisión. El switch sí separa dominios de colisión y aumenta la capacidad agregada (p. 28-29).

> [!warning]
> Las **velocidades crecientes** (10 Mbps → 10 Gbps) **no cambian el formato de trama**: una de las metas de Gigabit era *"mantener el mismo formato de trama, incluidos los tamaños mínimo y máximo"* (p. 31). Lo que cambia es la **capa física** (medio, codificación, señalización).

> [!warning]
> **Ethernet clásica usa Manchester** (p. 23); **las versiones modernas no**: pasan a esquemas más eficientes (4B/5B, 8B/10B).

## Autoevaluación
> [!question]- ¿Qué diferencia esencial hay entre Ethernet clásica y Ethernet conmutada?
> La clásica usa un **canal compartido** (cable largo o hub) y necesita **[[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]]** para resolver colisiones. La conmutada usa **enlaces dedicados** a un **switch**, de modo que **no hay colisiones** y la capacidad **se multiplica** por el número de puertos activos (p. 27-29).

> [!question]- ¿Qué papel tienen los repeaters en Ethernet clásica?
> Son dispositivos de **capa física** que **reciben, amplifican y retransmiten** la señal en ambas direcciones (p. 21). Permiten extender el bus más allá de la longitud máxima de un segmento, **sin cambiar el dominio de colisión**.

## Contraste
> [!success] Verificado
> La historia (Metcalfe/Boggs 1976, DIX 1978, IEEE 802.3 1983), las longitudes (500 m thick / 185 m thin) y la evolución a conmutada están alineadas con Wikipedia (*Ethernet*) y con la literatura habitual (Tanenbaum). No se han detectado discrepancias.

## Fuentes
- [[Redes/ARC_Tema_2/Fuente - ARC_Tema_2\|Fuente - ARC_Tema_2]], p. 18-23, 27-29

## Mis notas
