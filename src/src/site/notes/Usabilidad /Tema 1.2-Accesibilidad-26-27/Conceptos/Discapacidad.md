---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-2-accesibilidad-26-27/conceptos/discapacidad/","tags":["materia/Usabilidad","tema/1.2"],"dg-note-properties":{"tipo":"concepto","aliases":["Disability","Deficiencias","Tipos de discapacidad"],"tags":["materia/Usabilidad","tema/1.2"],"nivel":1,"fuentes":["[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Discapacidad

> [!abstract] En una frase
> La **discapacidad** es una **diferencia individual que supera un límite más o menos arbitrario** (p. 17); su definición operativa, de cara al diseño, es *cualquier limitación que impide usar un sistema sin adaptaciones*.

## ¿Qué problema resuelve?
Para hacer un sistema accesible hay que saber **a qué** se adapta. "Discapacidad" como término es demasiado general; en diseño hace falta una **clasificación por tipos** que oriente las decisiones concretas: una ceguera no requiere lo mismo que una tetraplejia o un déficit cognitivo.

## Qué es
Es la **unidad de análisis** de la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]. El material (p. 17) ofrece una definición deliberadamente laxa — "diferencia individual que supera un límite más o menos arbitrario" — para subrayar dos cosas:

- **No es binaria**: muchas discapacidades están presentes "en mayor o menor grado entre muchas personas consideradas normales". Pensar en ellas no beneficia solo a los casos extremos.
- **Es contextual**: el "límite" depende del sistema (no ver bien no es discapacidad para usar un teléfono por voz; sí lo es para una pantalla pequeña).

### Clasificación (p. 20)

1. **Deficiencias visuales** (p. 21–35)
   - **Color**: [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Daltonismo\|Daltonismo]] y sus tres formas (protanopia, deuteranopia, tritanopia).
   - **Visión reducida**: menor agudeza visual.
   - **Ceguera**: ausencia completa — requiere canales alternativos (voz sintetizada, Braille actualizable).
2. **Auditivas** (p. 36–38)
   - Dificultades parciales o sordera total.
   - Usuarios de lengua de signos: vocabulario escrito reducido → cuidado con el nivel de lectura.
3. **Motrices** (p. 39–40)
   - Dificultad o imposibilidad de mover punteros, pulsar combinaciones, mantener teclas.
   - Alternativas: teclado completo, entrada por voz, por cabeza, por boca.
4. **Cognitivas** (p. 41–42)
   - Dificultades de concentración, memoria, comprensión.
   - Afectadas también por el envejecimiento y enfermedades degenerativas.
   - Dos "recetas": **sencillez** (lectura fácil) y **evaluación con personas apropiadas**.

### Prevalencia (datos del material, INE y OMS)

- **Mundo**: 16 % de la población mundial con discapacidad (OMS, 7-3-2023, p. 7).
- **España, EDAD 2020** (INE): 4,38 millones = **9,2 %** de la población (p. 19).
- **España, EDAD 2008** (INE): 8,5 % (3,8 M). Las encuestas EDDS 1999 daban el 9,0 %.
- **Centros residenciales (EDAD-centros 2023)**: 94,7 % de residentes con alguna discapacidad; 65 % tiene 80+ años (p. 19).
- **Edad**: la prevalencia se dispara con la edad (+14 puntos entre 65–75 años; +28 entre 75–85; 58 % a partir de 85) (p. 7).

## Cómo podrías haberlo descubierto
Si el objetivo del [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Diseño Universal\|Diseño Universal]] es acomodar la mayor diversidad posible, lo primero es **mapear esa diversidad**. La clasificación por canales sensoriales y motores (ver, oír, moverse, pensar) sigue la estructura de la interacción humana con un sistema: entrada, procesamiento, salida.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]: el diseño accesible se define *frente a* un abanico de discapacidades.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Diseño Universal\|Diseño Universal]]: usa esta clasificación como mapa de dimensiones a cubrir.

## Permite entender
- Por qué las [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Herramientas de evaluación de accesibilidad\|herramientas de evaluación]] detectan cosas distintas según el tipo de discapacidad: no es lo mismo revisar contraste de color (visual) que estructura del documento (lectores de pantalla) que tiempo de interacción (motriz/cognitiva).
- Por qué el principio del *curb cut effect* (p. 43–44) funciona: cada tipo de discapacidad tiene un análogo situacional en personas sin discapacidad (ceguera ↔ conductor con ojos ocupados; sordera ↔ biblioteca; motricidad limitada ↔ llevar al bebé en brazos).
- Por qué las nuevas versiones de [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]] (2.1 y 2.2) han añadido criterios específicos para discapacidad **cognitiva** y **móvil/baja visión**: la cobertura por tipo determina qué queda sin cubrir.

## Ejemplo
> [!example]
> **Un formulario web con captcha visual**: una persona ciega no puede resolverlo; una persona daltónica puede no distinguir los colores de validación; una persona con dislexia puede necesitar más tiempo para leer. Un solo formulario toca con las cuatro familias de discapacidad simultáneamente.

## Errores comunes
> [!warning]
> - **Reducir discapacidad a "silla de ruedas"**: la motricidad es solo una de cuatro familias.
> - **Pensar discapacidad como "ellos" frente a "nosotros"**: muchos tipos están presentes en grado leve en usuarios no diagnosticados.
> - **Suponer que es rara**: 16 % mundial, 9,2 % España, 58 % a partir de 85 años.

## Autoevaluación
> [!question]- ¿Qué cuatro familias de discapacidad reconoce el material?
> **Visuales** (color, visión reducida, ceguera), **auditivas**, **motrices** y **cognitivas**.

> [!question]- Según la encuesta EDAD 2020 del INE, ¿qué porcentaje de la población española tenía discapacidad?
> **9,2 %** (4,38 millones de personas).

> [!question]- ¿Por qué el material da una definición de discapacidad deliberadamente laxa ("diferencia individual que supera un límite arbitrario")?
> Para resaltar que no es binaria ni absoluta: hay muchas gradaciones y muchos casos "leves" en población no diagnosticada. Pensar en ellas beneficia a mucha más gente que la clínicamente discapacitada.

## Contraste
> [!success] Verificado
> La **OMS** cifra la discapacidad mundial en torno al 16 % desde 2023 (ver [who.int](https://www.who.int/es/news-room/fact-sheets/detail/disability-and-health)); coincide con el material. Los datos del **INE** citados (EDAD 2020, EDAD-centros 2023) son los oficiales. La clasificación en visuales / auditivas / motrices / cognitivas es también la que usa [Wikipedia: Accesibilidad web](https://es.wikipedia.org/wiki/Accesibilidad_web) ("auditivas, cognitivas, neurológicas, físicas, visuales"), con el matiz de que Wikipedia desglosa además "trastornos del habla" y "neurológicas", no mencionadas aparte en el material.

## Fuentes
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27\|Fuente - Tema 1.2-Accesibilidad-26-27]], p. 7, 17–20, 32, 36, 39, 41–44.
- Externas: [who.int — Disability and health](https://www.who.int/es/news-room/fact-sheets/detail/disability-and-health), [ine.es — EDAD 2020](https://www.ine.es/prensa/edad_2020_p.pdf), [es.wikipedia.org/wiki/Accesibilidad_web](https://es.wikipedia.org/wiki/Accesibilidad_web).

## Mis notas
