---
{"dg-publish":true,"permalink":"/redes/arc-tema-3/conceptos/dominio-de-difusion/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Broadcast Domain","Dominio Broadcast"],"tags":["materia/redes","tema/protocolos"],"nivel":0,"fuentes":["[[Redes/ARC_Tema_3/Fuente - ARC_Tema_3]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Dominio de Difusión

> [!abstract] En una frase
> Área de la red (conjunto de equipos y dispositivos) a la que **se llega enviando una trama de difusión**; todas las estaciones de ese dominio reciben y copian la trama.

## ¿Qué problema resuelve?
Nombra con precisión **hasta dónde llega una trama con destino `FF:FF:FF:FF:FF:FF`**. Sin este concepto no se puede razonar sobre el tráfico de broadcast (ARP, DHCP…) ni elegir los dispositivos de interconexión adecuados para contenerlo: una difusión mal contenida satura la red.

## Qué es
Según el material (p. 6): **"Un dominio de difusión es el área de una red, formada por computadoras y dispositivos de red que se puede alcanzar enviando una trama de difusión. Consumo inadecuado de recursos y bajo rendimiento de la red"**. La trama de difusión lleva como **dirección MAC destino** el valor especial **`FF:FF:FF:FF:FF:FF`**; a diferencia de la unicast, **todas las estaciones del segmento copian la trama**, no solo su destinatario (p. 6).

Comportamiento según el dispositivo (resumido en la tabla de p. 48):
- **Repetidor y [[Redes/ARC_Tema_3/Conceptos/Puente y Switch\|Hub]]**: *expanden* el dominio de difusión (p. 10).
- **Puente y [[Redes/ARC_Tema_3/Conceptos/Puente y Switch\|Switch]]**: *expanden* el dominio de difusión (reenvían la trama por **todos** sus puertos; p. 17).
- **[[Redes/ARC_Tema_3/Conceptos/Router\|Router]]**: **divide** el dominio de difusión; **no propaga una trama de difusión a sus otros interfaces** porque los considera redes diferentes (p. 46, 48).
- **[[Redes/ARC_Tema_3/Conceptos/Gateway\|Gateway]]**: también divide dominio de difusión (p. 48).

> [!example]
> Red con dos switches S1 y S2 conectados por un router R1. Si A envía ARP (difusión) por S1, el switch replica a sus puertos y la trama cruza S1 entero; pero R1 **no** la pasa a S2. S1 forma un dominio de difusión; S2, otro distinto (p. 17, 46).

## Cómo podrías haberlo descubierto
En una red de un solo cable, "difusión" es la condición **natural** del medio: todo lo que mande cualquiera llega a todos. Al introducir dispositivos de interconexión, surge una pregunta: *"¿cuánto se propaga una trama dirigida a `FF:FF:FF:FF:FF:FF`?"*. Un hub la reparte sin pensar; un switch tampoco se la queda, porque **no sabe por qué puerto está "todos"**; solo el router, que entiende de redes IP distintas, puede decir *"a mí esa difusión no me cruza"*. De esa pregunta sale la definición: el dominio es **todo lo que la trama alcanza sin topar con un router**.

## Depende de
- La trama Ethernet y su campo *Dirección Destino* (p. 6), donde la dirección especial `FF:FF:FF:FF:FF:FF` marca el destino "a todos".

## Permite entender
- Por qué **ARP** funciona dentro de una LAN pero no cruza routers: el ARP Request se envía por difusión y queda confinado al dominio de difusión del emisor (p. 25).
- Por qué una red con muchos switches encadenados puede sufrir **tormentas de difusión** si no se segmenta con routers o VLANs (p. 17).
- Por qué el router aparece como la **frontera natural** entre LANs.

## Errores comunes
> [!warning]
> **Dominio de difusión ≠ [[Redes/ARC_Tema_3/Conceptos/Dominio de Colisión\|dominio de colisión]]**. Un switch **divide** colisión pero **expande** difusión; solo el router (o un gateway) divide ambas (p. 48). Confundirlos lleva a creer que añadir switches aísla las LANs, cuando en realidad siguen compartiendo tráfico broadcast.

## Autoevaluación
> [!question]- ¿Por qué el router divide el dominio de difusión pero el switch lo expande?
> Porque el switch opera a nivel 2 y, al no entender IP, propaga la trama `FF:FF:FF:FF:FF:FF` por todos sus puertos (p. 17). El router opera a nivel 3: ve el paquete IP y **considera cada interfaz una red distinta**, por lo que no reenvía la difusión al otro lado (p. 46).

## Contraste
> [!success] Verificado
> La definición (área alcanzable por una trama de difusión), el papel de la MAC `FF:FF:FF:FF:FF:FF` y el comportamiento de cada dispositivo (hub/switch expanden, router divide) coinciden con Wikipedia (*Broadcast domain*) y con la tabla resumen del propio material (p. 48). Sin discrepancias.

## Fuentes
- [[Redes/ARC_Tema_3/Fuente - ARC_Tema_3\|Fuente - ARC_Tema_3]], p. 6, 10, 17, 46, 48

## Mis notas
