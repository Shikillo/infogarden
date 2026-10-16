---
{"dg-publish":true,"permalink":"/redes/arc-tema-3/conceptos/dominio-de-colision/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Dominio Colisión","Collision Domain"],"tags":["materia/redes","tema/protocolos"],"nivel":0,"fuentes":["[[Redes/ARC_Tema_3/Fuente - ARC_Tema_3]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Dominio de Colisión

> [!abstract] En una frase
> **Segmento físico** de una red en el que **dos tramas enviadas a la vez pueden colisionar**, destruyéndose mutuamente y haciendo que las estaciones tengan que retransmitirlas.

## ¿Qué problema resuelve?
Cuando varias estaciones comparten el mismo medio físico, si dos emiten al mismo tiempo sus señales **se mezclan** y las tramas se corrompen. El concepto de *dominio de colisión* **nombra el perímetro exacto** dentro del cual puede ocurrir esto: todo lo que está dentro **compite por el mismo canal**, y todo lo que está fuera **no se ve afectado**. Es la unidad básica para razonar sobre congestión en una LAN: segmentar la red consiste, en gran parte, en **romper dominios de colisión demasiado grandes**.

## Qué es
Según el material (p. 5): *"Un dominio de colisión es un segmento físico de una red de computadores donde es posible que las tramas puedan 'colisionar' con otras. Se da cuando varios dispositivos conectados al mismo medio físico acceden al medio al mismo tiempo, ocurre una colisión. Consumo inadecuado de recursos y de ancho de banda en la red"*.

Puntos clave:
- Es un **concepto físico / de nivel 1-2**, no de IP.
- Está asociado a la [[Redes/ARC_Tema_2/Conceptos/Subcapa MAC\|Subcapa MAC]]: dentro de un dominio de colisión hace falta un protocolo como [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]] para arbitrar el acceso.
- Dos estaciones en el **mismo** dominio pueden colisionar; dos estaciones en dominios **distintos**, no.

### Qué pasa con cada dispositivo (tabla resumen de p. 48)

| Dispositivo | Capa | Dominio de colisión |
|---|---|---|
| **[[Redes/ARC_Tema_3/Conceptos/Repetidor y Hub\|Repetidor]]** | 1 Física | **Expande** |
| **[[Redes/ARC_Tema_3/Conceptos/Repetidor y Hub\|Hub]]** | 1 Física | **Expande** |
| **[[Redes/ARC_Tema_3/Conceptos/Puente y Switch\|Puente]]** | 2 Enlace (MAC) | **Divide** |
| **[[Redes/ARC_Tema_3/Conceptos/Puente y Switch\|Switch]]** | 2 Enlace (MAC) | **Divide** |
| **[[Redes/ARC_Tema_3/Conceptos/Router\|Router]]** | 3 Red (IP) | **Divide** |
| **[[Redes/ARC_Tema_3/Conceptos/Gateway\|Gateway]]** | ≥ 4 Transporte | **Divide** |

El material deja claro por qué el switch divide (p. 16): *"Un Switch/Puente divide el Dominio de Colisión. Si una trama es errónea (CRC) se descarta"*. En el ejemplo de p. 16, A y B colgados de puertos distintos del switch pueden transmitir **simultáneamente sin colisión**, mientras que en el lado donde cuelga un hub la colisión sí ocurre.

## Cómo podrías haberlo descubierto
Pon diez ordenadores colgados del mismo cable coaxial de Ethernet clásica (ARC_Tema_2 p. 20). Si dos quieren hablar a la vez, las dos señales se superponen y los bits que ve el resto son basura: hay una **colisión**. Si en lugar del cable único instalas un **hub**, la foto cambia (topología estrella) pero el comportamiento es el mismo (p. 9): el hub repite cada bit por todos los puertos, así que **sigue habiendo un único medio compartido** y, por tanto, **un único dominio de colisión**. Pero si cambias el hub por un **switch**, cada puerto se vuelve un medio independiente: ahí nace el concepto de "cada puerto del switch es su propio dominio". A partir de ese momento, el **tamaño del dominio** es la variable clave del diseño: menos estaciones por dominio → menos colisiones → más ancho de banda útil.

## Depende de
- *(raíz del tema)*: concepto previo necesario para hablar del resto.
- [[Redes/ARC_Tema_2/Conceptos/Subcapa MAC\|Subcapa MAC]] (Tema 2): CSMA/CD opera **dentro** de un dominio de colisión.

## Permite entender
- [[Redes/ARC_Tema_3/Conceptos/Repetidor y Hub\|Repetidor y Hub]]: **expanden** el dominio (p. 10).
- [[Redes/ARC_Tema_3/Conceptos/Puente y Switch\|Puente y Switch]]: lo **dividen** (p. 16).
- [[Redes/ARC_Tema_3/Conceptos/Router\|Router]]: lo **divide** (p. 45).
- Por qué cambiar hubs por switches mejora **drásticamente** el rendimiento de una LAN: cada puerto pasa a ser un dominio de colisión aislado con **ancho de banda dedicado**.

## Ejemplo
> [!example]
> Red con **S1** (switch) y **H1** (hub) colgando de un puerto de S1. Las estaciones A, B, C conectadas a otros puertos del switch pueden transmitir **simultáneamente sin colisión** (cada puerto es su propio dominio). Pero las estaciones conectadas al hub H1 están **todas en el mismo dominio** y, si dos emiten a la vez, chocan: *"El Hub expande la colisión. El switch corta la colisión"* (p. 16).

## Errores comunes
> [!warning]
> **Dominio de colisión ≠ dominio de difusión**. Un switch **divide colisión** pero **expande difusión** (p. 16-17). Solo el router divide ambos (p. 45-46). Confundirlos lleva a creer que basta con añadir switches para "aislar" dos LANs.

> [!warning]
> **El concepto es físico, no es por IP**. Dos equipos pueden estar en la misma IP de red pero en dominios de colisión distintos (si entre ellos hay un switch) o viceversa. La IP no determina colisiones; **el cableado y los dispositivos de nivel 1-2 sí**.

> [!warning]
> Añadir **más hubs encadenados** no mejora el rendimiento: unifica dominios y empeora las colisiones (p. 10).

## Autoevaluación
> [!question]- ¿Por qué un switch divide el dominio de colisión y un hub lo expande?
> El hub opera a **nivel 1 (físico)** y **repite cada bit por todos los puertos**, por lo que es equivalente a un cable único compartido (p. 9). El switch opera a **nivel 2 (MAC)**: cada puerto es un **enlace independiente** y solo envía la trama por el puerto del destino, por lo que dos estaciones en puertos distintos **no pueden colisionar** (p. 13-16).

> [!question]- ¿Qué pasa con el dominio de colisión si conecto dos hubs entre sí?
> Se **unifica**: ambos hubs y sus estaciones pasan a formar un **único** dominio de colisión mayor (p. 10). El número de colisiones esperadas crece.

## Contraste
> [!success] Verificado
> La definición del material (segmento físico donde pueden colisionar tramas; expandido por hub/repetidor y dividido por switch/router) coincide con Wikipedia (*Collision domain*) y con los libros de referencia (Tanenbaum). Sin discrepancias.

## Fuentes
- [[Redes/ARC_Tema_3/Fuente - ARC_Tema_3\|Fuente - ARC_Tema_3]], p. 5, 10, 16, 45, 48

## Mis notas
