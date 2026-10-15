---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-3-dcu-mpi-ua-26-27/conceptos/evaluacion-de-usabilidad/","tags":["materia/Usabilidad","tema/1.3"],"dg-note-properties":{"tipo":"concepto","aliases":["Métodos de evaluación de usabilidad","Usability testing","Inspección Indagación Test","Evaluación centrada en el usuario"],"tags":["materia/Usabilidad","tema/1.3"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Evaluación de usabilidad

> [!abstract] En una frase
> La **evaluación de usabilidad** es el **proceso para aprender de los usuarios el grado de usabilidad del sistema observándolos mientras lo utilizan** (p. 75); en MPIU+a se organiza en **tres grandes familias de métodos**: **Inspección, Indagación y Test** (p. 33, 69).

## ¿Qué problema resuelve?
Sin evaluación, el DCU se queda en teoría. Cada iteración necesita datos reales para decidir qué cambiar. Hay múltiples técnicas con costes y resoluciones muy distintas; el modelo clasifica las técnicas en tres familias para elegir la correcta según momento y presupuesto.

## Qué es
Es la **Fase 4** del [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]] (y se integra con la actividad 4 de la [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Actividades DCU (ISO 9241-210)\|ISO 9241-210]]). El material (p. 33, 69) la organiza en tres grupos:

### 1. Inspección

Los **expertos** examinan el sistema sin usuarios.

- **Evaluación Heurística**: expertos aplican heurísticas conocidas (típicamente las 10 de Nielsen).
- **Recorrido Cognitivo** (Cognitive Walkthrough): expertos simulan las tareas de un usuario novato.
- **Recorrido de Usabilidad Plural**: varios expertos recorren juntos.
- **Recorrido Cognitivo con Usuarios**: variante híbrida.
- **Estándares**: checklist contra normas (ej., WCAG).

Características: barata, rápida, descubre problemas obvios. No sustituye a usuarios reales.

### 2. Indagación

Se **recoge información** del usuario preguntando o mirando.

- **Observación de Campo**: ver al usuario en su entorno natural.
- **Focus Group** (Grupo de Discusión Dirigido): discusión guiada con un grupo.
- **Entrevistas**: individuales, estructuradas o semi.
- **Cuestionarios**: SUS, QUIS, PSSUQ, Likert.
- **Grabación del Uso (logging)**: capturar sesiones de uso real.

Características: entiende *por qué* y *qué piensa* el usuario; difícil de cuantificar.

### 3. Test

Se **mide** el uso real del sistema (o prototipo).

- **Medida de Prestaciones**: tiempo por tarea, tasa de éxito, errores.
- **Pensando en Voz Alta (Thinking Aloud)**: el usuario verbaliza mientras usa el sistema.
- **Interacción Constructiva**: dos usuarios resuelven juntos.
- **Test Retrospectivo**: tras la tarea, se repasa en vídeo con el usuario.
- **Método del Conductor**: un experto guía mientras el usuario conduce.
- **Ordenación de Tarjetas ([[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Card Sorting\|Card Sorting]])**: ya visto como técnica de diseño; aquí sirve también para evaluar categorizaciones.

Características: datos cuantitativos y cualitativos combinados; necesita participantes reales.

### Definición formal de usability testing (p. 75)

> *"Proceso que permite aprender de los usuarios el grado de usabilidad de un sistema informático observándolos mientras lo utilizan."*
> ([experienceux.co.uk](http://www.experienceux.co.uk/faqs/what-is-usability-testing/))

### En la práctica (p. 73–74)

En producción se añaden **métodos de telemetría**: análisis de logs, Google Analytics. Son indagación sobre uso real masivo.

## Cómo podrías haberlo descubierto
Para evaluar un sistema puedes hacer tres cosas: **que lo mire un experto** (inspección), **preguntar al usuario** (indagación) o **medir lo que hace** (test). Son tres accesos distintos a la realidad; cada uno capta algo que los otros no.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]]: la actividad 4 ISO es la evaluación.
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]]: su Fase 4.
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Card Sorting\|Card Sorting]]: aparece como técnica tanto en diseño como en evaluación.

## Permite entender
- Por qué **inspección + test** se combinan: la inspección detecta lo obvio barato; el test descubre lo real.
- Por qué el **thinking aloud** con 5 usuarios suele considerarse suficiente para la mayoría de problemas (regla de Nielsen "5 usuarios bastan"): se cubre más del 80 % de problemas con pocos sujetos.
- Por qué los **analytics** (Google Analytics, logs) son evaluación continua: el DCU exige monitorizar a largo plazo (actividad 4 ISO 9241-210).

## Ejemplo
> [!example]
> **Evaluar un formulario de registro**:
> - **Inspección heurística** (2 expertos, 1 h): detectan 8 problemas obvios (labels mal, errores poco claros).
> - **Thinking aloud** (5 usuarios, 30 min cada uno): descubren que el captcha es incomprensible, que el usuario no sabe qué es "DNI/NIE" y que al revisar un dato el formulario se vacía.
> - **Analytics del formulario de registro ya en producción**: muestran que el 42 % abandona en el paso 3 (donde fallaba el captcha).

## Errores comunes
> [!warning]
> - **Sustituir usuarios por expertos**: la inspección es barata pero NO descubre todo. Es complementaria.
> - **Hacer thinking aloud con 20 usuarios**: coste alto sin ganancia de información (ley de rendimiento decreciente).
> - **Fiar la evaluación a los cuestionarios al final**: la satisfacción autorreportada es subjetiva y poco diagnóstica.
> - **Evaluar solo en el laboratorio**: olvidar el contexto real (observación de campo) oculta problemas.

## Autoevaluación
> [!question]- ¿Qué tres familias de métodos reconoce MPIU+a?
> **Inspección, Indagación y Test** (p. 33, 69).

> [!question]- ¿Qué familia incluye el thinking aloud?
> **Test** — el usuario verbaliza mientras usa el sistema.

> [!question]- ¿Qué distingue inspección de test?
> La **inspección** la hacen expertos sin usuarios; el **test** mide a usuarios reales usando el sistema.

> [!question]- ¿Qué es el usability testing según el material?
> *"Proceso que permite aprender de los usuarios el grado de usabilidad de un sistema observándolos mientras lo utilizan"* (p. 75).

## Contraste
> [!success] Verificado
> La clasificación en Inspección / Indagación / Test es la de Lorés et al. (*Introducción a la IPO*, AIPO 2002) y refleja la de Nielsen (*Usability Engineering*, 1993). Las técnicas listadas son estándar en la IPO y aparecen en [Nielsen Norman Group](https://www.nngroup.com/) con los mismos nombres. La "regla de los 5 usuarios" es de Nielsen (1993, 2000), confirmada en [nngroup.com/articles/why-you-only-need-to-test-with-5-users](https://www.nngroup.com/articles/why-you-only-need-to-test-with-5-users/).

## Fuentes
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27\|Fuente - Tema 1.3-DCU-MPIUa-26-27]], p. 19, 33, 69–75.
- Externas: [experienceux.co.uk/faqs/what-is-usability-testing](http://www.experienceux.co.uk/faqs/what-is-usability-testing/), [nngroup.com](https://www.nngroup.com/).

## Mis notas
