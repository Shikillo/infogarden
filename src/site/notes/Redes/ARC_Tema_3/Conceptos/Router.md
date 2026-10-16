---
{"dg-publish":true,"permalink":"/redes/arc-tema-3/conceptos/router/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Enrutador","Router IP"],"tags":["materia/redes","tema/protocolos"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_3/Fuente - ARC_Tema_3]]"],"contraste":"pendiente","estado":"nuevo"}}
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

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_3/Fuente - ARC_Tema_3\|Fuente - ARC_Tema_3]], p. 18, 41, 45, 46, 48

## Mis notas
