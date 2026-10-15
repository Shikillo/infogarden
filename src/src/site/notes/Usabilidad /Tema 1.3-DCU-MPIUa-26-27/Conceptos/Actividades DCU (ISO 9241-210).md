---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-3-dcu-mpi-ua-26-27/conceptos/actividades-dcu-iso-9241-210/","tags":["materia/Usabilidad","tema/1.3"],"dg-note-properties":{"tipo":"concepto","aliases":["Actividades clave del DCU","4 actividades ISO 9241-210","Human-centered design activities"],"tags":["materia/Usabilidad","tema/1.3"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Actividades DCU (ISO 9241-210)

> [!abstract] En una frase
> La **ISO 9241-210:2019** fija **4 actividades iterativas** que todo proceso de [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]] debe realizar: **(1) entender el contexto de uso, (2) especificar los requisitos del usuario, (3) producir soluciones de diseño y (4) evaluar el diseño** (p. 16–19).

## ¿Qué problema resuelve?
Decir "centra el diseño en el usuario" es tan amplio que cada equipo lo interpreta de forma distinta. La ISO 9241-210 convierte el [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]] en un **conjunto operativo de actividades** con entradas, salidas y una regla fundamental: **se iteran**, no se hacen una vez.

## Qué es
Son las **4 actividades clave** definidas en la norma **ISO 9241-210:2019 — "Ergonomics of human-system interaction. Part 210: Human-centred design for interactive systems"** (p. 7).

### 1. Entender y especificar el contexto de uso (p. 16)

Caracterizar el escenario real:

- **Usuarios**: conocimientos, habilidades, experiencia, educación, entrenamiento, atributos físicos, hábitos, capacidades motor-sensoriales. Identificar **grupos distintivos** (p. ej., expertos vs. novatos).
- **Tarea**: objetivos, frecuencia y duración.
- **Entorno**: organizacional (estructura del grupo), técnico (hardware, red) y físico (temperatura, humedad, salud y seguridad).

### 2. Especificar los requisitos del usuario (p. 17)

- Identificar **personas y usuarios relevantes**.
- **Proponer objetivos claros**.
- Establecer **puntos de referencia** con los que comparar el diseño.
- **Evidenciar** que los requerimientos han sido aceptados por sus representantes.
- Conocer **requisitos legales** (p. ej., seguridad laboral; también accesibilidad por **RD 1112/2018**, ver [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Legislación de accesibilidad en España\|Legislación de accesibilidad en España]]).

### 3. Producir soluciones de diseño (p. 18)

- Diseñar **tareas, interacción e interfaz** para cumplir los requisitos, teniendo en cuenta la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Experiencia de Usuario\|Experiencia de Usuario]] completa.
- Aplicar **principios de diseño, estándares y/o guías de estilo**.
- Hacer las soluciones concretas: **escenarios, simulaciones, modelos y maquetas**.
- Modificar las soluciones en base a la evaluación centrada en el usuario y feedback.
- Comunicar la solución a los responsables de implementación.

### 4. Evaluar el diseño (p. 19)

- Conducir una **evaluación centrada en el usuario** para obtener feedback **temprano**.
- Aplicar métodos: **test con usuarios** y **evaluación por inspección** (expertos usando checklists, heurísticas o estándares).
- Test con usuarios **en cualquier estado del diseño**: temprano, medio, final.
- **Monitorizar a largo plazo** para identificar fallos tras el despliegue.

### La iteración

Las 4 actividades **se iteran**: tras evaluar, se vuelve a entender el contexto o a especificar requisitos y se produce una nueva solución. Esto es lo que distingue DCU de un waterfall con una fase de "testing" al final.

## Cómo podrías haberlo descubierto
Son las preguntas naturales de cualquier diseño honesto: *¿quién, dónde, para qué?* (contexto), *¿qué tiene que hacer?* (requisitos), *¿cómo lo hace?* (solución), *¿funciona?* (evaluación). La ISO solo las formaliza.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]]: es su versión formal operativa.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]]: su objetivo principal.

## Permite entender
- Por qué el modelo **[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]]** se estructura exactamente en esas fases (análisis, diseño, prototipado, evaluación): es la cristalización de las 4 actividades ISO.
- Por qué la ISO insiste en "a lo largo de todo el ciclo de vida" (p. 7): las actividades no son secuenciales de una sola pasada; son iterativas.

## Ejemplo
> [!example]
> **Diseño de una app para dar cita en un ambulatorio**:
> 1. **Contexto**: usuarios mayores con lentitud en el móvil, uso en sala de espera con wifi flaky.
> 2. **Requisitos**: pedir cita en <3 pasos, texto grande, sin obligar a crear cuenta.
> 3. **Solución**: boceto → wireframe → prototipo clicable.
> 4. **Evaluar**: thinking aloud con 5 usuarios reales → detectas que el calendario les cuesta → vuelves a 3.
> La iteración 3 → 4 → 3 se repite varias veces hasta que la tasa de éxito es la esperada.

## Errores comunes
> [!warning]
> - **Hacer las 4 actividades una vez**: pierdes el valor del DCU. La fuerza está en la iteración.
> - **Confundir "evaluar" con "testing final"**: la actividad 4 se hace también sobre prototipos tempranos (incluso de papel).
> - **Saltar la actividad 1**: imaginar el contexto de uso en vez de observarlo es la causa más frecuente de rediseños caros.

## Autoevaluación
> [!question]- ¿Qué norma ISO fija las 4 actividades del DCU y qué parte es?
> La **ISO 9241-210:2019**, parte 210: *Human-centred design for interactive systems*.

> [!question]- ¿Cuáles son las 4 actividades?
> **1)** Entender el contexto de uso, **2)** Especificar los requisitos del usuario, **3)** Producir soluciones de diseño, **4)** Evaluar el diseño.

> [!question]- ¿Son secuenciales?
> **No**: son **iterativas**. La actividad 4 realimenta a 1, 2 o 3 según lo que descubra.

## Contraste
> [!success] Verificado
> [Wikipedia: ISO 9241](https://en.wikipedia.org/wiki/ISO_9241) confirma que la parte **210** cubre el *human-centered design*. [Wikipedia: Human-centered design](https://en.wikipedia.org/wiki/Human-centered_design) describe estas mismas actividades como "approach to interactive systems development that aims to make systems usable and useful by focusing on the users, their needs and requirements". El contenido coincide con el estándar oficial [iso.org/standard/77520.html](https://www.iso.org/standard/77520.html).

## Fuentes
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27\|Fuente - Tema 1.3-DCU-MPIUa-26-27]], p. 7, 15–19.
- Externas: [iso.org/standard/77520.html](https://www.iso.org/standard/77520.html), [en.wikipedia.org/wiki/ISO_9241](https://en.wikipedia.org/wiki/ISO_9241), [en.wikipedia.org/wiki/Human-centered_design](https://en.wikipedia.org/wiki/Human-centered_design).

## Mis notas
