---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-2-accesibilidad-26-27/conceptos/niveles-de-conformidad-wcag/","tags":["materia/Usabilidad","tema/1.2"],"dg-note-properties":{"tipo":"concepto","aliases":["Nivel A","Nivel AA","Nivel AAA","Niveles A AA AAA","Conformance levels"],"tags":["materia/Usabilidad","tema/1.2"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Niveles de conformidad WCAG

> [!abstract] En una frase
> Las **[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]]** definen **tres niveles de conformidad acumulativos** — **A**, **AA**, **AAA** — para que una web pueda declarar objetivamente su grado de accesibilidad (p. 55, 59).

## ¿Qué problema resuelve?
Si todos los criterios fuesen "obligatorios" por igual, cumplir las WCAG sería inviable para la mayoría de las webs. Si fuesen "voluntarios", no habría forma de exigirlos. Los tres niveles sirven de **escalera**: un mínimo imprescindible, un nivel de buenas prácticas y un ideal máximo. Gobiernos y clientes pueden exigir el nivel apropiado a cada caso.

## Qué es
### WCAG 1.0 (p. 55–59)

En WCAG 1.0 cada **punto de verificación** tiene asignada una de las **3 prioridades**:

- **Prioridad 1** ("**tiene que**"): si no se cumple, **uno o más grupos no pueden acceder** al documento. Es un requerimiento básico.
- **Prioridad 2** ("**debe**"): si no se cumple, uno o más grupos **tendrán dificultades importantes** para acceder.
- **Prioridad 3** ("**puede**"): si no se cumple, uno o más grupos tendrán **alguna dificultad** para acceder.

A partir de estas prioridades, los niveles de conformidad son **acumulativos**:

- **A**: satisface todos los puntos de **prioridad 1**.
- **AA** ("Doble A"): satisface los de **prioridad 1 + 2**.
- **AAA** ("Triple A"): satisface los de **prioridad 1 + 2 + 3**.

### WCAG 2.x (p. 68, 80)

En WCAG 2.0, 2.1 y 2.2 el modelo de "prioridades" desaparece y se asignan directamente **niveles** a cada criterio:

- Cada criterio es **A**, **AA** o **AAA**.
- Para declarar conformidad **AA**, se cumplen *todos* los criterios A **y** AA (no solo los AA).
- Para declarar **AAA**, se cumplen *todos* los A, AA y AAA.

**Totales por versión** (p. 68, 75, 80):

| Versión | Criterios A | Criterios AA | Criterios AAA | Total |
|---------|------------|--------------|---------------|-------|
| 2.0 | — | — | — | 61 |
| 2.1 | +5 | +7 | +5 | 78 (+17) |
| 2.2 | +2 | +4 | +3 | 86 (+9) |
| 2.2 (desglose) | 31 | 24 | 31 | 86 |

### En la práctica

- **A** = mínimo legal en muchos países.
- **AA** = objetivo habitual de administraciones públicas y buenas prácticas corporativas. Es el nivel que exige el RD 1112/2018 en España.
- **AAA** = no es exigido *para toda la página*; el propio W3C recomienda no requerir AAA como política general porque algunos criterios AAA son imposibles de cumplir en ciertos contenidos.

## Cómo podrías haberlo descubierto
Si quieres convertir "ser accesible" en algo verificable, necesitas umbrales objetivos. Tres niveles con dificultad creciente dan un vocabulario común (A, AA, AAA) que legisladores, auditores y desarrolladores pueden referenciar sin ambigüedad.

## Depende de
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]]: estos niveles son su mecanismo de cumplimiento.

## Permite entender
- Por qué cuando una administración exige "conformidad AA" **no está pidiendo todos los criterios**, sino los de nivel A y AA (los AAA son extra).
- Por qué una web puede ser **AA en el 95 %** y aun así no poder declararse AA: los niveles son **binarios**; falla un criterio y cae el nivel.
- Por qué los reports de las [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Herramientas de evaluación de accesibilidad\|Herramientas de evaluación de accesibilidad]] desglosan los problemas por **nivel A/AA/AAA**: permite priorizar correcciones.
- La correspondencia entre el modelo WCAG 1.0 (prioridades) y WCAG 2.x (niveles): el A de 2.x ≈ Prioridad 1 de 1.0, etc.

## Ejemplo
> [!example]
> **Una web de la Administración General del Estado** debe cumplir **nivel AA** de WCAG 2.1 (según el RD 1112/2018 y la norma EN 301 549 referenciada). Si tiene 1 criterio AA sin cumplir, legalmente **no puede declarar conformidad AA**, aunque cumpla los otros 23 criterios AA y los 31 A.

## Errores comunes
> [!warning]
> - **Confundir prioridad (WCAG 1.0) con nivel (WCAG 2.x)**: son equivalentes en espíritu pero no en letra; en 2.x es más limpio.
> - **Pensar que AAA es siempre deseable**: el propio W3C desaconseja exigir AAA como política general porque algunos criterios AAA son incompatibles con cierto contenido.
> - **Confundir "nivel AA" con "80 % de criterios AA cumplidos"**: la conformidad es binaria (sí/no) para el nivel declarado.

## Autoevaluación
> [!question]- ¿Qué diferencia hay entre "AA" y "AAA"?
> AA cumple criterios A **y** AA; AAA cumple A, AA **y** AAA. Son **acumulativos**: para subir de nivel hay que cumplir el anterior.

> [!question]- ¿Cuántos criterios de nivel AA hay en WCAG 2.2?
> **24** criterios de nivel AA (p. 80).

> [!question]- ¿Por qué el W3C no recomienda exigir AAA para toda una web?
> Porque algunos criterios AAA no son aplicables a cualquier contenido (ej. descripciones en lengua de signos para cada vídeo, nivel de lenguaje máximo que puede impedir ciertos textos).

## Contraste
> [!success] Verificado
> El sistema de tres niveles acumulativos y las fechas de versiones coinciden con [w3.org/TR/WCAG22/#conformance](https://www.w3.org/TR/WCAG22/) y con [Wikipedia: WCAG](https://es.wikipedia.org/wiki/Web_Content_Accessibility_Guidelines).

## Fuentes
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27\|Fuente - Tema 1.2-Accesibilidad-26-27]], p. 55–59, 68, 75, 80.
- Externas: [w3.org/TR/WCAG22/#conformance](https://www.w3.org/TR/WCAG22/).

## Mis notas
