---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-1-introd-ing-usab-26-27/conceptos/ingenieria-de-usabilidad/","tags":["materia/Usabilidad","tema/1.1"],"dg-note-properties":{"tipo":"concepto","aliases":["Usability Engineering","IU","Ingeniería de la Usabilidad"],"tags":["materia/Usabilidad","tema/1.1"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Fuente - Tema 1.1-Introd_Ing_Usab_26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Ingeniería de Usabilidad

> [!abstract] En una frase
> La **Ingeniería de Usabilidad** es un **método sistemático, disciplinado y cuantitativo** de diseño y desarrollo de sistemas que toma en cuenta el factor humano para construir interfaces con un alto grado de [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]] (Corrales, 1998, p. 34).

## ¿Qué problema resuelve?
Si la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]] es el *qué* (una propiedad medible del sistema), hace falta un **cómo**: un proceso repetible que la produzca de forma fiable, no como accidente afortunado. La Ingeniería de Usabilidad es ese cómo: convierte el objetivo "sistema usable" en un proceso con pasos y métricas, igual que la Ingeniería del Software lo hace para la calidad del código.

## Qué es
Es un **campo de la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|Interacción Persona-Ordenador (IPO/HCI)]]** dedicado específicamente a construir interfaces con alto grado de usabilidad (p. 34). Combina tres rasgos:

- **Sistemático**: aplica un proceso con fases definidas (no improvisado).
- **Disciplinado**: sigue normas, criterios y evaluaciones objetivas.
- **Cuantitativo**: fija métricas (eficacia, eficiencia, tasa de errores, satisfacción) y las mide.

El material (p. 35) añade dos definiciones "según la IA" que coinciden en lo esencial:
- "enfoque sistemático y disciplinado para mejorar la usabilidad de productos y servicios... No se trata solo de un conjunto de pruebas o evaluaciones finales, sino de un **proceso integral que se integra en todas las fases del ciclo de vida de un proyecto**, desde el análisis inicial hasta el diseño, desarrollo y evaluación".

Y la pone en el mismo plano estructural que la Ingeniería del Software, en cuya definición IEEE se inspira (p. 36): "la aplicación de un enfoque sistemático, disciplinado y cuantificable para el desarrollo, operación y mantenimiento del software".

En el proceso, la Ingeniería de Usabilidad usa como **paradigma central** el [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]] y como **entrada** los [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Requerimientos del Usuario\|Requerimientos del Usuario]]. Sus salidas son interfaces evaluables en los seis atributos ([[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Eficacia\|Eficacia]], [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Facilidad de aprendizaje\|Facilidad de aprendizaje]], [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Eficiencia\|Eficiencia]], [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Memorabilidad\|Memorabilidad]], [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Errores\|Errores]], [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Satisfacción\|Satisfacción]]).

## Cómo podrías haberlo descubierto
Si el objetivo es la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]] y la quieres **medir** (ISO 9241-210:2019 obliga: eficacia, eficiencia, satisfacción), necesitas instrumentos y un orden. Y si quieres **repetir** el éxito, un proceso. Al ponerle nombre a ese método disciplinado, aparece la Ingeniería de Usabilidad como analogía directa de la Ingeniería del Software: mismo esqueleto, otro objeto.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]]: fija el objetivo.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]]: su paradigma de proceso.
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Requerimientos del Usuario\|Requerimientos del Usuario]]: su entrada.

## Permite entender
- Por qué un curso llamado "Ingeniería de la Usabilidad" existe: no es "diseño gráfico" ni "estudios de usuario sueltos"; es un cuerpo de método.
- Por qué la asignatura cubre, en orden, [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Usabilidad\|Usabilidad]] → [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]] → [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]]/MPIU+a → [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Requerimientos del Usuario\|Requerimientos del Usuario]]: ese es el esqueleto del proceso.
- La relación con la Ingeniería del Software (p. 36): mismo marco mental, aplicado al factor humano.

## Ejemplo
> [!example]
> **Analogía con la Ingeniería del Software**: en Ingeniería del Software, el objetivo "software de calidad" se operativiza en métricas (cobertura de pruebas, defectos por KLOC, tiempo de respuesta) y en un ciclo de vida (análisis → diseño → implementación → pruebas → mantenimiento). La Ingeniería de Usabilidad hace lo mismo con el objetivo "sistema usable": métricas (los 6 atributos) y ciclo de vida (DCU, con investigación → diseño → prototipado → evaluación → iteración).

## Errores comunes
> [!warning]
> - **Reducirla a "hacer tests al final"**: es un proceso integral desde el análisis inicial, no una fase.
> - **Confundirla con el diseño gráfico**: el diseño es *parte* del proceso, no su totalidad.
> - **Separarla de la Ingeniería del Software**: ambas conviven en el ciclo de desarrollo del producto; una ignora a la otra con mucho coste.

## Autoevaluación
> [!question]- ¿Qué tres rasgos definen el enfoque de la Ingeniería de Usabilidad?
> **Sistemático, disciplinado y cuantitativo** (análogo a la definición IEEE de Ingeniería del Software).

> [!question]- ¿En qué fases del ciclo de vida interviene?
> En **todas**: desde el análisis inicial hasta diseño, desarrollo y evaluación. No es una fase final de validación.

## Contraste
> [!success] Verificado
> [Wikipedia: Usability engineering](http://en.wikipedia.org/wiki/Usability_engineering) describe la Ingeniería de Usabilidad como una **subdisciplina del HCI** que estructura el desarrollo de sistemas interactivos para alcanzar un buen grado de usabilidad; coincide con el material. La relación con el DCU y con la Ingeniería del Software (IEEE) es la clásica.

## Fuentes
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Fuente - Tema 1.1-Introd_Ing_Usab_26-27\|Fuente - Tema 1.1-Introd_Ing_Usab_26-27]], p. 34–36.
- Externas: [en.wikipedia.org/wiki/Usability_engineering](http://en.wikipedia.org/wiki/Usability_engineering), [es.wikipedia.org/wiki/Interacci%C3%B3n_persona-computadora](https://es.wikipedia.org/wiki/Interacci%C3%B3n_persona-computadora).

## Mis notas
