---
{"dg-publish":true,"permalink":"/redes/arc-tema-3/conceptos/ip-y-arp/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["IP","Protocolo IP","ARP","Direccionamiento IP","Clases IP","Encaminamiento IP"],"tags":["materia/redes","tema/protocolos"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_3/Fuente - ARC_Tema_3]]"],"contraste":"verificado","estado":"nuevo"}}
---

# IP y ARP

> [!abstract] En una frase
> **IP** aporta un **direccionamiento lógico jerárquico** (32 bits en IPv4) y un **servicio sin conexión** para encaminar datagramas entre redes heterogéneas; **ARP** resuelve, dentro de cada red local, **la dirección física (MAC)** correspondiente a una IP para que la trama se pueda entregar.

## ¿Qué problema resuelve?
La dirección física **MAC** solo tiene sentido dentro de una LAN: no está jerarquizada y no permite encaminar entre redes. Para que ordenadores de **redes distintas** (con tecnologías físicas distintas) puedan hablar, hace falta:

1. **Un direccionamiento lógico común** por encima de las MAC: eso es **IP** (p. 21).
2. **Un puente entre ese direccionamiento lógico y las MAC reales** del medio físico que se va a usar en el último salto: eso es **ARP** (p. 25).

Sin IP no se puede encaminar; sin ARP, aunque sepas la IP del destino, **no puedes construir la trama** de nivel 2 porque te falta la MAC.

## Qué es

### Protocolo IP

**Funcionamiento** (p. 20):
- **Servicio sin conexión** (datagrama): **no hay garantía de entrega**, posible **entrega desordenada**.
- IP realiza las funciones de **encaminamiento**.
- Define la **unidad básica** (datagrama), el **formato**, las **reglas de procesamiento**, las **condiciones de error**, etc.
- El datagrama IP se **encapsula en una trama** (p. ej. Ethernet) para viajar por el medio.

**Direccionamiento** (p. 21):
- Direcciones de **32 bits** (IPv4), escritas como **cuatro octetos decimales** separados por puntos: `n1.n2.n3.n4` (p. ej. `10000000 00001010 00000010 00011110` → `128.10.2.30`).
- **Jerárquico** para facilitar el encaminamiento.
- Identifica un **punto de conexión a una red**, no al host; **una máquina puede tener varias IPs** (una por interfaz, p. 22).
- Cada dirección se divide en **identificador de red** + **identificador de host**.

**Clases Full-Class** (p. 22-23):

| Clase | Máscara | Notación corta | Ejemplo |
|---|---|---|---|
| **A** | `255.0.0.0` | `/8` | `12.0.0.0/8` |
| **B** | `255.255.0.0` | `/16` | `129.12.0.0/16` |
| **C** | `255.255.255.0` | `/24` | `195.45.10.0/24` |

La **máscara de red** permite extraer el identificador de red haciendo un AND lógico con la IP (p. 23). En **Class-Less** las máscaras son **variables** (`/22`, por ejemplo) y determinan el tamaño de la red; ver [[Redes/ARC_Tema_3/Conceptos/Subnetting y Supernetting\|Subnetting y Supernetting]].

**Direcciones privadas RFC 1918** (p. 24): tres bloques reservados para redes privadas:
- `10.0.0.0 – 10.255.255.255` (una red clase A).
- `172.16.0.0 – 172.31.255.255` (16 redes clase B contiguas).
- `192.168.0.0 – 192.168.255.255` (256 redes clase C contiguas).

Muy útiles para **NAT** (Tema 10).

**Formato del datagrama IP** (p. 31):
- **Vers** (4 bits): versión (4 en IPv4).
- **Longc** (longitud de cabecera): tamaño en **palabras de 32 bits** (mínimo 5).
- **Longitud total**: en octetos, cabecera + datos; **máximo 65 535 octetos**.
- **Tipo de servicio** (TOS): prioridad y preferencias (retardo, velocidad, fiabilidad) — orientativo, no garantizado.
- **TTL** (p. 36): tiempo de vida; cada router lo **decrementa**; al llegar a 0 el datagrama se **descarta**. Evita bucles infinitos.
- **Protocolo**: identifica el **protocolo superior** (TCP, UDP, ICMP…) para demultiplexar.
- **Checksum**: solo cubre la **cabecera** (p. 37).
- **Opciones**: longitud variable, para verificación o diagnóstico.
- Campos específicos de **fragmentación** (identificación, flags DF/MF, offset): ver [[Redes/ARC_Tema_3/Conceptos/Fragmentación de Datagramas IP\|Fragmentación de Datagramas IP]].

