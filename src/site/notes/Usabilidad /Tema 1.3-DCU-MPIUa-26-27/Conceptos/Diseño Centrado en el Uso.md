---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-3-dcu-mpi-ua-26-27/conceptos/diseno-centrado-en-el-uso/","tags":["materia/Usabilidad","tema/1.3"],"dg-note-properties":{"tipo":"concepto","aliases":["Diseño centrado en el uso vs usuario","Use-centered design","DCU vs DCUso"],"tags":["materia/Usabilidad","tema/1.3"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Diseño Centrado en el Uso

> [!abstract] En una frase
> El **Diseño Centrado en el Uso** se enfoca en **cómo** se usa el sistema (modelado sistemático de las tareas, basado en Ingeniería del Software), frente al [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|Diseño Centrado en el Usuario]], que se enfoca en el usuario (su experiencia, su satisfacción, su opinión) (p. 20).

## ¿Qué problema resuelve?
Son dos enfoques que a veces se confunden. El material los pone en paralelo para que el estudiante entienda que **MPIU+a** combina ambos: el rigor de modelar el uso + la implicación activa del usuario.

## Qué es
Es una **distinción conceptual** que aparece una vez en el tema (p. 20) para precisar el DCU. Dos columnas comparadas:

| | **Diseño Centrado en el Uso** | **Diseño Centrado en el Usuario (DCU)** |
|-|-------------------------------|------------------------------------------|
| **Enfoque** | En el **uso** que el usuario hace/hará de la aplicación. | En **los usuarios**: experiencia y grado de satisfacción. |
| **Base** | **Concreción de modelos** (de tareas, de interacción). | **Opinión del usuario**. |
| **Implicación del usuario** | **Selectiva**: modelado explorativo, validación de modelos, revisión de usabilidad. | **Substancial**: estudios de usuarios, diseño participativo, respuesta del usuario, pruebas con usuarios. |
| **Base metodológica** | **Diseño basado en la modelización**. | Se diseñan **iterativamente** distintos prototipos. |
| **Rigor del proceso** | **Sistemático**, procesos bien definidos. | Procesos **muy variables e informales**. |
| **Disciplina de referencia** | **Ingeniería del Software**. | **Ingeniería de la Usabilidad**. |

### Por qué conviene distinguirlo

- **Diseño Centrado en el Uso** aporta rigor y modelos (análisis de tareas, casos de uso UML, modelos de diálogo), pero puede caer en la trampa de modelar bien un uso **que el usuario no reconoce**.
- **Diseño Centrado en el Usuario** aporta implicación real y satisfacción, pero sin estructura puede ser caótico y no escalable.

El [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]] los integra: toma la **estructura** del Diseño Centrado en el Uso (fases, entregables, modelos) y la **implicación substancial del usuario** del DCU (prototipos iterativos, test con usuarios).

## Cómo podrías haberlo descubierto
Hay dos preguntas distintas que uno puede responder: *¿cómo se usa este sistema?* (modelado del uso) y *¿qué le pasa al usuario cuando lo usa?* (experiencia). Cada una centra una disciplina distinta. Un buen método combina las dos.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]]: uno de los dos enfoques comparados.
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]]: su síntesis.
- Ingeniería del Software: base del Diseño Centrado en el Uso.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Ingeniería de Usabilidad\|Ingeniería de Usabilidad]]: base del DCU.

## Permite entender
- Por qué los **análisis de tareas** (técnica central del Diseño Centrado en el Uso) aparecen en MPIU+a: proporcionan el rigor del modelado.
- Por qué los **prototipos iterativos con usuarios** (central del DCU) también aparecen: aportan la implicación substancial.
- Por qué un equipo solo de ingenieros de software tiende al Diseño Centrado en el Uso (sistemático, modelador) y un equipo solo de UX tiende al DCU (iterativo, informal): el principio 4 (equipos multidisciplinares) rompe esa polarización.

## Ejemplo
> [!example]
> **Formulario de declaración de la renta online**:
> - **Diseño Centrado en el Uso** modelaría el flujo con casos de uso UML, matrices de tareas, modelos de diálogo. Resultado: un sistema correcto formalmente, pero potencialmente frustrante.
> - **Diseño Centrado en el Usuario** haría entrevistas, prototipos iterativos, test con 10 contribuyentes reales. Resultado: amable, pero quizá sin cubrir casos raros.
> - **MPIU+a** haría ambos: modelos UML para formalizar + iteraciones con usuarios reales. Mejor cobertura y mejor experiencia.

## Errores comunes
> [!warning]
> - **Equipararlos**: no son sinónimos.
> - **Elegir uno "porque es más moderno"**: el DCU es más conocido hoy, pero el Diseño Centrado en el Uso aporta estructura que el DCU puro suele descuidar.
> - **Pensar que son incompatibles**: MPIU+a demuestra que no.

## Autoevaluación
> [!question]- ¿Qué distingue el **enfoque** de los dos?
> El Diseño Centrado en el **Uso** se enfoca en **cómo se usa** el sistema (modelos). El Diseño Centrado en el **Usuario** se enfoca en **el usuario** (experiencia, satisfacción).

> [!question]- ¿Qué disciplina de referencia tiene cada uno?
> El Diseño Centrado en el **Uso** → **Ingeniería del Software**. El DCU → **[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Ingeniería de Usabilidad\|Ingeniería de Usabilidad]]**.

> [!question]- ¿Cómo los integra MPIU+a?
> Toma la **estructura y los modelos** del Diseño Centrado en el Uso + la **implicación substancial del usuario** del DCU, en un modelo iterativo con fases bien definidas.

## Contraste
> [!success] Verificado
> Esta distinción aparece en la literatura española de IPO (Lorés, AIPO 2002) y se recoge por extensión del concepto *use-centered design* (Flach & Dominguez 1995, para HCI de sistemas complejos). No hay una entrada en Wikipedia específica para "Diseño Centrado en el Uso", pero el contenido del material es coherente con las fuentes citadas (p. 83).

## Fuentes
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27\|Fuente - Tema 1.3-DCU-MPIUa-26-27]], p. 20, 24, 83.
- Externas: Lorés (ed.), *Introducción a la Interacción Persona-Ordenador*, AIPO 2002.

## Mis notas
