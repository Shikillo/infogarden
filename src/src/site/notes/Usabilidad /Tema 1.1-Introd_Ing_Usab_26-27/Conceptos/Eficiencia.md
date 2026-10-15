---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-1-introd-ing-usab-26-27/conceptos/eficiencia/","tags":["materia/Usabilidad","tema/1.1"],"dg-note-properties":{"tipo":"concepto","aliases":["Efficiency"],"tags":["materia/Usabilidad","tema/1.1"],"nivel":1,"fuentes":["[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Fuente - Tema 1.1-Introd_Ing_Usab_26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Eficiencia

> [!abstract] En una frase
> La **eficiencia** (efficiency) son los **recursos empleados** en relación con la precisión y plenitud con que los usuarios alcanzan los objetivos (ISO 9241-210:2019).

## ¿Qué problema resuelve?
Mientras la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Eficacia\|Eficacia]] pregunta "¿se consigue?", la eficiencia pregunta "**¿a qué coste?**". Un sistema puede ser 100 % eficaz y aun así inviable si cada tarea exige diez pasos innecesarios o un cuarto de hora de usuario experto. La eficiencia convierte el coste en una variable explícita de la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]].

## Qué es
Es el segundo de los tres atributos de la definición ISO 9241-210:2019 de usabilidad. "Recursos" se interpreta ampliamente:

- **Tiempo**: segundos o minutos para completar la tarea.
- **Esfuerzo cognitivo**: cuánto hay que pensar o recordar.
- **Pasos**: número de clics, pulsaciones o acciones.
- **Dinero / infraestructura**: cuando aplica.

El material (p. 29) la asocia con la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Facilidad de aprendizaje\|Facilidad de aprendizaje]] (que supone un coste en tiempo), con la tasa de [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Errores\|Errores]] (que también cuestan tiempo al corregirlos) y con la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Memorabilidad\|Memorabilidad]] (una asimilación inapropiada se traduce en errores que gastan recursos).

Nielsen (p. 30) la plantea como una pregunta operativa: "una vez que los usuarios han aprendido el diseño, ¿con qué rapidez pueden realizar las tareas?". Es decir, la eficiencia se mide **sobre usuarios ya expertos**, no sobre novatos.

## Cómo medirla
Pasos (p. 32):

1. **Establecer la definición de pericia** (qué significa ser "usuario experto" en este sistema).
2. Obtener una muestra de usuarios expertos (difícil).
3. Medir el tiempo (u otro recurso) empleado para realizar **tareas habituales**.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]]: la eficiencia es uno de sus tres atributos ISO.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Eficacia\|Eficacia]]: solo tiene sentido medir eficiencia sobre tareas que se completan con éxito.

## Permite entender
- Por qué los atajos de teclado existen: convierten pasos en acciones instantáneas y disparan la eficiencia del usuario experto.
- Por qué la curva de aprendizaje importa: el tiempo de la fase novato es un *coste* que afecta a la eficiencia global.

## Ejemplo
> [!example]
> **IDE con atajos**: un desarrollador novato tarda 20 segundos en buscar "Comentar línea" en el menú. Uno experto lo hace con `Ctrl+/` en 0,2 s. La eficacia es la misma (la línea queda comentada), pero la eficiencia difiere en dos órdenes de magnitud.

## Errores comunes
> [!warning]
> - **Confundir eficiencia con rapidez pura**: ir rápido pero equivocándose no es eficiente; es solo rápido.
> - **Medir eficiencia sobre novatos**: Nielsen la define sobre usuarios *que ya han aprendido el diseño*.
> - **Olvidar que "recursos" no es solo tiempo**: una interfaz que exige recordar mucho gasta un recurso cognitivo caro aunque no gaste segundos.

## Autoevaluación
> [!question]- Un usuario tarda 10 segundos en completar una tarea pero el sistema le obliga a recordar 12 pasos. ¿Es eficiente?
> No necesariamente. El tiempo es bajo, pero el coste cognitivo (recordar 12 pasos) es alto. La eficiencia considera *todos* los recursos, no solo el reloj.

> [!question]- ¿Sobre qué tipo de usuarios se mide la eficiencia según Nielsen?
> Sobre usuarios **expertos**, una vez han aprendido el diseño.

## Contraste
> [!success] Verificado
> La definición y la metodología de medida se corresponden con la ISO 9241-11 ("specification and measurement of usability"), confirmada por [Wikipedia: ISO 9241](https://en.wikipedia.org/wiki/ISO_9241).

## Fuentes
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Fuente - Tema 1.1-Introd_Ing_Usab_26-27\|Fuente - Tema 1.1-Introd_Ing_Usab_26-27]], p. 28–30, 32–33.

## Mis notas
