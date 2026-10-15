---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-2-accesibilidad-26-27/conceptos/principios-pour/","tags":["materia/Usabilidad","tema/1.2"],"dg-note-properties":{"tipo":"concepto","aliases":["POUR","Perceptible Operable Comprensible Robusto","Perceivable Operable Understandable Robust"],"tags":["materia/Usabilidad","tema/1.2"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Principios POUR

> [!abstract] En una frase
> Los **4 principios POUR** son la columna vertebral de **WCAG 2.0 y posteriores**: el contenido web tiene que ser **Perceptible, Operable, Comprensible y Robusto** (p. 68–72).

## ¿Qué problema resuelve?
Pasar de 14 pautas sueltas (WCAG 1.0) a un marco **con una estructura mental** que permita ubicar cualquier criterio nuevo. Antes de añadir una regla hay que preguntarse: *¿esto es un problema de percepción, de operación, de comprensión o de robustez técnica?* Los principios dan la casilla.

## Qué es
Son los 4 principios en los que se organizan todas las pautas y criterios de las [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]] 2.0, 2.1 y 2.2. Cada uno responde a una pregunta operativa:

### 1. Perceptible (p. 69)
> La información y los componentes de la interfaz de usuario **deben presentarse a los usuarios de manera que puedan percibirlos**.

Pautas:
- 1.1 Alternativas textuales.
- 1.2 Multimedia dependiente del tiempo.
- 1.3 Adaptabilidad (presentar el contenido en diferentes formas sin perder información).
- 1.4 Distinguible (separación fondo/figura, contraste).

### 2. Operable (p. 70)
> Los componentes de la interfaz de usuario y la navegación **deben ser operables**.

Pautas:
- 2.1 Accesible a través del teclado.
- 2.2 Tiempo suficiente.
- 2.3 Convulsiones y reacciones físicas (evitar parpadeos peligrosos).
- 2.4 Navegable.
- *(2.5 Modalidades de entrada — añadida en 2.1.)*

### 3. Comprensible (p. 71)
> La información y el manejo de la interfaz **deben ser comprensibles**.

Pautas:
- 3.1 Legible (lenguaje identificado, abreviaturas aclaradas).
- 3.2 Predecible (comportamiento coherente).
- 3.3 Ayuda a la entrada de datos (prevenir y corregir errores).

### 4. Robusto (p. 72)
> El contenido debe ser **lo suficientemente robusto** como para que su interpretación sea fiable por una **amplia variedad de agentes de usuario**, incluidas las **tecnologías asistivas**.

Pautas:
- 4.1 Compatible (con navegadores, lectores de pantalla, dispositivos actuales y futuros).

Un dato relevante: el criterio **4.1.1 Parsing** se eliminó en WCAG 2.2 porque los parsers de HTML modernos ya son robustos a errores menores de marcado.

## Cómo podrías haberlo descubierto
Un sistema interactivo tiene cuatro cosas que pueden fallar para un usuario con discapacidad: **ver/oír** la información (percepción), **manipular** la interfaz (operación), **entender** lo que ocurre (comprensión) o **que la tecnología asistiva lo interprete** (robustez técnica). Un principio por cada uno.

## Depende de
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]]: los principios son su estructura organizativa desde la versión 2.0.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Discapacidad\|Discapacidad]]: cada principio apunta a tipos distintos (perceptible → visuales/auditivas; operable → motrices; comprensible → cognitivas; robusto → compatibilidad técnica con tecnologías asistivas de todas las anteriores).

## Permite entender
- Por qué un vídeo sin subtítulos **y** sin transcripción falla por "**Perceptible**", no por "Comprensible": el usuario no puede *percibir* el contenido de audio.
- Por qué una web **solo navegable con ratón** falla por "**Operable**" (criterio 2.1.1 Teclado), aunque el diseño sea bonito y comprensible.
- Por qué un lector de pantalla que no entienda la estructura de la página falla por "**Robusto**" (compatibilidad), no por los otros tres.

## Ejemplo
> [!example]
> **Un botón hecho con un `div` y un *onclick*** (en vez de la etiqueta `button` nativa): se ve y se entiende; incluso puede operarse con ratón. Pero un lector de pantalla puede no reconocerlo como botón ni dejar al usuario de teclado activarlo con Enter. Falla por **Operable** (teclado) y **Robusto** (compatibilidad), pero no por Perceptible ni Comprensible.

## Errores comunes
> [!warning]
> - **Confundir "comprensible" con "operable"**: una web puede ser perfectamente operable (navegable, controlable) y aun así ser incomprensible (textos crípticos, formularios sin instrucciones).
> - **Olvidar el "robusto"**: muchos sitios cumplen los tres primeros principios pero no son robustos frente a navegadores antiguos o tecnologías asistivas.
> - **Pensar que son 4 reglas**: son 4 **principios** que agrupan 12 o 13 pautas y decenas de criterios.

## Autoevaluación
> [!question]- Enumera los 4 principios POUR y qué pregunta responde cada uno.
> - **P**erceptible: ¿puede el usuario *percibir* la información?
> - **O**perable: ¿puede *manipular* la interfaz?
> - **C**omprensible: ¿puede *entender* la interfaz y la información?
> - **R**obusto: ¿pueden las *tecnologías asistivas* interpretarla fiablemente?

> [!question]- ¿Qué principio incluye el criterio "accesible mediante teclado"?
> **Operable** (pauta 2.1).

> [!question]- ¿Qué principio desaparece con la eliminación de 4.1.1 Parsing en WCAG 2.2?
> Ninguno: el principio **Robusto** sigue intacto; solo se elimina ese criterio específico (parseo) porque los navegadores actuales son robustos a errores de HTML.

## Contraste
> [!success] Verificado
> Los 4 principios y su enunciado coinciden con [w3.org/TR/WCAG22/](https://www.w3.org/TR/WCAG22/) y con [Wikipedia: WCAG](https://es.wikipedia.org/wiki/Web_Content_Accessibility_Guidelines). El acrónimo "POUR" se usa comúnmente en la comunidad de accesibilidad (W3C, WebAIM, Deque) y es la forma estándar de referirse a este marco.

## Fuentes
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27\|Fuente - Tema 1.2-Accesibilidad-26-27]], p. 68–73, 80–81.
- Externas: [w3.org/TR/WCAG22/#principles](https://www.w3.org/TR/WCAG22/), [sidar.org/traducciones/wcag20/es/](http://www.sidar.org/traducciones/wcag20/es/).

## Mis notas
