---
{"dg-publish":true,"permalink":"/redes/arc-tema-2/conceptos/ethernet-conmutada-fast-gigabit/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Switched Ethernet","Fast Ethernet","Gigabit Ethernet","10 Gigabit Ethernet","10G Ethernet"],"tags":["materia/redes","tema/protocolos"],"nivel":2,"fuentes":["[[Redes/ARC_Tema_2/Fuente - ARC_Tema_2]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Ethernet Conmutada / Fast / Gigabit / 10G

> [!abstract] En una frase
> Serie de **evoluciones de [[Redes/ARC_Tema_2/Conceptos/Ethernet\|Ethernet]]** que, manteniendo el mismo formato de trama y direccionamiento de 48 bits, van sustituyendo el **canal compartido** por **enlaces dedicados a un switch** y suben la velocidad de **10 Mbps a 10 Gbps**.

## ¿Qué problema resuelve?
La Ethernet clásica tiene un problema **estructural**: todas las estaciones comparten el canal y, a medida que se añaden más, **el rendimiento por estación se deteriora** (p. 27). Para seguir creciendo sin tirar los estándares a la basura, se busca una evolución que:

1. **Elimine las colisiones** sin cambiar el formato de trama.
2. **Permita subir la velocidad** por saltos (×10) manteniendo compatibilidad.
3. Se instale **sobre cableado estándar**, no sobre coaxial grueso.

Las versiones **conmutada, Fast, Gigabit y 10G** son la respuesta a esas tres exigencias.

## Qué es
### Ethernet conmutada (p. 27-29)
El cableado deja de ser *"un cable largo"* y pasa a ser una **arquitectura en estrella** alrededor de un elemento central:

- Cada estación tiene un **cable dedicado** que termina en un **concentrador central** (p. 27).
- **Añadir y quitar estaciones** es mucho más fácil que en el bus clásico.
- La longitud del cable se reduce a **100 m** con par trenzado telefónico, o **200 m** con cable **Categoría 5** (p. 27).

Dos tipos de concentrador (p. 28):

| Concentrador | Comportamiento |
|---|---|
| **Hub** | Equivalente al cable largo clásico. Repite todo por todos los puertos ⇒ **mismo dominio de colisión**, no aumenta la capacidad. |
| **Switch** | Determina a qué puerto va cada trama por su MAC destino. **Sin colisiones**, capacidad agregada mucho mayor, beneficios de seguridad (p. 29). |

El material es explícito (p. 29): *"Switch es la solución"*. Con switch *"no hay colisión"* y hay **beneficios de seguridad** (una estación solo ve el tráfico destinado a ella). Y, muy importante, permite subir la velocidad: *"podría resolver este problema aumentando el habla de la Ethernet básica de 1 Mbps a 10 Mbps, 100 Mbps o incluso 1 Gbps"* (p. 29).

### Fast Ethernet (p. 30)
- **100 Mbps**.
- Cableado original compatible con el existente.

### Gigabit Ethernet (p. 31-32)
Las **metas** del estándar fueron explícitamente (p. 31):

1. Aumentar **×10** el rendimiento de Fast Ethernet.
2. Mantener **compatibilidad** con Ethernet clásica y Fast.
3. Servicio de **datagramas sin acuse de recibo**, con **unidifusión** y **difusión**.
4. **Mismo esquema de direccionamiento de 48 bits**.
5. **Mismo formato de trama**, incluidos los **tamaños mínimo y máximo**.

Admite dos topologías (p. 32):
- **Ethernet de dos estaciones**: enlace directo entre dos equipos.
- **Ethernet con múltiples estaciones**: topología típica en switch.

### 10 Gigabit Ethernet (p. 33)
El siguiente salto, con **cableado dedicado**: mantiene la misma filosofía de trama y direccionamiento, cambiando capa física y medio.

## Cómo podrías haberlo descubierto
Si el cuello de botella es el **canal compartido**, la solución natural es **dar a cada estación su propio canal**. Para eso basta con **llevar un cable por estación a un elemento central**. Si ese elemento solo repite (hub), **no has resuelto nada**: sigue siendo un bus con forma de estrella. Pero si **mira la MAC destino** y envía la trama **solo al puerto correcto** (switch), has conseguido dos cosas a la vez: **eliminar colisiones** y **sumar ancho de banda**. A partir de ahí, subir de 100 Mbps a 1 Gbps o 10 Gbps es cuestión de **mejorar la capa física** (cableado, codificación, señalización), sin tocar el formato de trama.

## Depende de
- [[Redes/ARC_Tema_2/Conceptos/Ethernet\|Ethernet]]: parte de la evolución del mismo estándar.
- [[Redes/ARC_Tema_2/Conceptos/Subcapa MAC\|Subcapa MAC]]: la MAC sigue siendo la misma; cambia la arquitectura física.
- [[Redes/ARC_Tema_2/Conceptos/Protocolo Subcapa MAC - Formato Trama\|Protocolo Subcapa MAC - Formato Trama]]: Gigabit insiste en mantener el **mismo formato de trama**.
- [[Redes/ARC_Tema_1/Conceptos/Medios de Transmisión\|Medios de Transmisión]] (Tema 1): cada salto cambia los requisitos de cable (categoría, fibra).

## Permite entender
- Por qué una red moderna **ya no sufre colisiones**: el switch las ha hecho desaparecer.
- Por qué un **hub no es un switch**: solo este último separa dominios de colisión y suma capacidad.
- La estabilidad de Ethernet como estándar: **40 años subiendo velocidad sin cambiar la trama**.

## Ejemplo
> [!example]
> Una oficina moderna: cada puesto va por un **cable UTP cat 5e** de ≤100 m a un **switch Gigabit**. Dos usuarios enviando ficheros al mismo tiempo pueden hacerlo a **1 Gbps cada uno**, porque sus flujos van por **puertos distintos** del switch, sin interferirse. En un hub, ambos compartirían la misma capacidad y pelearían por ella (p. 27-29, 32).

## Errores comunes
> [!warning]
> **Hub ≠ switch**. Instalar un hub en una topología en estrella no elimina las colisiones: *"los concentradores no aumentan la capacidad: son equivalentes al cable largo único de la Ethernet clásica"* (p. 27).

> [!warning]
> Subir de 100 Mbps a 1 Gbps **no es "una Ethernet distinta"**: es la misma Ethernet con otra capa física. Por eso un adaptador Gigabit sabe hablar también a 100 Mbps y 10 Mbps, por **autonegociación**.

> [!warning]
> Gigabit **mantiene el tamaño mínimo de trama** (p. 31). Para que CSMA/CD siguiera funcionando en modo compartido se recurrió al *carrier extension*, pero con switch (lo normal) ya no es necesario.

> [!warning]
> Las categorías de cable **importan**: Fast Ethernet funciona en cat 5, Gigabit necesita cat 5e o superior, y 10 Gigabit exige cat 6/6a o fibra. Pinchar un cable viejo en un switch moderno no da automáticamente su velocidad máxima.

## Autoevaluación
> [!question]- ¿Por qué el estándar Gigabit insistió en mantener el mismo formato de trama que la Ethernet original?
> Para preservar la **compatibilidad hacia atrás**: todo el software, los equipos y el direccionamiento (**48 bits**) existentes siguen funcionando. Cambia la **capa física**, no la trama (p. 31).

> [!question]- Diferencia entre hub y switch en Ethernet conmutada.
> El **hub** repite cada señal por todos los puertos, por lo que todas las estaciones siguen compartiendo el mismo dominio de colisión (equivalente al cable largo clásico, p. 27). El **switch** mira la **MAC destino** y envía la trama **solo al puerto correcto**: no hay colisiones, hay más capacidad agregada y hay beneficios de seguridad (p. 28-29).

## Contraste
> [!success] Verificado
> Las velocidades (10/100/1000/10000 Mbps), la distinción hub/switch, la longitud máxima del cable (100 m con par trenzado) y las metas de Gigabit Ethernet se han contrastado con Wikipedia (*Ethernet switch*, *Fast Ethernet*, *Gigabit Ethernet*, *10 Gigabit Ethernet*). Coincide con el material.

## Fuentes
- [[Redes/ARC_Tema_2/Fuente - ARC_Tema_2\|Fuente - ARC_Tema_2]], p. 27-33

## Mis notas
