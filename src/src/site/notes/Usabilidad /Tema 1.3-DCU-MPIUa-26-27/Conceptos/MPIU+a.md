---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-3-dcu-mpi-ua-26-27/conceptos/mpiu-a/","tags":["materia/Usabilidad","tema/1.3"],"dg-note-properties":{"tipo":"concepto","aliases":["MPIu+a","MPIUa","Modelo de Proceso de la Ingeniería de la Usabilidad y de la Accesibilidad"],"tags":["materia/Usabilidad","tema/1.3"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# MPIU+a

> [!abstract] En una frase
> El **MPIU+a** (Modelo de Proceso de la Ingeniería de la Usabilidad y de la Accesibilidad) es un **método de [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|Diseño Centrado en el Usuario]]** que integra la **Ingeniería del Software**, la **Ingeniería de la Usabilidad** y la **[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]** en el ciclo de vida del software (Granollers, 2004, Universitat de Lleida; p. 24, 26).

## ¿Qué problema resuelve?
El [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]] como paradigma dice *qué hacer* (centrar el diseño en el usuario), pero no *cómo encajarlo* con el proceso de Ingeniería del Software que ya existe en la organización (análisis, diseño, codificación, pruebas, despliegue). El MPIU+a propone un **modelo de proceso concreto** que superpone las dos ingenierías e integra la accesibilidad como componente desde el principio (p. 26).

## Qué es
Es la **propuesta metodológica central** del Tema 1.3. Nace como **Tesis Doctoral de Toni Granollers (Universitat de Lleida, 2004)**: *"MPIu+a. Una metodología que integra la Ingeniería del Software, la Interacción Persona-Ordenador y la Accesibilidad en el contexto de equipos de desarrollo multidisciplinares"* (p. 83).

### Características (p. 26, 28)

- **Tecnológicamente independiente**: no exige una tecnología concreta.
- **Aplicable a cualquier proyecto** independientemente de su clase y envergadura.
- Se **adapta a los modelos mentales** de los integrantes de equipos multidisciplinares.
- **Muy simple**.
- Sigue los **principios del DCU**.
- Fomenta un desarrollo **evolutivo: iterativo e incremental**.
- **Integra** la Ingeniería del Software + la Ingeniería de la Usabilidad + la Accesibilidad.
- **Consistente con los estándares de calidad** relacionados (ISO 9241-210:2019, WCAG, etc.).

### Los tres pilares (p. 28–39)

El modelo descansa sobre **tres pilares** conceptuales que atraviesan todas las fases:

1. **Organización conceptual** — procesos bien definidos y adaptables.
2. **El usuario** — presente en todas las etapas.
3. **Iteratividad** — se vuelve atrás tantas veces como haga falta.

Además es **adaptado para equipos multidisciplinares** y **validado experimentalmente** (en la propia tesis de Granollers).

### Las 6 fases (p. 40)

1. **Análisis** — ver [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Fases de MPIU+a\|Fases de MPIU+a]].
2. **Diseño**.
3. **Prototipado** — ver [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Prototipado\|Prototipado]].
4. **Evaluación** — ver [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Evaluación de usabilidad\|Evaluación de usabilidad]].
5. **Implementación**.
6. **Lanzamiento**.

Cada fase tiene **entregables definidos** (SRS, SDP, prototipos, informes de test…) y **técnicas asociadas** ([[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Stakeholders\|Stakeholders]], [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Card Sorting\|Card Sorting]], heurística, thinking aloud…).

## Cómo podrías haberlo descubierto
Si tienes la Ingeniería del Software (que estructura el "cómo construir") y la Ingeniería de la Usabilidad (que estructura "cómo mejorar la experiencia"), lo natural es **superponer sus ciclos**: cada fase de Ingeniería SW tiene su contrapartida de usabilidad (requisitos SW ↔ requisitos de usuario; test unitarios ↔ test con usuarios). Añadir la accesibilidad como requisito transversal cierra el modelo. Eso es MPIU+a.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]]: su paradigma base; MPIU+a es *un modo* de hacer DCU.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]]: su objetivo principal.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]: su componente transversal (el "+a").
- Ingeniería del Software: su estructura organizativa (fases, entregables).

## Permite entender
- Por qué el método propuesto por el curso se llama "+a": la accesibilidad no es un añadido tardío, está en el proceso desde el análisis.
- Por qué cada fase lleva técnicas de usabilidad diferentes: el nivel de madurez del artefacto cambia (no se usa thinking aloud sobre un boceto en papel ni card sorting en producción).
- La relación con la ISO 9241-210:2019: las **4 actividades clave** de la ISO ([[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Actividades DCU (ISO 9241-210)\|Actividades DCU (ISO 9241-210)]]) se corresponden con las fases 1–4 de MPIU+a.

## Ejemplo
> [!example]
> **Diseño de un portal de transparencia municipal**: en MPIU+a, se empezaría con un análisis etnográfico y entrevistas a [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Stakeholders\|Stakeholders]] (vecinos, administración, periodistas); se harían prototipos de papel y wireframes evaluados con usuarios reales (thinking aloud, card sorting); el frontend se desarrollaría cumpliendo WCAG 2.1 AA (accesibilidad desde el día 1); al lanzar, se monitorizaría el uso real (post-lanzamiento ≠ mantenimiento, p. 82).

## Errores comunes
> [!warning]
> - **Confundir MPIU+a con "metodología ágil"**: no son incompatibles, pero MPIU+a estructura ingeniería de usabilidad+accesibilidad; ágil estructura la cadena de entrega. Pueden combinarse.
> - **Reducirlo a "DCU con fases"**: la novedad es la **integración** con Ingeniería del Software y la **accesibilidad transversal**.
> - **Pensar que post-lanzamiento = mantenimiento**: el material lo distingue explícitamente (p. 82). Post-lanzamiento es *analizar el uso real*.

## Autoevaluación
> [!question]- ¿Qué tres disciplinas integra MPIU+a?
> **Ingeniería del Software + Ingeniería de la Usabilidad + Accesibilidad** (p. 26).

> [!question]- ¿Cuáles son los tres pilares conceptuales?
> **Organización conceptual, usuario e iteratividad** (p. 28).

> [!question]- ¿Cuáles son las 6 fases del modelo?
> **Análisis, Diseño, Prototipado, Evaluación, Implementación, Lanzamiento** (p. 40).

> [!question]- ¿Quién propuso el MPIU+a y dónde?
> **Toni Granollers** en su **Tesis Doctoral** de la **Universitat de Lleida** (2004).

## Contraste
> [!success] Verificado
> El MPIU+a es un modelo académico específico del grupo GRIHO de la Universitat de Lleida, publicado como tesis doctoral en 2004 por Toni Granollers y mantenido en [curso-ipo.com](https://curso-ipo.com/fases-mpiua/) y [griho.udl.cat](https://griho.udl.cat/). No tiene artículo propio en Wikipedia, pero sí referencias en la literatura española de IPO (Lorés et al., AIPO 2002). La definición y características coinciden con las fuentes primarias.

> [!info] Por qué no está en Wikipedia
> Es un modelo académico de ámbito español, no un estándar internacional (como el ISO 9241-210). Esto limita la verificación independiente a las publicaciones del propio grupo GRIHO y a bibliografía universitaria española. No hay discrepancias detectadas con esa literatura.

## Fuentes
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27\|Fuente - Tema 1.3-DCU-MPIUa-26-27]], p. 24–40, 83.
- Externas: [curso-ipo.com/fases-mpiua](https://curso-ipo.com/fases-mpiua/), tesis doctoral Granollers (Universitat de Lleida, 2004).

## Mis notas
