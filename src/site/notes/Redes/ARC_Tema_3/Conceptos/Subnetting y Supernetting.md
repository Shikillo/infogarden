---
{"dg-publish":true,"permalink":"/redes/arc-tema-3/conceptos/subnetting-y-supernetting/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Subnetting","Supernetting","VLSM","CIDR","Classless Inter-Domain Routing"],"tags":["materia/redes","tema/protocolos"],"nivel":2,"fuentes":["[[Redes/ARC_Tema_3/Fuente - ARC_Tema_3]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Subnetting y Supernetting

> [!abstract] En una frase
> Técnicas de direccionamiento **sin clases** (**CIDR**) que, usando **máscaras variables**, permiten **dividir** una red IP en subredes más pequeñas (**subnetting**) o **agrupar** varias contiguas en una ruta única (**supernetting**), para no derrochar direcciones ni inflar las tablas de encaminamiento.

## ¿Qué problema resuelve?
El direccionamiento **Full-Class** reserva bloques enormes a cualquier red:
- Clase A → **2²⁴ ≈ 16 millones** de hosts.
- Clase B → **2¹⁶ ≈ 65 000** hosts.
- Clase C → **254** hosts.

*"No es habitual conectar 2²⁴ ó 2¹⁶ hosts a una misma red local"* (p. 42). Resultado: direcciones **desperdiciadas** y **tablas de encaminamiento** gigantes porque hay demasiadas redes anunciadas. Las dos caras del problema son:

1. **Dentro de una organización**: una clase B es demasiado para una LAN; conviene **partir** el espacio en trozos más pequeños.
2. **En el backbone de Internet**: miles de redes pequeñas anunciadas por separado inflan las tablas; conviene **agregar** rutas contiguas en una sola entrada.

**Subnetting** resuelve (1); **Supernetting / CIDR** resuelve (2).

## Qué es

### Máscara de red (p. 23)
Es un patrón de 32 bits que, en AND con una dirección IP, **extrae la parte de red**:

```
IP:       157.42.4.2    10011101.00101010.00000100.00000010
Máscara:  255.255.0.0   11111111.11111111.00000000.00000000
Red:      157.42.0.0    10011101.00101010.00000000.00000000
```

En **Full-Class**, cada clase trae su máscara (p. 23):
- Clase A → `/8` → `255.0.0.0`.
- Clase B → `/16` → `255.255.0.0`.
- Clase C → `/24` → `255.255.255.0`.

En **Class-Less** la máscara es **arbitraria** (`/22`, `/27`, lo que haga falta) y es la que determina el tamaño de la red, no el primer octeto.

### Subnetting (p. 43)
*"Una de las soluciones es fragmentar una red IP en subredes. Para que esto no signifique modificar IPs se utilizan máscaras de red"* (p. 43).

**Ejemplo del material**: la red `131.107.0.0/16` tiene (`2¹⁶ − 2 =`) **65 534** hosts, demasiado para una sola LAN. Si **ampliamos la máscara 2 bits**, pasa a ser `/18`:

| Subred | Rango | Hosts |
|---|---|---|
| `131.107.0.0/18` | `131.107.0.1` – `131.107.63.254` | 2¹⁴ − 2 |
| `131.107.64.0/18` | `131.107.64.1` – `131.107.127.254` | 2¹⁴ − 2 |
| `131.107.128.0/18` | `131.107.128.1` – `131.107.191.254` | 2¹⁴ − 2 |
| `131.107.192.0/18` | `131.107.192.1` – `131.107.255.254` | 2¹⁴ − 2 |

Con **2 bits** de subred, salen **4 subredes de 2¹⁴ hosts** (unos **16 382** cada una) sin tocar la asignación global.

Esto es lo que se conoce como **VLSM** (Variable Length Subnet Mask): dentro de la misma organización pueden coexistir subredes de distintos tamaños (`/22` para la planta grande, `/27` para un pequeño enlace punto a punto, etc.).

### Supernetting y CIDR (p. 44)
*"CIDR (Classless Inter-Domain Routing) permite reducir el tamaño de las tablas de encaminamiento de los routers. Añade la información de máscara a las tablas de encaminamiento"* (p. 44).

Si una organización tiene asignadas 8 redes contiguas de clase C:
```
192.0.0.0/24, 192.0.1.0/24, …, 192.0.7.0/24
```
en lugar de **8 entradas** en las tablas externas, basta con **una** usando una máscara más corta (más general): `192.0.0.0/21`. Eso es **supernetting**: **agregar varias redes contiguas** en una entrada única.

En las tablas Classless (p. 39) cada entrada tiene **máscara explícita**:
```
RED DEST   MÁSCARA           GATEWAY
21.128.1.0 255.255.255.0     0.0.0.0
0.0.0.0    0.0.0.0           15.128.56.1   (ruta por defecto)
```

El router aplica **"longest prefix match"**: si varias entradas coinciden, gana la de **máscara más larga** (la más específica).

## Cómo podrías haberlo descubierto
El error de diseño original fue **meter el tamaño de la red en los bits altos** (A/B/C). Si en lugar de eso el **tamaño va aparte**, en una **máscara**, dejas la IP y mueves el límite a voluntad. Esa única idea desbloquea las dos cosas:
- Si **estiro** la máscara (más 1s), parto una red en más subredes de menos hosts → **subnetting**.
- Si **acorto** la máscara, varias redes contiguas se funden en una sola → **supernetting**.
- Y como ahora **la máscara se almacena en las tablas**, los routers pueden mezclar entradas de cualquier tamaño sin ambigüedad: nace **CIDR**.

## Depende de
- [[Redes/ARC_Tema_3/Conceptos/IP y ARP\|IP y ARP]]: la base conceptual (direccionamiento IP, clases, máscara).
- [[Redes/ARC_Tema_3/Conceptos/Router\|Router]]: usa las tablas con máscaras para encaminar.

## Permite entender
- Por qué una dirección `12.1.2.3/22` **no es "clase A"** aunque empiece por un número bajo: en Classless la red la marca la **máscara** (p. 23).
- Por qué una IP del rango `/16` puede estar en una red /24, /22, /27…: todo depende de **la máscara con la que se configuró**.
- Por qué los **ISP** suelen asignar bloques `/21`, `/22`: el cliente los puede subdividir internamente con VLSM.
- Por qué sin CIDR las tablas de **BGP** de Internet serían inmanejables.
- La **ruta por defecto** `0.0.0.0/0` (p. 41) como el **supernet máximo**: máscara de 0 bits = cualquier destino.

## Ejemplo
> [!example]
> Una empresa recibe `195.128.56.0/24` y necesita cuatro subredes para departamentos. Puede hacer VLSM con máscara `/26` (**2 bits adicionales**): salen cuatro subredes `195.128.56.0/26`, `195.128.56.64/26`, `195.128.56.128/26`, `195.128.56.192/26`, cada una con **62 hosts** útiles (2⁶ − 2). Esta es, de hecho, la asignación que aparece en el ejemplo de encaminamiento de p. 41.

> [!example]
> Un ISP tiene asignados `203.0.112.0/24` hasta `203.0.127.0/24` (16 redes contiguas). En lugar de anunciar 16 rutas en el exterior, anuncia **una sola**: `203.0.112.0/20`. Supernetting (CIDR) en acción.

## Errores comunes
> [!warning]
> **No todas las particiones son válidas**: una subred debe empezar en una dirección cuyos bits de host sean todos 0, y su rango útil es `2^(bits de host) − 2` (se restan la dirección de red y la de broadcast).

> [!warning]
> **La "clase" ya no existe en la práctica**: pensar que una `/22` es "una clase C grande" es un error. CIDR eliminó las clases para el enrutamiento (p. 42-44).

> [!warning]
> **Subnetting ≠ VLAN**: subnetting es un reparto a nivel 3 del espacio IP; una **VLAN** es una segmentación a nivel 2 por configuración del switch. Son ortogonales (aunque suelen combinarse).

> [!warning]
> Al mezclar máscaras en las tablas, los routers aplican **longest prefix match**: una ruta `/24` siempre gana a una `/16` que incluya el mismo destino. Olvidar esto lleva a sorpresas de encaminamiento.

> [!warning]
> **RIPv1 no soporta Classless**; **RIPv2** y **OSPF** sí (p. 40). Mezclar protocolos antiguos y modernos puede provocar que las máscaras se pierdan.

## Autoevaluación
> [!question]- ¿Cuántas subredes y hosts salen al pasar de `/16` a `/18`?
> Al añadir **2 bits** de red → 2² = **4 subredes**. Cada una tiene `32 − 18 = 14` bits de host → `2¹⁴ − 2 = 16 382` hosts útiles (p. 43).

> [!question]- Diferencia entre subnetting y supernetting.
> **Subnetting**: **estirar** la máscara para dividir una red en subredes más pequeñas. **Supernetting**: **acortar** la máscara para fusionar varias redes contiguas en una sola entrada de tabla. Ambos son posibles gracias a que CIDR almacena la máscara explícitamente en las rutas (p. 43-44).

> [!question]- En Classless, ¿cómo sabe un router cuál es la red destino de una IP?
> Aplicando la **máscara explícita** de cada entrada de su tabla y comparando. Como pueden coincidir varias, aplica **longest prefix match**: gana la de máscara más larga (más específica) (p. 39, 44).

## Contraste
> [!success] Verificado
> La descripción de VLSM y CIDR (longest prefix match, agregación de rutas, máscara en las tablas de encaminamiento) coincide con **RFC 1519 / RFC 4632 (CIDR)** y con Wikipedia (*Classless Inter-Domain Routing*, *Subnetwork*). Sin discrepancias.

## Fuentes
- [[Redes/ARC_Tema_3/Fuente - ARC_Tema_3\|Fuente - ARC_Tema_3]], p. 21-24, 39, 41-44

## Mis notas
