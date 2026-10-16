---
{"dg-publish":true,"permalink":"/redes/arc-tema-2/conceptos/protocolo-subcapa-mac-formato-trama/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["MAC Frame Format","Ethernet Frame","Trama Ethernet","Formato Trama MAC"],"tags":["materia/redes","tema/protocolos"],"nivel":2,"fuentes":["[[Redes/ARC_Tema_2/Fuente - ARC_Tema_2]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Protocolo Subcapa MAC — Formato de Trama

> [!abstract] En una frase
> Estructura de la **trama Ethernet** (versiones **DIX** y **IEEE 802.3**) que define los campos de direcciones, tipo/longitud, datos y CRC; su **tamaño mínimo** está fijado por el límite **2τ** necesario para detectar colisiones.

## ¿Qué problema resuelve?
Para que [[Redes/ARC_Tema_2/Conceptos/Ethernet\|Ethernet]] funcione, no basta con un cable y un protocolo de acceso: emisor y receptor tienen que **ponerse de acuerdo en el formato exacto de los bits** que viajan por el cable. Y ese formato no es libre: tiene que permitir **direccionar** destinatarios, **detectar errores** y, sobre todo, **detectar colisiones a tiempo**, lo que impone un **tamaño mínimo** a cada trama.

## Qué es
El material presenta dos variantes muy similares (p. 24): **Ethernet (DIX)** y **IEEE 802.3**. En el formato típico aparecen los siguientes campos:

| Campo | Tamaño | Función |
|---|---|---|
| **Preámbulo** | 7 bytes | sincronización del receptor |
| **SFD** (Start Frame Delimiter) | 1 byte | marca el inicio de la trama |
| **Dirección destino (MAC)** | 6 bytes | 48 bits, identifica al destinatario |
| **Dirección origen (MAC)** | 6 bytes | 48 bits, identifica al emisor |
| **Tipo / Longitud** | 2 bytes | DIX: tipo de protocolo; 802.3: longitud del campo de datos |
| **Datos** | 46 – 1500 bytes | carga útil |
| **CRC** | 4 bytes | código de redundancia para detectar errores |

Puntos clave que subraya el material:

- **Direcciones de 48 bits**: formato universal usado por todas las versiones de Ethernet (p. 31).
- **Datos con mínimo 46 bytes**: si la carga útil es más corta, se **rellena** (padding) para alcanzar el mínimo.
- **CRC** final para detección de errores.

### Por qué un tamaño mínimo de trama
En [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]], una colisión puede tardar hasta **2τ** en detectarse (p. 25), donde τ es el **retardo de propagación** de un extremo al otro del cable. Si la trama se enviara en menos tiempo que 2τ, la estación emisora **podría terminar sin saber** que ha colisionado. Para evitarlo:

- Se fija un **tiempo mínimo de trama** ≥ 2τ.
- Combinando ese tiempo con el **ancho de banda** B y la **longitud del cable** L (a velocidad de propagación c), sale el **tamaño mínimo de trama F** y, equivalentemente, la **longitud máxima del cable** (p. 26).

Es decir, el **mínimo de 46 bytes de datos** (que con cabeceras llega a los **64 bytes de trama mínima**) no es un capricho: viene impuesto por la física del medio y por CSMA/CD.

## Cómo podrías haberlo descubierto
Si quieres que dos ordenadores se entiendan, tienes que fijar **dónde está cada cosa** en el torrente de bits. La elección es casi obvia: primero algo para **sincronizarse** (preámbulo), después **a quién va** y **de quién viene** (direcciones), luego **qué tipo de datos** son (tipo/longitud), después **los datos** y, al final, **un sello de validez** (CRC). Lo único no obvio es el **tamaño mínimo**: aparece cuando te das cuenta de que, si una colisión tarda 2τ en percibirse, la trama tiene que durar al menos 2τ para que el emisor pueda enterarse de ella antes de terminar.

## Depende de
- [[Redes/ARC_Tema_2/Conceptos/Subcapa MAC\|Subcapa MAC]]: la trama es la unidad de datos de esta subcapa.
- [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]]: el límite 2τ impone el tamaño mínimo de trama.
- [[Redes/ARC_Tema_2/Conceptos/Ethernet\|Ethernet]]: contexto estándar en el que se usa este formato.

## Permite entender
- Por qué en Ethernet existe un **tamaño mínimo** de 64 bytes de trama (padding si hace falta).
- Por qué, al pasar de Ethernet clásica a Gigabit, el estándar insistió en **mantener el mismo formato de trama** (p. 31): mantiene la compatibilidad con todo el software existente.
- La relación entre **longitud máxima del cable**, **ancho de banda** y **tamaño de trama** (p. 26).

## Ejemplo
> [!example]
> Un paquete IP de 20 bytes "desnudo" encapsulado en Ethernet quedaría por debajo del mínimo. La capa Ethernet **añade padding** hasta llegar a los 46 bytes mínimos del campo de datos. El receptor sabe que es padding gracias al **campo de longitud** (en 802.3) o a la cabecera superior (en DIX con campo *tipo*) y lo descarta (p. 24, 26).

## Errores comunes
> [!warning]
> **DIX vs IEEE 802.3**: el mismo campo de 2 bytes se usa como **tipo** en DIX y como **longitud** en 802.3. Como los valores de "tipo" empiezan por encima de los valores posibles de "longitud" (>1536), ambas convenciones conviven sin ambigüedad.

> [!warning]
> El **mínimo de 46 bytes de datos** no es arbitrario: viene de **2τ** y de CSMA/CD (p. 25-26). Confundirlo con una limitación de la memoria o del cable es un error típico.

> [!warning]
> El **CRC** detecta errores pero no los corrige: su presencia **no sustituye** mecanismos de retransmisión de capas superiores.

## Autoevaluación
> [!question]- ¿Por qué una trama Ethernet tiene un tamaño mínimo?
> Para que **la detección de colisión (CSMA/CD)** pueda ocurrir **antes** de que el emisor termine de enviar. Como una colisión puede tardar **hasta 2τ** en detectarse (p. 25), la trama tiene que durar al menos ese tiempo. En función del ancho de banda y de la longitud del cable, eso se traduce en un número concreto de bytes (p. 26).

> [!question]- ¿Qué pasa si la carga útil es menor que el mínimo?
> Se añade **padding** hasta llegar al mínimo, para no incumplir el tamaño de trama que exige CSMA/CD (p. 24, 26).

## Contraste
> [!success] Verificado
> El formato (direcciones MAC de 48 bits, datos 46-1500, CRC-32) y la justificación del mínimo por 2τ coinciden con la literatura habitual (Tanenbaum) y con Wikipedia (*Ethernet frame*). No se han detectado discrepancias.

## Fuentes
- [[Redes/ARC_Tema_2/Fuente - ARC_Tema_2\|Fuente - ARC_Tema_2]], p. 24-26

## Mis notas