### Protocolo ARP (Address Resolution Protocol, RFC 826)

**El problema** (p. 25): el host A conoce la IP del destino C pero **no su MAC**, y la MAC es necesaria en niveles inferiores para rellenar la trama.

**Mecanismo** (p. 26-27):
1. A envía un **ARP Request** por **difusión** (MAC destino `FF:FF:FF:FF:FF:FF`, protocolo `0x0806`) con el formato: `{IP_A, MAC_A, IP_C, ?}`.
2. **Todas las estaciones** de la LAN reciben la petición, pero **solo C responde** con un **ARP Reply** unicast: `{IP_A, MAC_A, IP_C, MAC_C}`.
3. A guarda la correspondencia `IP_C ↔ MAC_C` en su **caché ARP**.

**Refinamientos** (p. 27):
- Las entradas tienen **tiempo de vida limitado** (caché, no permanente).
- Cualquier estación que **oiga** una petición puede aprovechar para **actualizar su caché**.
- Se admiten **entradas permanentes**.
- Los errores de transmisión se resuelven con **retransmisiones por timeout**.

**Formato ARP** (p. 28-29): usa un formato común que vale para distintas tecnologías; indica tipo de hardware (Ethernet = 1), tipo de protocolo (IP = `0x800`), longitudes de direcciones y un campo **operación**: `1 = ARP request`, `2 = ARP reply`, `3 = RARP request`, `4 = RARP reply`.

### Encaminamiento IP

**Diálogo directo vs indirecto** (p. 38):
- **Directo**: emisor y destino en la **misma red IP**. El emisor averigua la MAC del destino con ARP y le envía directamente la trama. Ejemplo A→B en la misma red.
- **Indirecto**: destino en **otra red**. El emisor envía la trama al **router** (ARP sobre la IP del router), que la encamina. Ejemplo A→C a través de R1.

En el caso indirecto, los campos IP (origen y destino) no cambian, pero la **MAC destino** de la trama es la del **router**, no la del host final.

**Tablas de encaminamiento** (p. 39-40):
- Entradas iniciales (**FullClass**): `RED DEST | GATEWAY`.
- Modernas (**Classless**): `RED DEST | MÁSCARA | GATEWAY`.
- **Ruta por defecto** (`0.0.0.0/0`): para todo lo que no esté en la tabla; útil si la salida al resto de Internet es única.
- **Rutas específicas** para hosts concretos: control y seguridad.

Los routers **intercambian información** para mantener coherentes sus tablas. Protocolos más populares (p. 40):
- **RIP** (*Routing Information Protocol*): **vector de distancias**. RIPv1 Full-Class, RIPv2 Classless.
- **OSPF** (*Open Shortest Path First*): **estado del enlace**.

**Problemas del direccionamiento clásico** (p. 42):
- Las tablas crecen demasiado.
- Las clases A y B **desperdician** direcciones (nadie conecta 2²⁴ hosts a una misma LAN).
- Direcciones escasas.

De ahí nacen las técnicas de **[[Redes/ARC_Tema_3/Conceptos/Subnetting y Supernetting\|Subnetting y Supernetting]] / CIDR**.

## Cómo podrías haberlo descubierto
Si queremos que ordenadores con **tecnologías físicas distintas** se entiendan, lo primero que hace falta es un **direccionamiento común** que no dependa del medio. Ese direccionamiento tiene que ser **jerárquico** para que al mirarlo se sepa "más o menos" por dónde encaminar (igual que un número de teléfono: prefijo de país → región → abonado). Esa es la IP: **red + host** separados por una máscara. Pero cuando llega el momento de **poner los bits en el cable**, al switch Ethernet solo le hablan en **MAC**. Alguien tiene que **traducir IP a MAC** en el último salto: la forma más barata es **preguntar a gritos "¿quién tiene esta IP?"** y aprovechar la **difusión** del medio local. Eso es ARP, con el añadido de **cachear** las respuestas para no preguntar constantemente.

## Depende de
- [[Redes/ARC_Tema_2/Conceptos/Subcapa MAC\|Subcapa MAC]] (Tema 2): IP se **encapsula sobre tramas MAC** (p. 20).
- [[Redes/ARC_Tema_3/Conceptos/Router\|Router]]: el que materializa el encaminamiento IP.
- [[Redes/ARC_Tema_3/Conceptos/Dominio de Difusión\|Dominio de Difusión]]: ARP vive dentro del dominio de difusión y no cruza routers.

