---
{"dg-publish":true,"permalink":"/redes/arc-tema-1/conceptos/medios-de-transmision/","tags":["materia/redes","tema/introduccion"],"dg-note-properties":{"tipo":"concepto","aliases":["Medios Guiados","Medios No Guiados","Medio de Transmisión","Medio físico"],"tags":["materia/redes","tema/introduccion"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_1/Fuente - ARC_Tema_1]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Medios de Transmisión

> [!abstract] En una frase
> **Medio físico** por el que viaja la señal entre nodos de una red; se divide en **guiados** (cables) y **no guiados** (inalámbricos), y sus propiedades fijan la **velocidad**, **distancia** y **calidad** que la red puede alcanzar.

## ¿Qué problema resuelve?
Toda red necesita **propagar una señal** de un punto a otro. Esa señal no vive en el aire del enunciado: viaja por un **medio concreto** (un cable de cobre, una fibra de vidrio, el espectro electromagnético), y cada medio impone **sus propios límites** —cuánta información cabe, hasta dónde llega, cuánto ruido captura—. Elegir el medio es, en la práctica, elegir el **techo** de lo que la red podrá hacer.

## Qué es
Según el material (p. 13), hay **dos grandes familias**:

- **Medios guiados** (*wired*): la señal viaja **confinada** en un conductor físico (par de cobre, par trenzado, coaxial, fibra óptica).
- **Medios no guiados** (*wireless*): la señal se **propaga por el espectro electromagnético** (radio, microondas, infrarrojo, luz).

Las **características de la transmisión** vienen determinadas por el medio y por la señal (p. 13): **velocidad**, **distancia**, **calidad** (ruido, interferencias, distorsión de retardo…). El principio general es: **mayor ancho de banda → mayor velocidad**. Y hay una asimetría importante entre guiados y no guiados (p. 13):

- En **medios guiados**, el **medio en sí** es lo que más condiciona.
- En **medios no guiados**, lo que más condiciona es el **ancho de banda que produce la antena**.

### Medios guiados
- **Par de cobre** (p. 15): hasta ~50 m a <19.2 kbps; **mayor velocidad a menor distancia**. Problemas: **diafonía (crosstalk)** y sensibilidad al ruido.
- **Par trenzado** (p. 16): mejor inmunidad gracias al **trenzado** (más trenzados por metro → mejor calidad). Variantes:
  - **STP** (apantallado) y **UTP** (sin apantallar).
  - **Categorías de UTP** (p. 16): **Cat 3** (16 MHz, voz), **Cat 4** (20 MHz, voz y datos hasta 16 Mbps), **Cat 5** (100 MHz, 100 Mbps, FastEthernet y ATM), **Cat 5E y 6** (Gigabit Ethernet a 1 Gbps, ATM a 1.2 y 2.4 Gbps).
- **Cable coaxial** (p. 17): "el medio más versátil"; tipos de **50 Ω** y **75 Ω**. Capaz de transportar hasta **10 000 conversaciones de voz simultáneas**. Hoy **sustituido por fibra óptica** en LAN y CATV.
- **Fibra óptica** (p. 18): **inmune a interferencias electromagnéticas y diafonía**; ancho de banda **hasta Tbps**; **monomodo**: varios Gbps hasta **30 km sin repetidor**. Problemas: **dificultad en los empalmes**. Aplicaciones: enlaces de gran distancia, metropolitanos, bucle de abonado y LAN.

### Medios no guiados
- **Inalámbrico** (p. 19): transmisión y recepción vía **antena** sobre el **espectro electromagnético** (p. 14). Dos variantes:
  - **Direccional**: haz **enfocado**, requiere **alineamiento cuidadoso** de las antenas.
  - **Omnidireccional**: señal emitida en **todas direcciones**, recibida por **múltiples antenas**.

## Cómo podrías haberlo descubierto
Si pones a dos equipos a hablarse, la primera pregunta es "¿por dónde?". El cable más simple es un **par de cobre**: barato pero ruidoso y limitado en distancia. Un día alguien se da cuenta de que **trenzar los dos hilos** cancela buena parte de la interferencia: nace el **par trenzado**. Para distancias mayores aparece el **coaxial**, con una malla que apantalla. Y cuando se busca inmunidad total al ruido eléctrico y mucho ancho de banda, se pasa de electricidad a **luz** dentro de una **fibra**. En paralelo, para evitar la tiranía del cable se mira al **aire** y se descubre que la **antena** puede radiar la señal, con el coste de compartir el espectro con todo el mundo. La clasificación guiado/no guiado es simplemente **la línea entre "hay cable" y "no lo hay"**.

## Depende de
- [[Redes/ARC_Tema_1/Conceptos/Red de Área Local (LAN)\|Red de Área Local (LAN)]]: el PDF presenta estos medios como opción de **transmisión LAN** (p. 13).
- [[Redes/ARC_Tema_1/Conceptos/Capa Física\|Capa Física]]: la Capa Física del [[Redes/ARC_Tema_1/Conceptos/Modelo OSI\|Modelo OSI]] es la que especifica el medio, el nivel de señal y las velocidades (p. 23).

## Permite entender
- [[Redes/ARC_Tema_1/Conceptos/Topología de Red\|Topología de Red]]: el medio elegido limita las topologías físicas razonables (una fibra en bus es raro; un par trenzado en estrella con switch es lo típico).
- Las **categorías de Ethernet**: por qué Fast Ethernet pide Cat 5, Gigabit pide Cat 5E/6, etc.
- La **inmunidad de la fibra** frente al cobre, clave en entornos industriales y de larga distancia.

## Ejemplo
> [!example]
> Un edificio moderno cablea los puestos de trabajo con **UTP Cat 6** para Gigabit Ethernet; el **backbone** entre plantas se tiende con **fibra multimodo** por su mayor ancho de banda y menor sensibilidad a interferencias; y las salas de reuniones usan **WiFi** (medio no guiado omnidireccional) para la comodidad del usuario. Cada tramo elige el medio **que mejor resuelve su compromiso** entre coste, distancia e inmunidad al ruido (p. 13-19).

## Errores comunes
> [!warning]
> **Más ancho de banda no es gratis**: en guiados, mejorar de categoría de cable implica cambiar la infraestructura; en no guiados, el ancho de banda depende de la **antena** y del **espectro disponible**, que suele estar regulado (p. 13-14).

> [!warning]
> La **fibra** no es cara "por el vidrio", sino sobre todo por los **empalmes** y los equipos ópticos (p. 18). Y, pese a su velocidad, **no sustituye siempre al cobre** en el último tramo del cableado horizontal.

> [!warning]
> **Direccional ≠ mejor que omnidireccional**: una antena direccional da más alcance pero exige alineamiento; una omnidireccional cubre más zona pero reparte la potencia (p. 19).

## Autoevaluación
> [!question]- ¿Por qué una fibra óptica es inmune a la diafonía mientras un par de cobre no?
> Porque la fibra transmite **luz** confinada en el núcleo de vidrio, no una señal eléctrica, y por tanto **no induce ni recibe campos electromagnéticos** de los pares vecinos. El par de cobre sí, al transportar corriente, acopla señales a los pares adyacentes (p. 15, 18).

> [!question]- ¿Qué categoría mínima de UTP necesitas para Gigabit Ethernet?
> **Cat 5E** (o superior). Cat 5 llega a 100 Mbps / 100 MHz; Cat 5E y Cat 6 soportan Gigabit (p. 16).

> [!question]- En medios no guiados, ¿qué pesa más al determinar el ancho de banda: el "medio" (el aire) o la antena?
> La **antena**: el aire no cambia, pero el ancho de banda y el patrón de radiación dependen del diseño de la antena (p. 13, 19).

## Contraste
> [!success] Verificado
> Las categorías de UTP (3-6), las propiedades de la fibra monomodo (varios Gbps, 30 km sin repetidor) y la clasificación guiado/no guiado se han contrastado con fuentes externas (Wikipedia: *Transmission medium*, *Twisted pair*, *Optical fiber*) y coinciden con el material. No se han detectado discrepancias relevantes.

## Fuentes
- [[Redes/ARC_Tema_1/Fuente - ARC_Tema_1\|Fuente - ARC_Tema_1]], p. 13-19

## Mis notas
