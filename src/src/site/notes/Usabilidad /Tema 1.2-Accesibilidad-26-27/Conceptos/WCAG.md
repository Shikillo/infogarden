---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-2-accesibilidad-26-27/conceptos/wcag/","tags":["materia/Usabilidad","tema/1.2"],"dg-note-properties":{"tipo":"concepto","aliases":["Web Content Accessibility Guidelines","Directrices de Accesibilidad para el Contenido Web","WCAG 1.0","WCAG 2.0","WCAG 2.1","WCAG 2.2"],"tags":["materia/Usabilidad","tema/1.2"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# WCAG

> [!abstract] En una frase
> Las **WCAG (Web Content Accessibility Guidelines)** son las **directrices de accesibilidad web** publicadas por la [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WAI\|WAI]] del [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]]; especifican **cómo hacer el contenido web accesible** mediante pautas y criterios verificables, con tres [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Niveles de conformidad WCAG\|niveles de conformidad (A, AA, AAA)]].

## ¿Qué problema resuelve?
"Accesible" es un objetivo vago: una web puede ser más o menos accesible, y hace falta una forma **objetiva, verificable y comparable** de decidir si lo es. Las WCAG convierten la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]] en una lista concreta de criterios con herramientas de evaluación asociadas, con la cual gobiernos, auditores y desarrolladores pueden referirse a lo mismo.

## Qué es
Son un **conjunto de recomendaciones** del [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]], producidas por la [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WAI\|WAI]] (concretamente el AG WG). Han pasado por cuatro versiones principales:

### Evolución (p. 55–81)

| Versión | Fecha | Estructura | Criterios totales | Observación |
|---------|-------|------------|-------------------|-------------|
| **1.0** | 5-may-1999 | **14 pautas**, 3 prioridades | 65 puntos de verificación | Modelo de **prioridades** (P1, P2, P3). |
| **2.0** | 11-dic-2008 | 4 [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Principios POUR\|Principios POUR]], **12 pautas** | 61 criterios | ISO/IEC 40500:2012. Modelo nuevo: principios → pautas → criterios. |
| **2.1** | 5-jun-2018 (actualizada 2025) | 4 principios, **13 pautas** (nueva 2.5) | **78 criterios** (+17) | Añade móvil, baja visión, cognitivas. Backwards compatible con 2.0. |
| **2.2** | 5-oct-2023 | 4 principios, 13 pautas | **86 criterios** (+9) | **Elimina 4.1.1 Parsing**. |

### Estructura de WCAG 2.x

- **4 principios** ([[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Principios POUR\|POUR]]): Perceptible, Operable, Comprensible, Robusto.
- **Pautas**: una docena de reglas generales (p. ej. "1.1 Alternativas textuales").
- **Criterios de conformidad**: enunciados verificables, cada uno con un **nivel** (A, AA o AAA) y **técnicas** "cómo cumplir" + "comprender".

### WCAG 1.0 — modelo de prioridades (p. 55–59)

- **Prioridad 1** ("tiene que"): si no se cumple, uno o más grupos **no pueden** acceder.
- **Prioridad 2** ("debe"): si no se cumple, uno o más grupos encontrarán **dificultades importantes**.
- **Prioridad 3** ("puede"): si no se cumple, uno o más grupos encontrarán **alguna dificultad**.
- **Niveles de conformidad**: **A** cumple P1; **AA** cumple P1+P2; **AAA** cumple P1+P2+P3.

### WCAG 1.0 — las 14 pautas (p. 67)

1. Alternativas equivalentes para contenido visual y auditivo.
2. No confiar solo en el color.
3. Marcadores y hojas de estilo (cabeceras `<Hx>`, CSS).
4. Aclarar el lenguaje natural usado.
5. Tablas que se transformen airosamente.
6. Páginas con nuevas tecnologías que se transfiguren airosamente.
7. Control del usuario sobre contenido temporal.
8. Accesibilidad de interfaces embebidas.
9. Independencia del dispositivo.
10. Soluciones provisionales.
11. Tecnologías y directrices del W3C.
12. Información de contexto y orientación.
13. Mecanismos de navegación claros.
14. Documentos claros y sencillos.

### WCAG 2.x — las 12/13 pautas (p. 73)

- **Perceptible**: 1.1 alternativas textuales, 1.2 multimedia dependiente del tiempo, 1.3 adaptabilidad, 1.4 distinguible.
- **Operable**: 2.1 teclado, 2.2 tiempo suficiente, 2.3 convulsiones, 2.4 navegable, (2.5 modalidades de entrada en 2.1+).
- **Comprensible**: 3.1 legible, 3.2 predecible, 3.3 ayuda a la entrada de datos.
- **Robusto**: 4.1 compatible con agentes y tecnologías asistivas.

### Compatibilidad hacia atrás (p. 76)