## Permite entender
- [[Redes/ARC_Tema_3/Conceptos/Fragmentación de Datagramas IP\|Fragmentación de Datagramas IP]]: justificación y mecanismo de la fragmentación.
- [[Redes/ARC_Tema_3/Conceptos/Subnetting y Supernetting\|Subnetting y Supernetting]]: evolución del direccionamiento Full-Class a Classless.
- [[Redes/ARC_Tema_3/Conceptos/Router\|Router]]: su razón de ser es encaminar paquetes IP.
- Por qué una red con **IP sin máscara coherente** no funciona: emisor y receptor pueden discrepar sobre si están en la misma red (y por tanto sobre si usar diálogo directo o indirecto).

## Ejemplo
> [!example]
> **Diálogo directo** (p. 38). Host A (`193.18.1.100/24`) hace `ping 193.18.1.101`. A detecta que destino y origen comparten la misma red (`193.18.1.0/24`). Lanza un ARP request por difusión; B responde con su MAC; A construye la trama con `MAC destino = MAC_B` y la envía directamente al switch, que la entrega.

> [!example]
> **Diálogo indirecto** (p. 38). Host A (`193.18.1.100/24`) hace `ping 193.18.2.30`. Al aplicar su máscara ve que están en redes distintas, así que envía la trama al **router R1** cuya IP es su *default gateway* (`193.18.1.1`). ARP resuelve la MAC de R1, no la de C. R1 recibe el datagrama, consulta su tabla, lo reencapsula en la interfaz Eth1 con `MAC destino = MAC_C` (previa resolución ARP en la red `193.18.2.0/24`) y lo entrega.

> [!example]
> **Encaminamiento** (p. 41). R1 tiene la entrada `21.128.2.0 / 255.255.255.0 → 195.128.56.2`. Un datagrama hacia `21.128.2.10` se envía por esa ruta hacia R2.

## Errores comunes
> [!warning]
> **IP no garantiza nada**: ni entrega, ni orden, ni ausencia de duplicados (p. 20). Las capas superiores (TCP) son las que añaden fiabilidad. Pensar que "una vez que se manda, llega" es un error típico.

> [!warning]
> **Una IP identifica una interfaz**, no un host: *"una máquina puede tener varias direcciones distintas"* (p. 22). Un router por definición tiene **al menos una IP por interfaz**.

> [!warning]
> **ARP no cruza routers**: la difusión queda confinada al dominio de difusión del emisor. Si el destino está en otra red, ARP se usa para la IP del **router**, no para la del destino final (p. 38).

> [!warning]
> **TTL evita bucles, no garantiza entrega** (p. 36). Si por error el TTL inicial es pequeño, un paquete legítimo puede morir sin llegar a destino.

> [!warning]
> La **máscara importa, no "la clase"**. En Classless una IP `12.1.2.3/22` no es "clase A": la red se determina por la **máscara**, no por el primer octeto (p. 23).

## Autoevaluación
> [!question]- Diferencia entre diálogo directo y diálogo indirecto.
> En el **directo**, origen y destino están en la **misma red IP**; el emisor usa ARP para obtener la MAC del destino y le envía la trama directamente. En el **indirecto**, están en redes distintas; la trama lleva la **MAC del router** como destino de nivel 2, aunque la IP destino sea la del host final (p. 38).

> [!question]- ¿Por qué ARP se envía por difusión?
> Porque el emisor **no sabe** aún la MAC del destino, pero necesita que alguien de la LAN le conteste. La difusión (`FF:FF:FF:FF:FF:FF`) garantiza que **todas** las estaciones reciben la pregunta; solo responde la que tiene esa IP (p. 25-27).

> [!question]- ¿Por qué los routers decrementan el TTL?
> Para **evitar que un datagrama mal encaminado dé vueltas eternas** por Internet (p. 36). Al llegar a 0, se descarta y no se vuelve a retransmitir.

> [!question]- ¿Qué significa `0.0.0.0 / 0.0.0.0` en una tabla de encaminamiento?
> La **ruta por defecto**: se aplica a cualquier destino que no coincida con otra entrada más específica. Es útil cuando la salida al resto de Internet es única (p. 39, 41).

## Contraste
> [!success] Verificado
> IPv4 (32 bits), clases A/B/C, rangos privados **RFC 1918**, formato ARP (operación 1/2/3/4, Ethernet=1, IP=0x0800), TTL y encaminamiento directo/indirecto se han contrastado con las RFCs (**RFC 791** IP, **RFC 826** ARP, **RFC 1918**) y con Wikipedia (*IPv4*, *Address Resolution Protocol*). Coincide con el material.

## Fuentes
- [[Redes/ARC_Tema_3/Fuente - ARC_Tema_3\|Fuente - ARC_Tema_3]], p. 19-29, 31, 36-41

## Mis notas
