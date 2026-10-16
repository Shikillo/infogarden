---
{"dg-publish":true,"permalink":"/redes/arc-tema-3/conceptos/router/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Enrutador","Router IP"],"tags":["materia/redes","tema/protocolos"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_3/Fuente - ARC_Tema_3]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Router

> [!abstract] En una frase
> Dispositivo de **nivel 3 (IP)** que **conecta redes heterogéneas**, encamina los paquetes IP consultando sus **tablas de encaminamiento** y **divide tanto el dominio de colisión como el de difusión**.

## ¿Qué problema resuelve?
Un [[Redes/ARC_Tema_3/Conceptos/Puente y Switch\|switch]] basta mientras todo el tráfico se mueva por la misma LAN de nivel 2, pero no sabe nada de direcciones IP ni puede atravesar tecnologías distintas (LAN, MAN, WAN). El router aparece para **unir redes diferentes** y para elegir, paquete a paquete, **por qué enlace enviarlo** hacia su destino.

## Qué es
Según el material (p. 18): **"Permite conectar redes heterogéneas con direccionamiento IP. Encamina el paquete IP por el enlace adecuado para alcanzar el destino. Dispone de interfaz para interconectar redes LAN, MAN y/o WAN. Realiza un encaminamiento basado en tablas de encaminamiento. Comparte información con otros Routers"**. En el modelo OSI/TCP/IP se ubica en el **nivel 3 (Red / Internet)** (p. 18).

Características que indica el material:
- **Nivel 3** del modelo OSI (Red); nivel **Internet** en TCP/IP (p. 18, 48).
- Las tablas de encaminamiento tienen columnas `RED DEST | MÁSCARA | GATEWAY`; con `0.0.0.0 / 0.0.0.0` se expresa la **ruta por defecto** hacia el gateway de salida (p. 41).
- **Dominio de colisión**: lo **divide**. "Un Router divide el Dominio de Colisión. Si una trama es errónea (CRC) se descarta" (p. 45).
- **Dominio de difusión**: también lo **divide**. "El router no propaga una trama de difusión a sus otros interfaces pues se considera redes diferentes" (p. 46).
- Comparte información con otros routers mediante **protocolos de encaminamiento** para mantener coherentes sus tablas (p. 18).

> [!example]
> En la topología de p. 41, R1 recibe un paquete destinado a `21.128.2.10`. Consulta su tabla, encuentra la entrada `21.128.2.0 / 255.255.255.0 → 195.128.56.2` y lo reenvía por su interfaz hacia R2, que a su vez lo entrega localmente (p. 41).

### Cómo construye el router sus tablas
Las tablas no se escriben a mano (salvo rutas estáticas): los routers **comparten información** mediante **protocolos de encaminamiento** (p. 18, 40):

| Protocolo | Familia | Full-Class / Classless |
|---|---|---|
| **RIP v1** | Vector de distancias | Full-Class |
| **RIP v2** | Vector de distancias | Classless |
| **OSPF** | Estado del enlace | Classless |

- **Vector de distancias**: cada router comparte con sus vecinos su "tabla resumida" (red destino → coste). Simple, convergencia lenta.
- **Estado del enlace** (OSPF): cada router difunde el estado de sus enlaces, y todos construyen el **mapa completo** aplicando Dijkstra. Más complejo, converge más rápido.

### Qué hace exactamente un router al recibir un paquete
1. Si la trama tiene **CRC** erróneo, la descarta (p. 45).
2. Decapsula la trama de nivel 2 y toma el **datagrama IP**.
3. **Decrementa el TTL**; si llega a 0, descarta y manda ICMP (p. 36).
4. Busca en la tabla la **ruta con el prefijo más largo** que case con la IP destino.
5. Si el **MTU** de la interfaz de salida es menor que el datagrama y DF=0, **fragmenta** (ver [[Redes/ARC_Tema_3/Conceptos/Fragmentación de Datagramas IP\|Fragmentación de Datagramas IP]]).
6. Resuelve con **ARP** la MAC del siguiente salto en la red de salida.
7. Encapsula el datagrama en una nueva trama y lo transmite.

## Depende de
- [[Redes/ARC_Tema_3/Conceptos/IP y ARP\|IP y ARP]]: el router se mueve con direcciones IP; necesita ARP para resolver la MAC del siguiente salto en cada red.
- [[Redes/ARC_Tema_3/Conceptos/Subnetting y Supernetting\|Subnetting y Supernetting]]: las máscaras de las tablas de encaminamiento salen de esta técnica (p. 42-44).
- [[Redes/ARC_Tema_3/Conceptos/Dominio de Colisión\|Dominio de Colisión]] y [[Redes/ARC_Tema_3/Conceptos/Dominio de Difusión\|Dominio de Difusión]]: el router los **divide**, en contraste con hubs/switches (p. 45, 46).

## Permite entender
- Por qué para **llegar fuera de la LAN** hay que configurar un *default gateway*: es el router al que se envía todo paquete cuya red destino no está en la tabla (p. 41).
- Por qué el router aparece como la **frontera natural de las LANs**: al dividir dominio de difusión, los broadcasts no cruzan.
- Por qué los routers hablan entre sí: para construir una visión coherente de la red (p. 18).

## Errores comunes
> [!warning]
> El router **no es un switch rápido**: operan a capas distintas. Un switch mira direcciones MAC (nivel 2) dentro de una misma LAN; un router mira direcciones IP (nivel 3) y conecta **redes distintas** (p. 18, 48). Pensar que "basta con un switch grande" es un error típico cuando se quieren segmentar dominios de difusión.

## Autoevaluación
> [!question]- ¿Qué diferencia a un router de un switch respecto a los dominios de colisión y difusión?
> El **switch divide colisión pero expande difusión** (p. 17). El **router divide ambos**: colisión (p. 45) y difusión (p. 46). Esa es la razón de que el router sea la frontera entre LANs y el switch solo divida colisión dentro de una misma LAN (p. 48).

## Cómo podrías haberlo descubierto
Si tienes LANs con **tecnologías físicas distintas** (Ethernet por un lado, Wi-Fi por otro, un enlace WAN serie por un tercero), un switch no sirve: no sabe hablar varios "idiomas" físicos a la vez. Lo que necesitas es un dispositivo que **lea un direccionamiento común** por encima de la MAC —IP— y que, mirando ese direccionamiento, decida **por qué interfaz** mandar cada paquete. Eso es un router. Y si varios routers tienen que coordinarse para que un paquete llegue de una punta de la red a la otra, necesitan **compartir información** sobre qué saben llegar y por dónde: nacen los **protocolos de encaminamiento** (RIP, OSPF). La función básica del router sale de responder, una por una, a estas tres preguntas: *"¿esta IP está en mi red local?"* (si sí, ARP y entrego) *"¿y si no, por qué puerto?"* (tabla) *"¿y cómo mantengo la tabla al día?"* (protocolo de enrutamiento).

## Contraste
> [!success] Verificado
> El rol del router (nivel 3, encamina IP, divide colisión y difusión), las tablas con máscara/gateway y los protocolos **RIP** / **OSPF** se han contrastado con Wikipedia (*Router (computing)*, *RIP*, *OSPF*) y con las RFCs correspondientes (**RFC 2453** RIPv2, **RFC 2328** OSPFv2). Sin discrepancias.

## Fuentes
- [[Redes/ARC_Tema_3/Fuente - ARC_Tema_3\|Fuente - ARC_Tema_3]], p. 18, 41, 45, 46, 48

## Mis notas
