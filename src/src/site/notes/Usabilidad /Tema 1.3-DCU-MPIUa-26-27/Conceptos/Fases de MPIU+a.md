---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-3-dcu-mpi-ua-26-27/conceptos/fases-de-mpiu-a/","tags":["materia/Usabilidad","tema/1.3"],"dg-note-properties":{"tipo":"concepto","aliases":["Fases MPIUa","Fases MPIu+a","Ciclo de vida MPIU+a"],"tags":["materia/Usabilidad","tema/1.3"],"nivel":3,"fuentes":["[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Fases de MPIU+a

> [!abstract] En una frase
> El **[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]]** se desarrolla en **6 fases** iterativas: **Análisis → Diseño → Prototipado → Evaluación → Implementación → Lanzamiento**, cada una con entregables definidos y con la **[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]] como componente transversal** (p. 40).

## ¿Qué problema resuelve?
El modelo general del [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]] habla de 4 actividades conceptuales (contexto, requisitos, soluciones, evaluación), pero un equipo real necesita saber **qué entregables producir, qué técnicas usar y en qué momento** del ciclo de vida. Las 6 fases dan esa cadena concreta, alineada con Ingeniería del Software.

## Qué es
### 1. Análisis (p. 41–52)

Dos subfases:

**1ª — Especificación del producto y planificación preliminar.**
- Entregables: necesidades del cliente, características del producto, estimación de recursos.
- Resultados: **especificación del sistema firmada**, planificación/presupuesto preliminares revisados.

**2ª — Planificación detallada y especificación de la ingeniería.**
- Entregables: prototipo (opcional), **SRS** (Software Requirements Specification), **SDP** (Software Development Plan), planificación y costes, plan de documentación, plan de test.
- Resultados: SRS firmado, SDP firmado.

**Técnicas específicas de usabilidad en Análisis** (p. 44–52):

- Objetivos de la Aplicación.
- **Análisis Etnográfico**.
- **Análisis de los implicados** → ver [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Stakeholders\|Stakeholders]].
- **Perfil del Usuario** (diferencias individuales, internacionales, HW/SW; p. 47).
- Actores, Roles y Organización.
- Listas de Tareas, Objetos, Plataforma, Perfil del Entorno.
- **Objetivos de usabilidad y accesibilidad**.
- Para **WEB**: audiencia, escenarios, redes sociales, análisis de la competencia, medida del éxito, Arquitectura de la Información.

### 2. Diseño (p. 53–60)

Tres bloques (FUNCIONAL, INTERFAZ, BASES DE DATOS).

- Entregables: **Documento de diseño del software**.
- Resultados: aprobación del jefe de proyecto.

**Técnicas de diseño** (p. 54):
- Análisis de Tareas.
- Modelo Conceptual.
- Definir Estilo (Estándares Generales, Metáforas, Colores, Estándares Particulares).
- Diseño Detallado.

**Para WEB** (p. 55): Arquitectura de la Información, organización de páginas, orientación, navegación, home, formularios, multimedia. Técnica clave: **[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Card Sorting\|Card Sorting]]** (p. 60).

### 3. Prototipado (p. 61–68)

Ver [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Prototipado\|Prototipado]].

### 4. Evaluación (p. 69–75)

Ver [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Evaluación de usabilidad\|Evaluación de usabilidad]].

### 5. Implementación (p. 76–78)

- Codificación, test unitarios, integración, test de integración.
- Entregables: producto SW, tests unitarios y resultados, test integración y resultados, casos de test a nivel de sistema.
- Para **WEB**: redacción adaptada a la audiencia; HTML/CSS/PHP; consistencia de colores de vínculos.

### 6. Lanzamiento (p. 79–82)

Dos actividades:

**Test de Sistema** (p. 79–80).
- Objetivo: batería completa que compruebe que el SW cumple requerimientos funcionales y de prestaciones.
- Entregables: resultados, informe, documento de diseño actualizado.
- Resultado: la fase se cumple cuando el producto pasa todos los test de sistema.

