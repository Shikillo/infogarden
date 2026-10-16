---
{"dg-publish":true,"permalink":"/redes/arc-tema-3/conceptos/fragmentacion-de-datagramas-ip/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Fragmentación IP","IP Fragmentation","MTU","Reensamblaje IP"],"tags":["materia/redes","tema/protocolos"],"nivel":2,"fuentes":["[[Redes/ARC_Tema_3/Fuente - ARC_Tema_3]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Fragmentación de Datagramas IP

> [!abstract] En una frase
> Cuando un datagrama IP es **mayor que la MTU** de la red por la que tiene que viajar, los **routers lo parten en fragmentos**; el **reensamblaje se hace solo en el destino** y basta un fragmento perdido para que **todo el datagrama se pierda**.

## ¿Qué problema resuelve?
Cada red física impone un **tamaño máximo de trama** llamado **MTU** (Maximum Transfer Unit). Ethernet, por ejemplo, no acepta tramas con más de **1500 bytes** de carga útil. Pero un datagrama IP puede llegar a **65 535 bytes**, y en una ruta real puede atravesar redes con MTUs **distintas** (Ethernet, Wi-Fi, enlaces WAN…). La fragmentación es el **mecanismo de IP para seguir siendo utilizable** sobre medios con MTU inferior a la del datagrama, sin forzar al emisor a conocer de antemano la MTU más pequeña del camino.

## Qué es
Según el material (p. 32-34):

- *"Los datagramas IP deben ser transmitidos a través del servicio que proporciona la red física"*.
- *"Todas las redes imponen limitaciones al tamaño máximo de los paquetes"* ⇒ **MTU**.
- MTU en **Ethernet**: **1500 bytes** (campo de datos de la trama).
- Si **datagrama ≤ MTU**, no hay fragmentación.
- Si **datagrama > MTU**, se **divide en fragmentos**. *"El problema se presentará en el tránsito entre dos redes físicas distintas: fragmentarán los routers"* (p. 33).

### Campos clave de la cabecera IP implicados (p. 33-34)

| Campo | Rol en la fragmentación |
|---|---|
| **Identificación** | **Igual** en todos los fragmentos del mismo datagrama; distinto entre datagramas. Permite al destino reconocer qué pedazos van juntos. |
| **Longitud (longitud total)** | Longitud **del fragmento concreto** (no del datagrama original). |
| **Flags → DF** (Do Not Fragment) | Si está activo, el datagrama **no puede ser fragmentado**: si no cabe, el router lo descarta y avisa (ICMP). |
| **Flags → MF** (More Fragments) | Si está activo, **este fragmento no es el último**. En el último fragmento MF = 0. |
| **Offset del fragmento** | Posición del fragmento dentro del datagrama original, **en múltiplos de 8 bytes**. |

### Reensamblaje (p. 34)
- **Solo en el destino**, nunca en routers intermedios. Un router que recibe un fragmento solo lo **vuelve a encaminar**.
- El destino identifica fragmentos del mismo datagrama con **(dirección origen, identificación, flags, offset)**.
- Al recibir el **primer fragmento** se activa un **temporizador**:
  - Si llegan **todos antes del timeout** → se ensambla y procesa.
  - Si **expira** → se **descartan los fragmentos** ya recibidos.

Es decir: **basta con que falte un fragmento** para perder el datagrama entero.

### Ejemplo del material (p. 35)
Envío de **2000 bytes de datos IP** de A a B por una ruta con MTUs **1500 → 800 → 900 → 1500**:

- En la **Red 1** (MTU 1500): el datagrama cabe partido en **dos fragmentos** de 1480 y 520 bytes de datos (ID=1, DF=0; el primero con MF=1, offset=0; el segundo con MF=0, offset=185).
- Al pasar a la **Red 2** (MTU 800), el router **re-fragmenta** el primer fragmento, generando a su vez dos trozos de 776 y 704 bytes de datos (ID=1 se **conserva**).
- El destino espera los tres fragmentos y los **reensambla** en el datagrama original de 2000 bytes.

> El **offset** sale en **unidades de 8 bytes**: para el fragmento que comienza en el byte 1480, el offset es `1480 / 8 = 185`. Por eso los fragmentos (salvo el último) tienen tamaños **múltiplos de 8**.

## Cómo podrías haberlo descubierto
Si quieres que IP funcione sobre cualquier tecnología (desde X.25 de 128 bytes hasta Ethernet de 1500 o fibra con MTU grande), tienes que afrontar que **lo que cabe en una red no cabe en la siguiente**. Las dos opciones son: *"obliga al emisor a usar la MTU más pequeña del camino"* (muy restrictivo si no la conoce) o *"deja que los routers rompan y marquen las piezas"* (más flexible). IP eligió la segunda. El **mínimo imprescindible** para que esto funcione es poder decir, en cada pieza:
1. *"Soy de este datagrama"* → **Identificación**.
2. *"Vengo de esta posición dentro del datagrama original"* → **Offset**.
3. *"Soy / no soy la última"* → **Flag MF**.

Si además el emisor quiere decir *"no me fragmentes"*, se añade el flag **DF** para que el router avise en lugar de partir. Esos cuatro campos son exactamente lo que se usa.

## Depende de
- [[Redes/ARC_Tema_3/Conceptos/IP y ARP\|IP y ARP]]: la fragmentación es una característica del datagrama IP.
- [[Redes/ARC_Tema_3/Conceptos/Router\|Router]]: los routers son los que fragmentan al atravesar redes con MTU inferior.
- [[Redes/ARC_Tema_1/Conceptos/Medios de Transmisión\|Medios de Transmisión]] (Tema 1) / [[Redes/ARC_Tema_1/Conceptos/Capa Física\|Capa Física]]: la MTU la imponen las tecnologías físicas.

## Permite entender
- Por qué una **pérdida pequeña** puede traducirse en una **retransmisión grande**: si se pierde un fragmento, se pierde el **datagrama entero** y lo tiene que retransmitir la capa superior.
- Por qué **TCP intenta descubrir la MTU del camino** (*Path MTU Discovery*): activando **DF** y escuchando los avisos ICMP de "fragmentation needed", para evitar fragmentar.
- Por qué **IPv6 elimina la fragmentación por los routers**: en IPv6 solo el **emisor** puede fragmentar; el router avisa y punto, para simplificar y acelerar el enrutamiento.
- Por qué los **múltiplos de 8** importan: el offset se cuenta en bloques de 8 bytes, para que quepa en los 13 bits del campo.

## Ejemplo
> [!example]
> Un servidor manda un fichero HTTP de 4 KB por TCP sobre IP sin DF. En el camino hay un enlace de MTU 576 bytes. Cuando el datagrama de 4096 bytes llega al router de ese enlace, **se fragmenta** en varios trozos de ≤576 bytes, todos con el mismo **ID**, offsets `0, 72, 144, …` (múltiplos de 8) y **MF=1** salvo el último (MF=0). El destino los reconstruye y entrega el datagrama de 4096 bytes a TCP (p. 32-35).

## Errores comunes
> [!warning]
> **No se reensambla en los routers intermedios**: cada router simplemente **reencamina** los fragmentos. El destino es el único que ensambla (p. 34). Confundirlo lleva a diseñar cachés inútiles.

> [!warning]
> **Un fragmento perdido = datagrama perdido**: no se puede recuperar el datagrama parcial. Por eso TCP prefiere **no fragmentar** y hace *Path MTU Discovery*.

> [!warning]
> **El offset está en múltiplos de 8 bytes**, no en bytes. Un offset de valor 185 significa "empieza en el byte 1480" (p. 35).

> [!warning]
> **DF no significa "importante"**, significa "no me partas": si está activo y el datagrama no cabe, el router lo **descarta** (y manda ICMP). Sin la gestión ICMP correcta, se produce el **"black hole MTU"**.

> [!warning]
> Si el **TTL** expira en un router mientras aún hay fragmentos esperando ensamblaje en el destino, el datagrama también se pierde (p. 36).

## Autoevaluación
> [!question]- ¿Por qué el reensamblaje se hace solo en el destino y no en routers intermedios?
> Porque entre dos puntos distintos de la red cada fragmento puede seguir **rutas diferentes** y llegar en **orden distinto**. Reensamblar en el camino obligaría a cada router a esperar y almacenar fragmentos, perdiendo las ventajas de un servicio sin conexión. El destino **sí tiene toda la información** y es el único que puede recomponer el datagrama (p. 34).

> [!question]- ¿Qué pasa si uno de los fragmentos llega después del timeout?
> El destino **descarta todos los fragmentos** del datagrama que ya tenía almacenados: *"los fragmentos ya recibidos se descartan"* (p. 34). El datagrama se da por perdido; si hace falta, la capa superior tendrá que retransmitirlo entero.

> [!question]- ¿Cuál es la MTU típica de Ethernet y por qué importa?
> **1500 bytes** de campo de datos (p. 32). Si un datagrama IP supera ese tamaño al entrar en Ethernet, el router de entrada tiene que **fragmentarlo** antes de encapsularlo en tramas (salvo que DF esté activo, en cuyo caso lo descarta).

## Contraste
> [!success] Verificado
> Mecanismo (identificación, offset en múltiplos de 8, flags DF/MF), MTU de 1500 bytes en Ethernet y reensamblaje solo en destino coinciden con **RFC 791** y con la literatura habitual (Tanenbaum). Sin discrepancias.

## Fuentes
- [[Redes/ARC_Tema_3/Fuente - ARC_Tema_3\|Fuente - ARC_Tema_3]], p. 32-37

## Mis notas