> Si una página cumple WCAG 2.1 también cumple WCAG 2.0. "Para decirlo de otra manera: si deseas cumplir con las WCAG 2.0 y 2.1, puedes usar los recursos 2.1 y no necesitas molestarte en mirar 2.0."

El mismo principio aplica a 2.2 respecto a 2.1 (con una excepción: 4.1.1 Parsing se elimina en 2.2).

## Cómo podrías haberlo descubierto
Si los gobiernos empiezan a exigir accesibilidad en sus webs (p. 11–16), hace falta una referencia común que diga **qué significa accesible**. La WAI, al ser el órgano técnico de la Web, es la fuente natural; ya en 1999 publica la versión 1.0.

## Depende de
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WAI\|WAI]]: su autor.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]]: el consorcio bajo el que opera la WAI.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Discapacidad\|Discapacidad]]: cubrir todos los tipos exige los criterios actuales.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Principios POUR\|Principios POUR]]: la columna vertebral de WCAG 2.x.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Niveles de conformidad WCAG\|Niveles de conformidad WCAG]]: la métrica de cumplimiento.

## Permite entender
- Por qué la legislación española (RD 1494/2007, RD 1112/2018) habla de **UNE 139803** y **EN 301 549**: estas normas **incorporan por referencia** las WCAG, para que al legislar no haya que reescribir las directrices.
- Por qué una web puede ser "AA" sin ser "AAA": los niveles son incrementales, y AAA es el ideal poco realista aplicado a cualquier contenido.
- Por qué 4.1.1 Parsing se elimina en 2.2: los parsers de HTML modernos ya son robustos a errores de marcado; el criterio quedó obsoleto.
- Por qué las versiones son **"outdated"** en el material (2.1 obsolete 06-05-25, 2.2 obsolete 12-12-24): el W3C mantiene un *living standard* con WCAG 2.2 vigente y WCAG 3.0 en desarrollo.

## Ejemplo
> [!example]
> **Un vídeo sin subtítulos** incumple la pauta **1.2 Multimedia dependiente del tiempo**, concretamente el criterio **1.2.2 Subtítulos (pregrabados)**, de nivel A. Una web con un solo vídeo sin subtítulos **no puede declarar conformidad ni A**.

## Errores comunes
> [!warning]
> - **Confundir pauta y criterio**: la pauta es una regla general ("1.1 Alternativas textuales"); el criterio es un enunciado verificable con nivel ("1.1.1 Contenido no textual — Nivel A").
> - **Pensar que WCAG 2.x son solo 12 reglas**: son 4 principios → 12/13 pautas → 61/78/86 criterios según la versión.
> - **Confundir conformidad con calidad**: una web puede cumplir WCAG AA y aun así tener problemas de [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]]. Son dimensiones distintas.

## Autoevaluación
> [!question]- ¿Qué significan las siglas POUR y a qué versión de WCAG pertenecen?
> **Perceptible, Operable, Understandable (Comprensible), Robust (Robusto)**. Son los 4 principios de **WCAG 2.0 en adelante**.

> [!question]- ¿Qué cambio estructural fundamental hubo de WCAG 1.0 a WCAG 2.0?
> WCAG 1.0 organizaba 14 pautas en **3 prioridades**. WCAG 2.0 introdujo los **4 principios POUR** y sustituyó "prioridades" por **"niveles de conformidad"** (A, AA, AAA) asignados a criterios verificables.

> [!question]- Si cumples WCAG 2.1, ¿cumples también 2.0?
> **Sí**: WCAG 2.1 es *backwards compatible* con 2.0. Lo mismo con 2.2 respecto a 2.1 (salvo la eliminación de 4.1.1 Parsing).

## Contraste
> [!success] Verificado
> [Wikipedia: WCAG](https://es.wikipedia.org/wiki/Web_Content_Accessibility_Guidelines) confirma que las WCAG son de la [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WAI\|WAI]] del [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/W3C\|W3C]], que **WCAG 2.0** es la **norma ISO/IEC 40500:2012** desde octubre de 2012, y que **WCAG 2.2 es Recomendación W3C desde el 5 de octubre de 2023**. Las fechas, estructuras y número de criterios coinciden con el material.

> [!info] Ampliación — ISO/IEC 40500:2012 (no está en el material)
> Un dato útil que el material no cita: **WCAG 2.0 también es norma ISO** (ISO/IEC 40500:2012). Esto es importante porque los gobiernos pueden referenciar la norma ISO en lugar de la recomendación W3C, con el mismo contenido.

## Fuentes
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27\|Fuente - Tema 1.2-Accesibilidad-26-27]], p. 55–81.
- Externas: [w3.org/WAI/standards-guidelines/wcag](https://www.w3.org/WAI/standards-guidelines/wcag/), [w3.org/TR/WCAG22/](https://www.w3.org/TR/WCAG22/), [es.wikipedia.org/wiki/Web_Content_Accessibility_Guidelines](https://es.wikipedia.org/wiki/Web_Content_Accessibility_Guidelines).

## Mis notas