**Despliegue** (p. 81).
- Objetivo: comprobar que el producto final refleja perfectamente el producto base.
- Entregable: producto preparado para entregar al cliente.

**Para WEB** (p. 82):
- **Pre-lanzamiento**: registro del dominio, test de tareas, código, carga, sistema.
- **Lanzamiento**: promoción del sitio, control de visitas, alta en buscadores, enlaces en sitios afines.
- **Post-lanzamiento**: **NO es mantenimiento**; es **analizar el uso real** de la web (dato explícito del material).

## Cómo podrías haberlo descubierto
Hay que casar el ciclo clásico de Ingeniería del Software (análisis, diseño, codificación, pruebas, despliegue) con las 4 actividades DCU. Donde el DCU dice "soluciones" aparecen el Diseño + Prototipado; donde dice "evaluar" aparece la Evaluación (que en MPIU+a se repite tras cada iteración de prototipado).

## Depende de
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]]: el modelo que las define.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]] y [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Actividades DCU (ISO 9241-210)\|Actividades DCU (ISO 9241-210)]]: su base teórica.

## Permite entender
- Por qué cada fase tiene **técnicas específicas**: el nivel de madurez del artefacto cambia (en Análisis se hace etnografía; en Diseño, modelo conceptual; en Prototipado, maquetas; en Evaluación, thinking aloud).
- Por qué **post-lanzamiento ≠ mantenimiento**: el DCU exige observar el uso real para alimentar la siguiente iteración.

## Ejemplo
> [!example]
> **Portal municipal de empleo**:
> - **Análisis**: entrevistar a usuarios desempleados reales y a técnicos del SEPE; perfilar audiencia; identificar stakeholders.
> - **Diseño**: card sorting para la arquitectura de la información (ofertas, ayudas, formación).
> - **Prototipado**: wireframes + prototipo clicable en Figma.
> - **Evaluación**: thinking aloud con 5 usuarios + inspección heurística por 3 expertos.
> - **Implementación**: HTML semántico cumpliendo WCAG 2.1 AA desde el día 1.
> - **Lanzamiento**: test de carga + promoción + analytics para medir uso real.

## Errores comunes
> [!warning]
> - **Confundir fases con "waterfall"**: las fases **se iteran**; cada evaluación realimenta al diseño o al prototipado.
> - **Tratar la evaluación solo al final**: en MPIU+a la evaluación se superpone con el prototipado (iteraciones cortas).
> - **Olvidar la accesibilidad en las primeras fases**: el "+a" exige que esté desde el Análisis.

## Autoevaluación
> [!question]- Enumera las 6 fases en orden.
> **Análisis, Diseño, Prototipado, Evaluación, Implementación, Lanzamiento** (p. 40).

> [!question]- ¿Qué diferencia hay entre "post-lanzamiento" y "mantenimiento"?
> Post-lanzamiento es **analizar el uso real** del sistema. Mantenimiento es corregir fallos y actualizar. En MPIU+a son conceptualmente distintos (p. 82).

> [!question]- ¿Qué entregables firma el responsable al final de la 2ª subfase de Análisis?
> **SRS** (Software Requirements Specification) y **SDP** (Software Development Plan).

## Contraste
> [!success] Verificado
> La estructura en fases con sus entregables (SRS, SDP) corresponde a la ingeniería del software clásica (Pressman, Sommerville) y a la literatura del grupo GRIHO. Las técnicas de usabilidad por fase son estándar en la IPO (AIPO, Lorés 2002). No hay discrepancias detectadas.

## Fuentes
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27\|Fuente - Tema 1.3-DCU-MPIUa-26-27]], p. 40–82.
- Externas: [curso-ipo.com/fases-mpiua](https://curso-ipo.com/fases-mpiua/).

## Mis notas
