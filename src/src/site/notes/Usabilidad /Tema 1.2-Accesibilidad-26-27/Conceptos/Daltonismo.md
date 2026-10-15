---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-2-accesibilidad-26-27/conceptos/daltonismo/","tags":["materia/Usabilidad","tema/1.2"],"dg-note-properties":{"tipo":"concepto","aliases":["Discromatopsia","Color blindness","Protanopia","Deuteranopia","Tritanopia"],"tags":["materia/Usabilidad","tema/1.2"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Daltonismo

> [!abstract] En una frase
> El **daltonismo** es la **dificultad para distinguir colores** derivada de un déficit en uno de los tres tipos de conos de la retina (p. 22).

## ¿Qué problema resuelve?
El material lo escoge como el **ejemplo más concreto** de deficiencia visual relacionada con el color, porque permite derivar directamente **reglas de diseño prácticas**: nunca codificar información crítica solo por color.

## Qué es
Es una **anomalía genética** de los conos de la retina. Hay tres tipos de conos, especializados en rojo, verde y azul; el resto de colores se obtiene por combinación (p. 21). El daltonismo aparece cuando falla alguno:

- **Protanopia**: ausencia de color **rojo**.
- **Deuteranopia**: ausencia de color **verde**.
- **Tritanopia**: ausencia de color **azul**.

Datos del material (p. 22):

- Afecta al **8 % de los hombres** y al **0,5 % de las mujeres**.
- La diferencia por sexo se debe a que los genes están en el **cromosoma X** (los hombres tienen uno; una copia defectuosa basta).
- **La falta de percepción del azul (tritanopia) es la más grave pero la menos común.**

### Reglas de diseño (p. 27)

1. **No codificar ninguna conducta importante únicamente mediante colores**.
2. Usar **colores perfectamente distinguibles** (comprobar con herramientas).
3. **Comprobar la visualización en distintas condiciones** (daltonismo, pantalla con poca saturación, impresión en escala de grises, baja luz…).

### Herramientas (p. 28–29)

- **Generadores de paletas accesibles**: palett.es.
- **Verificadores de contraste**: Color Contrast Check, Adobe Color, Color Contrast Analyzer.

## Cómo podrías haberlo descubierto
Si observas que el 8 % de los hombres no distingue bien rojo del verde, basta con mirar cualquier interfaz que señale "error" en rojo y "éxito" en verde para ver el fallo. La regla "no codificar solo por color" es la contrapartida directa.

## Depende de
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Discapacidad\|Discapacidad]]: es un tipo específico de deficiencia visual del color.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]: motiva reglas concretas de diseño.

## Permite entender
- Por qué los sistemas usan **doble codificación** (color + icono + texto): rojo con una ⚠️ y la palabra "error" es accesible; rojo solo no lo es.
- Por qué la **Pauta 2** de WCAG 1.0 ("no confiar solo en el color") y el criterio **1.4.1 Uso del color** de WCAG 2.x existen.
- Por qué los **enlaces** se recomiendan subrayados *además de* coloreados (coincide con la crítica de Jakob Nielsen en el Tema 1.1).

## Ejemplo
> [!example]
> **Formulario con "campos obligatorios en rojo"** y nada más: una persona daltónica (protanopia o deuteranopia) no distinguirá qué campos son obligatorios. Solución universal: añadir asterisco `*` o la palabra "obligatorio" (doble codificación: color + texto).

## Errores comunes
> [!warning]
> - **Confundir daltonismo con "ver en blanco y negro"**: eso es [acromatopsia](https://es.wikipedia.org/wiki/Acromatopsia), que es muy rara. El daltonismo clásico es dificultad para distinguir **ciertos** colores entre sí.
> - **Pensar que afecta a muy poca gente**: 8 % de los hombres es **1 de cada 12**; en una web con 10 000 visitantes hombres hay ~800 daltónicos.
> - **"Lo arreglamos con un modo oscuro"**: el daltonismo no se arregla cambiando tema; se arregla no codificando información solo por color.

## Autoevaluación
> [!question]- ¿Por qué el daltonismo afecta mucho más a hombres (8 %) que a mujeres (0,5 %)?
> Los genes de los conos defectuosos están en el **cromosoma X**. Los hombres tienen un solo X, por lo que una copia defectuosa basta; las mujeres tienen dos X y necesitan ambas defectuosas.

> [!question]- Nombra los tres tipos clásicos de daltonismo y qué color falta en cada uno.
> **Protanopia** (sin rojo), **deuteranopia** (sin verde), **tritanopia** (sin azul).

> [!question]- ¿Cuál es la regla de diseño más importante?
> **No codificar ninguna información importante únicamente mediante el color**. Añadir siempre una segunda vía: texto, icono, subrayado, forma.

## Contraste
> [!success] Verificado
> [Wikipedia: Daltonismo](https://es.wikipedia.org/wiki/Daltonismo) confirma la relación con el cromosoma X y la mayor prevalencia en hombres. El término procede del químico John Dalton, que estudió su propio caso.

> [!info] Matizado — porcentajes
> El material cifra 8 % hombres y 0,5 % mujeres. Wikipedia no da porcentajes exactos, pero las fuentes clínicas estándar (Color Vision Research, Birch 2012) sitúan la prevalencia en **~8 % de hombres y ~0,5 % de mujeres** para los déficits rojo-verde (que son la gran mayoría). Las cifras del material son correctas para "daltonismo" en el sentido más común. La **tritanopia** es extremadamente rara (<0,01 %), coherente con que el material la clasifique como "la menos común".

> [!info] Matizado — "daltonismo" vs "discromatopsia"
> Estrictamente, "daltonismo" designa los déficits de color **congénitos** (heredados). "Discromatopsia" es el término general para cualquier anomalía de la visión del color, incluidas las adquiridas. En el material y en la práctica se usan como sinónimos.

## Fuentes
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27\|Fuente - Tema 1.2-Accesibilidad-26-27]], p. 21–29.
- Externas: [es.wikipedia.org/wiki/Daltonismo](https://es.wikipedia.org/wiki/Daltonismo), [color-blindness.com](http://www.color-blindness.com/), [learn.microsoft.com/windows/win32/uxguide/vis-color](https://learn.microsoft.com/ko-kr/windows/win32/uxguide/vis-color).

## Mis notas
