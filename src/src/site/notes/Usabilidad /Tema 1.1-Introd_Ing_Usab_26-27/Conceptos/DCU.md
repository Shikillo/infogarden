---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-1-introd-ing-usab-26-27/conceptos/dcu/","tags":["materia/Usabilidad","tema/1.1","tema/1.3"],"dg-note-properties":{"tipo":"concepto","aliases":["Diseño Centrado en el Usuario","User-Centered Design","UCD","Human-Centered Design","HCD"],"tags":["materia/Usabilidad","tema/1.1","tema/1.3"],"nivel":1,"fuentes":["[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Fuente - Tema 1.1-Introd_Ing_Usab_26-27]]","[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# DCU (Diseño Centrado en el Usuario)

> [!abstract] En una frase
> El **Diseño Centrado en el Usuario (DCU)** es un **paradigma de la Interacción Persona-Ordenador** que coloca al usuario, sus necesidades, objetivos y capacidades, en el centro de todas las decisiones de diseño (p. 36).

## ¿Qué problema resuelve?
La historia del tema explica el porqué: el motivo de que las cosas sean difíciles de usar es "el énfasis en la tecnología, en vez de en el usuario" (Donald Norman, *The invisible computer*, p. 48). El DCU invierte ese orden: en lugar de preguntar *qué puede hacer la tecnología*, parte de *qué necesita hacer la persona* y deriva el sistema de ahí.

## Qué es
Aparece en el material como **"uno de los paradigmas más importantes" de la Interacción Persona-Ordenador (IPO/HCI)** (p. 36). No es un conjunto de pruebas finales, sino **un proceso integral** que atraviesa todas las fases del ciclo de vida:

- Investigar a los usuarios reales (necesidades, objetivos, limitaciones).
- Diseñar basándose en los [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Requerimientos del Usuario\|Requerimientos del Usuario]].
- Prototipar.
- Evaluar con los propios usuarios.
- Iterar.

La norma de referencia es la **ISO 9241-210:2019**, cuyo título es precisamente *Human-centred design for interactive systems*: el DCU es su versión canonizada. En este tema no se detalla el modelo (eso es [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Fuente - Tema 1.1-Introd_Ing_Usab_26-27\|el Tema 1.3 - DCU / MPIU+a]]), pero sí se fija su papel: es el puente entre la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]] como *objetivo* y la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Ingeniería de Usabilidad\|Ingeniería de Usabilidad]] como *método*.

## Cómo podrías haberlo descubierto
Si aceptas la definición ISO de usabilidad ("por determinados usuarios... en un contexto especificado"), para construir un sistema usable necesitas *decidir qué usuarios* y *qué contexto* antes de diseñar. Y la única forma honesta de hacerlo es **mirar al usuario**: observar, preguntar, probar con él. El DCU es la institucionalización de ese sentido común.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]]: define el objetivo que el DCU busca garantizar.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Requerimientos del Usuario\|Requerimientos del Usuario]]: son la entrada principal del proceso.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]: amplía "qué usuarios" para no excluir a nadie.

## Permite entender
- Por qué iterar: la primera versión nunca sabe lo suficiente del usuario.
- Por qué los prototipos y las pruebas con usuarios son centrales en la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Ingeniería de Usabilidad\|Ingeniería de Usabilidad]].
- La **ISO 9241-210:2019** operacionaliza el DCU en **4 actividades iterativas** → ver [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Actividades DCU (ISO 9241-210)\|Actividades DCU (ISO 9241-210)]].
- Los **4 principios de equipo** que preparan un DCU real → ver [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Principios del DCU\|Principios del DCU]].
- La diferencia respecto al "Diseño Centrado en el **Uso**" (modelado, Ing. Software) → ver [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Diseño Centrado en el Uso\|Diseño Centrado en el Uso]].
- El **modelo concreto** usado en el curso es el **[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]]** (Granollers, 2004), que lleva el DCU al ciclo de vida completo e integra la **[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]** desde el principio.

## Ejemplo
> [!example]
> **IU como "puerta"** (p. 49): el material dice que la Interfaz de Usuario (IU) es "la puerta del usuario a la funcionalidad del sistema subyacente". El DCU diseña esa puerta pensando en *quién la va a cruzar*: su altura, su peso, su destreza, su familiaridad con otros picaportes. En vez de poner la puerta más barata y esperar a ver quién puede abrirla.

## Errores comunes
> [!warning]
> - **Confundir DCU con "preguntar al cliente"**: el cliente no es necesariamente el usuario; el DCU pone en el centro a *quien va a usar* el sistema.
> - **Reducir el DCU a tests al final**: es un proceso iterativo *desde el principio*, no una fase de validación.
> - **Saltarse la observación real**: imaginar lo que querría el usuario no es DCU; es diseño egocéntrico con otro nombre.

## Autoevaluación
> [!question]- ¿De qué disciplina es el DCU uno de los paradigmas más importantes?
> De la **Interacción Persona-Ordenador (IPO)**, también llamada *Human-Computer Interaction (HCI)*.

> [!question]- ¿Por qué el DCU es iterativo?
> Porque las necesidades reales del usuario no se descubren todas al principio: cada prototipo y cada evaluación revelan nuevas, que obligan a volver atrás y rediseñar.

## Contraste
> [!success] Verificado
> [Wikipedia: Diseño Centrado en el Usuario](https://es.wikipedia.org/wiki/Dise%C3%B1o_centrado_en_el_usuario) coincide con el material: filosofía/proceso cuyas decisiones se basan en "necesidades, objetivos, expectativas, motivaciones y capacidades de los usuarios". Las etapas (conocer al usuario, diseñar, probar) también se corresponden.

> [!info] Matizado — DCU vs. Human-Centered Design
> La ISO 9241-210:2019 utiliza el término *Human-Centered Design* (DCH, Diseño Centrado en el Ser Humano). En la literatura española se usa el equivalente *DCU*: el material (y las guías ISO en español) tratan ambos como sinónimos a efectos prácticos. [Wikipedia: Human-centered design](https://en.wikipedia.org/wiki/Human-centered_design) confirma esta identificación.

## Fuentes
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Fuente - Tema 1.1-Introd_Ing_Usab_26-27\|Fuente - Tema 1.1-Introd_Ing_Usab_26-27]], p. 36, 48–50.
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27\|Fuente - Tema 1.3-DCU-MPIUa-26-27]], p. 3–20 (todo el tema).
- Externas: [es.wikipedia.org/wiki/Diseño_centrado_en_el_usuario](https://es.wikipedia.org/wiki/Dise%C3%B1o_centrado_en_el_usuario), [en.wikipedia.org/wiki/Human-centered_design](https://en.wikipedia.org/wiki/Human-centered_design), [iso.org/standard/77520.html](https://www.iso.org/standard/77520.html).

## Mis notas
