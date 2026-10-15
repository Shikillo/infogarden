---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-1-introd-ing-usab-26-27/conceptos/errores/","tags":["materia/Usabilidad","tema/1.1"],"dg-note-properties":{"tipo":"concepto","aliases":["Errors","Tasa de errores"],"tags":["materia/Usabilidad","tema/1.1"],"nivel":1,"fuentes":["[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Fuente - Tema 1.1-Introd_Ing_Usab_26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Errores

> [!abstract] En una frase
> El atributo de **errores** (errors) mide **cuántos errores cometen los usuarios, cuál es su gravedad y con qué facilidad pueden recuperarse de ellos** (Jakob Nielsen, nngroup.com).

## ¿Qué problema resuelve?
Ningún usuario trabaja sin equivocarse. Un sistema puede ser rápido y preciso en el caso ideal y, aun así, fracasar si un error pequeño del usuario tiene consecuencias catastróficas o si corregirlo requiere mucho esfuerzo. Este atributo convierte **la tolerancia al error** en una medida de [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]].

## Qué es
Es uno de los 5 componentes de calidad de Jakob Nielsen (p. 30). No se mide solo *cuántos* errores se producen, sino tres cosas distintas:

- **Frecuencia**: cuántos errores comete el usuario (tasa de errores).
- **Gravedad**: cuán grave es cada uno (desde un clic equivocado hasta una pérdida de datos).
- **Recuperabilidad**: cuánto cuesta corregirlos (deshacer, volver atrás, reintentar).

El material (p. 33) resume este atributo diciendo que un sistema usable es **"tolerante a los errores"**. Es decir: no basta con reducir errores; también hay que diseñar para que, cuando ocurran, el daño sea pequeño y la recuperación sencilla.

Hay dos técnicas de interfaz asociadas:

- **Mensajes de error "para humanos"** (p. 67): texto comprensible que explique qué ha pasado y cómo arreglarlo, no códigos técnicos.
- **Permitir deshacer** (p. 57): el usuario necesita poder revertir sus acciones.

## Cómo medirlo
Metodología (p. 32):

1. Contabilizar los **errores leves y catastróficos** cometidos por los usuarios durante una tarea especificada.
2. Métrica típica: **número de desviaciones respecto a la ruta de clics óptima**.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]]: es uno de los 6 atributos consolidados.

## Permite entender
- Por qué un sistema sin "deshacer" es poco usable: la gravedad de un error se dispara si no hay vuelta atrás.
- Por qué los mensajes de error técnicos ("ERROR 0x80070005") penalizan la usabilidad: no ayudan a recuperarse.
- Que la clasificación de errores en *leves* y *catastróficos* sirve para priorizar: lo catastrófico pesa mucho más en la medida.

## Ejemplo
> [!example]
> **F1 McLaren — botón del limitador** (p. 69): un botón del limitador de velocidad mal colocado hace que pilotos profesionales lo pulsen por error y pierdan carreras. Pequeña frecuencia, pero **gravedad enorme** y **recuperabilidad nula** (ya se perdió el tiempo). La tasa de errores aquí no es alta; lo que falla es la gravedad.

## Errores comunes
> [!warning]
> - **Confundir "pocos errores" con "sistema usable"**: si los errores son raros pero catastróficos, el atributo falla.
> - **Olvidar la recuperabilidad**: diseñar para evitar errores no es lo mismo que diseñar para corregirlos.
> - **Mezclar error del usuario y error del sistema**: aquí hablamos del del usuario (incluye desvíos de la ruta óptima), aunque muchos vienen inducidos por un mal diseño.

## Autoevaluación
> [!question]- ¿Cuáles son las tres dimensiones que mide este atributo?
> **Frecuencia** (cuántos), **gravedad** (cuán graves) y **recuperabilidad** (cuánto cuesta corregirlos).

> [!question]- ¿Por qué un mensaje "Error 0x80070005" penaliza la usabilidad?
> Porque no ayuda al usuario a entender qué ha pasado ni a recuperarse: baja la recuperabilidad.

## Contraste
> [!success] Verificado
> La definición y las tres dimensiones (frecuencia, gravedad, recuperabilidad) corresponden a la literatura canónica de Nielsen Norman Group ([nngroup.com/articles/usability-101](https://www.nngroup.com/articles/usability-101-introduction-to-usability/)). También es coherente con las heurísticas de Nielsen (ayuda a reconocer, diagnosticar y recuperarse de errores).

## Fuentes
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Fuente - Tema 1.1-Introd_Ing_Usab_26-27\|Fuente - Tema 1.1-Introd_Ing_Usab_26-27]], p. 29–33, 57, 63, 67, 69.

## Mis notas
