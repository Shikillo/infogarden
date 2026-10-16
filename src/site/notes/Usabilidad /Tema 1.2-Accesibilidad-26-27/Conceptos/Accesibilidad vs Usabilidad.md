---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-2-accesibilidad-26-27/conceptos/accesibilidad-vs-usabilidad/","tags":["materia/Usabilidad","tema/1.2"],"dg-note-properties":{"tipo":"concepto","aliases":["Accesibilidad y Usabilidad","Cuatro casos accesibilidad usabilidad"],"tags":["materia/Usabilidad","tema/1.2"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Accesibilidad vs Usabilidad

> [!abstract] En una frase
> **[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]** y **[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]]** son dimensiones distintas pero relacionadas: una web puede ser cualquiera de las **cuatro combinaciones** posibles — ni usable ni accesible, usable pero no accesible, accesible pero no usable, o **las dos**, que es el ideal del [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Diseño Universal\|Diseño Universal]] (p. 98–102).

## ¿Qué problema resuelve?
Es común confundir ambos términos o pensar que uno implica el otro. El material (p. 98) deja claro que *"no es lo mismo accesibilidad que usabilidad"*: hay webs usables para quienes pueden acceder, y webs accesibles con interfaces torpes. Entender los cuatro casos ayuda a diagnosticar y priorizar correcciones.

## Qué es
### Los cuatro casos (p. 99–102)

#### A. Ni usable ni accesible
> El caso **más habitual** (p. 99).

- El diseño no ha tenido en cuenta ni parámetros de accesibilidad ni técnicas de usabilidad.
- Solo "funciona" (y mal) para personas sin discapacidad y con tiempo para aprenderse la interfaz.

#### B. Usable y no accesible
> Solo es usable para quienes pueden acceder a sus funcionalidades (p. 100).

- Se aplicaron técnicas de [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]] (iteración, pruebas con usuarios "promedio") pero sin pensar en [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Discapacidad\|discapacidad]].
- Resultado: para el usuario típico, es un buen producto; para los demás, no existe.
- Ejemplo: una app muy pulida pero sin soporte de teclado ni etiquetas accesibles.

#### C. Accesible y no usable
> Equivalente a A), pero con un abanico mayor de población que notará la falta de usabilidad (p. 101).

- Cumple las [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]] formalmente, pero la interfaz es torpe para cualquier usuario, incluido quien usa tecnología asistiva.
- Pasó la auditoría automatizada pero no se pensó en el flujo real.
- "Más accesible" pero no "mejor".

#### D. Usable y accesible
> El **caso ideal**, el más escaso (p. 102).

- Representa la idea básica del [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Diseño Universal\|Diseño Universal]]: favorece el acceso universal *y además* lo hace de manera usable.
- Es lo que debería ser el objetivo de la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Ingeniería de Usabilidad\|Ingeniería de Usabilidad]].

### El debate (p. 103)

> "Algunos autores consideran que la Accesibilidad es parte de la Usabilidad y otros que la Usabilidad es parte de la Accesibilidad."

El material opta por una posición neutra: *"en cualquier caso, la accesibilidad favorece la usabilidad"*. Y recuerda la postura de la **ISO 25010**, donde la accesibilidad **es un atributo de la usabilidad** (ver [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]).

Los beneficios se refuerzan mutuamente (p. 103, Gutiérrez y Restrepo, SIDAR):

- Incrementa la **cuota de mercado** y la **audiencia**.
- Mejora la **eficiencia del sitio** (código más limpio).
- Transmite **responsabilidad social**.
- **Cumple legislación**.

## Cómo podrías haberlo descubierto
El experimento mental es sencillo: cruza dos ejes binarios (usable/no, accesible/no). Salen 4 cuadrantes. Observa el mundo real y ponle ejemplos a cada uno. Al hacerlo, descubres que no son dimensiones idénticas: hay webs claramente en B o en C.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]]: uno de los dos ejes.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]: el otro eje.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Diseño Universal\|Diseño Universal]]: el objetivo del caso D.

## Permite entender
- Por qué cumplir WCAG AA **no basta** para tener una buena [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Experiencia de Usuario\|Experiencia de Usuario]]: puedes estar en el caso C (accesible, no usable).
- Por qué un sitio muy pulido para el "usuario promedio" puede fracasar con una auditoría de accesibilidad: estás en el caso B.
- Por qué el [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Diseño Universal\|Diseño Universal]] es más que la suma de "accesibilidad + usabilidad": busca el caso D desde el origen, no por capas.

## Ejemplo
> [!example]
> - **Caso A**: una web corporativa de 2005 sin mantener, con menús flash, texto gris claro sobre blanco y navegación caótica.
> - **Caso B**: una app de startup muy intuitiva pero donde los botones son `div` con *onclick* en vez de `button`, sin acceso por teclado y sin ARIA.
> - **Caso C**: una web pública que cumple WCAG 2.1 AA pero donde el flujo para pedir cita son 7 pasos innecesarios y un formulario confuso.
> - **Caso D**: gov.uk — simplicidad extrema, foco claro de navegación por teclado, contraste alto, tipografía grande, sin elementos superfluos.

## Errores comunes
> [!warning]
> - **"Si es accesible, es usable"**: falso (caso C existe).
> - **"Si es usable, no hace falta accesibilidad"**: falso (caso B excluye a mucha gente).
> - **Confundir "cumplir WCAG" con "ser accesible"**: cumplir las [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]] es necesario pero no suficiente; hay accesibilidad en experiencia que las WCAG no capturan.

## Autoevaluación
> [!question]- ¿Cuál de los cuatro casos es, según el material, el más habitual?
> El **caso A — Ni usable ni accesible**. (p. 99)

> [!question]- ¿Cuál es el caso ideal y a qué paradigma de diseño corresponde?
> El **caso D — Usable y accesible**, que es la idea básica del **[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Diseño Universal\|Diseño Universal]]**.

> [!question]- Según la norma ISO 25010, ¿la accesibilidad es parte de la usabilidad o viceversa?
> La ISO 25010 trata la **accesibilidad como un atributo de la usabilidad** (ver también Tema 1.1).

## Contraste
> [!success] Verificado
> El esquema de los cuatro casos es la pedagogía clásica del Seminario Iberoamericano sobre Discapacidad y Accesibilidad en la Red (**SIDAR**), confirmada en [sidar.org](http://www.sidar.org/). La relación formal entre accesibilidad y usabilidad en la **ISO 25010** se verifica en [iso25000.com/.../iso-25010](https://iso25000.com/index.php/normas-iso-25000/iso-25010).

## Fuentes
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27\|Fuente - Tema 1.2-Accesibilidad-26-27]], p. 98–104.
- Externas: [usabilitygeek.com — The Difference between Web Site Usability and Accessibility](http://usabilitygeek.com/the-difference-between-web-site-usability-and-accessibility/), [sidar.org](http://www.sidar.org/).

## Mis notas
