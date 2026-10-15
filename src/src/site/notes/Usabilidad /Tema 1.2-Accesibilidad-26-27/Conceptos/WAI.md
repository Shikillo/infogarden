---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-2-accesibilidad-26-27/conceptos/wai/","tags":["materia/Usabilidad","tema/1.2"],"dg-note-properties":{"tipo":"concepto","aliases":["Web Accessibility Initiative","Iniciativa de Accesibilidad Web"],"tags":["materia/Usabilidad","tema/1.2"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# WAI (Web Accessibility Initiative)

> [!abstract] En una frase
> La **WAI** es el **grupo permanente del [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]], creado en 1997**, que promueve la accesibilidad en la Web mediante tecnología, normas (como las [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]]), herramientas, educación e investigación (p. 53).

## ¿Qué problema resuelve?
El [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]] cubre toda la Web, pero la accesibilidad exige atención específica: directrices concretas, test tools, evangelización, investigación. La WAI centraliza esa atención en un **grupo dedicado** con capacidad de publicar recomendaciones.

## Qué es
Es un grupo de trabajo permanente dentro del [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]] (p. 53). Lo fundaron el W3C y la Casa Blanca en **1997**. Sus actividades, agrupadas en 5 líneas (p. 53):

1. **Tecnología**: incorpora accesibilidad a los estándares web (HTML, CSS, ARIA).
2. **Normas (Guidelines)**: publica las **[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]]**, ATAG (herramientas de autoría) y UAAG (agentes de usuario).
3. **Herramientas**: validación y reparación de accesibilidad.
4. **Educación y formación**: materiales de aprendizaje.
5. **Investigación y desarrollo (I+D)**.

### Grupos de trabajo (p. 54)

- **AG WG** (Accessibility Guidelines Working Group, antes WCAG WG): mantiene las WCAG.
- **APA WG** (Accessible Platform Architectures).
- **ARIA WG** (Accessible Rich Internet Applications): el conjunto de atributos `aria-*` para accesibilidad de aplicaciones web dinámicas.
- **EOWG** (Education and Outreach Working Group): **cerrado en 2024**.
- **WAI IG** (WAI Interest Group).

## Cómo podrías haberlo descubierto
Si el [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]] quiere coordinar los estándares de la Web y la accesibilidad es un **tema vertical** que atraviesa HTML, CSS, APIs, autoría y navegación, lo lógico es un grupo propio que coordine lo relativo a ella en vez de dejarlo distribuido entre otros grupos.

## Depende de
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]]: la WAI es un grupo *dentro* del W3C; su autoridad viene de ahí.

## Permite entender
- Por qué las **[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]]** llevan "W3C" en su autoría: son el entregable principal de la WAI, que es un grupo del W3C.
- Por qué existen tres conjuntos de directrices (**WCAG** para contenido, **ATAG** para herramientas de autoría, **UAAG** para agentes de usuario): la WAI cubre los tres actores del ecosistema web.
- Por qué cita Tim Berners-Lee ("El poder de la Web está en su universalidad", p. 45): es el fundador del W3C que da el mandato político a la WAI.

## Ejemplo
> [!example]
> Cuando un desarrollador usa `aria-label="Cerrar"` en un botón con solo un icono de cruz, está usando una tecnología (ARIA) definida por el **ARIA WG** de la WAI, para que un lector de pantalla lea "Cerrar" aunque no haya texto visible.

## Errores comunes
> [!warning]
> - **Confundir WAI con WCAG**: la WAI es *el grupo*; las WCAG son *un entregable* de ese grupo.
> - **Pensar que la WAI es independiente del W3C**: no lo es; es un grupo dentro del W3C, dependiente de su infraestructura y gobernanza.

## Autoevaluación
> [!question]- ¿Cuándo y por qué se creó la WAI?
> En **1997**, por el [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]] (con el apoyo de la Casa Blanca), para dedicar atención específica a la accesibilidad web.

> [!question]- ¿Qué publicación de la WAI es la que se usa como referencia legal en la mayoría de normativas?
> Las **[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]]** (Web Content Accessibility Guidelines).

## Contraste
> [!success] Verificado
> [Wikipedia: Web Accessibility Initiative](https://en.wikipedia.org/wiki/Web_Accessibility_Initiative) confirma fecha de fundación (1997) y origen (W3C con endorsement de la Casa Blanca). Las cinco actividades y los grupos de trabajo coinciden con la descripción del material.

## Fuentes
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27\|Fuente - Tema 1.2-Accesibilidad-26-27]], p. 45, 50, 52–54.
- Externas: [w3.org/WAI](http://www.w3.org/WAI), [en.wikipedia.org/wiki/Web_Accessibility_Initiative](https://en.wikipedia.org/wiki/Web_Accessibility_Initiative), [es.wikipedia.org/wiki/Web_Accessibility_Initiative](https://es.wikipedia.org/wiki/Web_Accessibility_Initiative).

## Mis notas
