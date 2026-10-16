---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-2-accesibilidad-26-27/conceptos/herramientas-de-evaluacion-de-accesibilidad/","tags":["materia/Usabilidad","tema/1.2"],"dg-note-properties":{"tipo":"concepto","aliases":["TAW","WAVE","Siteimprove","Color Contrast Analyzer","W3C Markup Validator"],"tags":["materia/Usabilidad","tema/1.2"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Herramientas de evaluación de accesibilidad

> [!abstract] En una frase
> Las **herramientas de evaluación de accesibilidad** son software (plugins, aplicaciones, servicios online) que automatizan parte de la comprobación de las [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]], reduciendo tiempo y esfuerzo (p. 82).

## ¿Qué problema resuelve?
Verificar manualmente 86 criterios de [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]] 2.2 en cada página de un sitio es inviable. Las herramientas detectan automáticamente **lo que es posible comprobar por reglas** (contraste de color, atributos `alt`, estructura HTML, títulos de página) y señalan **lo que requiere revisión manual** (claridad de un texto alternativo, orden de tabulación, mensajes de error significativos). Reducen el trabajo manual al núcleo no automatizable.

## Qué es
Son programas que, dada una URL o un fragmento de HTML/CSS/JS, devuelven un informe clasificado por **criterio y nivel** ([[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Niveles de conformidad WCAG\|A/AA/AAA]]) con:

- **Problemas**: fallos que requieren corrección segura.
- **Advertencias**: posibles problemas que requieren revisión manual.
- **No verificados**: criterios que solo se pueden comprobar manualmente.

### Tipos (p. 83)

- **Plugin / extensión** de navegador (WAVE, axe DevTools, Siteimprove, WebDeveloper Toolbar).
- **Línea de comandos** (axe-cli, Pa11y).
- **Aplicación de escritorio** (Color Contrast Analyzer de TPGi).
- **Servicio online** (TAW, validator.w3.org).

### Herramientas citadas en el material

| Herramienta | Tipo | URL | Observación |
|-------------|------|-----|-------------|
| **TAW** | Online + descarga | tawdis.net | Informe por **principios POUR**; tres vistas (marcada, detalle, listado). Base: WCAG 2.0 (p. 84). |
| **WAVE** | Plugin + online | wave.webaim.org | De WebAIM; muy visual (iconos sobre la página). |
| **Siteimprove Accessibility Checker v2.0** | Chrome extension | Chrome Web Store | Fecha material: sep-25 (p. 87). |
| **WebDeveloper Toolbar** | Chrome extension | Chrome Web Store | Herramientas generales de desarrollo + accesibilidad (p. 88). |
| **Color Contrast Analyzer** | Desktop / online | vispero.com | Verifica contraste color texto/fondo según WCAG (p. 89). |
| **Adobe Color** | Online | color.adobe.com | Generador y verificador de paletas. |
| **palett.es** | Online | palett.es | Generador de paletas accesibles. |
| **W3C Markup Validator** | Online | validator.w3.org | No es solo accesibilidad: valida que el HTML sea correcto; condición previa para la pauta "Robusto" (p. 90). |

### Recomendaciones manuales que complementan a las automáticas (p. 91)

Ninguna herramienta sustituye estas verificaciones:

- **Usar solo el teclado** para navegar por la interfaz.
- Comprobar que la **ampliación de pantalla** del sistema operativo funciona con la aplicación.
- Cambiar los **tipos de letra estándar** y comprobar que el diseño sigue correcto.

### Lista oficial

La WAI mantiene una lista actualizada: [w3.org/WAI/test-evaluate/tools/list](https://www.w3.org/WAI/test-evaluate/tools/list/).

## Cómo podrías haberlo descubierto
Si tienes una norma con 86 criterios y una web con cientos de páginas, la única salida escalable es la automatización parcial. Las heurísticas automáticas cubren lo mecánico (contraste, atributos faltantes); el resto requiere personas.

## Depende de
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]]: definen qué comprobar.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Niveles de conformidad WCAG\|Niveles de conformidad WCAG]]: el informe se clasifica por nivel.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Principios POUR\|Principios POUR]]: muchas herramientas agrupan resultados por principio.

## Permite entender
- Por qué **ninguna herramienta puede garantizar que una web es accesible al 100 %**: cubren alrededor del 30–40 % de los criterios automáticamente; el resto requiere revisión manual.
- Por qué los informes de herramientas distinguen **"errors" / "warnings" / "manual checks"**: no cada señal es un fallo seguro.
- Por qué validar HTML (validator.w3.org, p. 90) también cuenta para la accesibilidad: era parte del principio **Robusto** vía 4.1.1 Parsing (eliminado en WCAG 2.2 pero sigue siendo buena práctica).

## Ejemplo
> [!example]
> **Auditoría WAVE sobre una página**: devuelve "3 errores" (ej., 2 imágenes sin `alt`, 1 contraste 2.9:1 < 4.5:1 requerido), "5 advertencias" (ej., enlaces vacíos revisables), "6 características de accesibilidad" detectadas (lenguaje definido, estructura semántica). Con esos datos, el desarrollador prioriza arreglar los 3 errores y verificar manualmente las 5 advertencias.

## Errores comunes
> [!warning]
> - **Pensar que "pasó la herramienta → es accesible"**: el **~60 % de los criterios WCAG no son auto-verificables**. Hace falta revisión humana + pruebas con usuarios reales.
> - **No validar el HTML**: un HTML con errores sintácticos puede comportarse de forma impredecible en lectores de pantalla.
> - **Usar una sola herramienta**: distintas herramientas tienen heurísticas distintas; combinar WAVE + axe + Siteimprove cubre más terreno.

## Autoevaluación
> [!question]- ¿Qué tres tipos de resultados devuelve una herramienta típica?
> **Problemas** (fallos seguros, requieren corrección), **advertencias** (requieren revisión manual) y **no verificados** (requieren análisis manual completo) — p. 84.

> [!question]- ¿Qué revisiones manuales recomienda el material como complemento?
> **Usar solo el teclado**, comprobar la **ampliación de pantalla** y **cambiar tipos de letra** (p. 91).

> [!question]- ¿Es WAVE una herramienta de línea de comandos?
> **No**: es una **extensión de navegador** y un servicio online (webaim.org).

## Contraste
> [!success] Verificado
> Todas las herramientas y organizaciones mencionadas existen y son referencias habituales de la comunidad de accesibilidad: WebAIM (Universidad del Estado de Utah), Siteimprove (empresa danesa), TPGi (antes The Paciello Group), SIDAR (Seminario Iberoamericano sobre Discapacidad y Accesibilidad en la Red).

## Fuentes
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27\|Fuente - Tema 1.2-Accesibilidad-26-27]], p. 82–91.
- Externas: [w3.org/WAI/test-evaluate/tools/list](https://www.w3.org/WAI/test-evaluate/tools/list/), [wave.webaim.org](http://wave.webaim.org/), [tawdis.net](https://www.tawdis.net), [validator.w3.org](http://validator.w3.org/).

## Mis notas
