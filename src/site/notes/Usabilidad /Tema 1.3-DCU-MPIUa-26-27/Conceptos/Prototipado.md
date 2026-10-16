---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-3-dcu-mpi-ua-26-27/conceptos/prototipado/","tags":["materia/Usabilidad","tema/1.3"],"dg-note-properties":{"tipo":"concepto","aliases":["Prototipos","Prototyping","Prototipado contextual"],"tags":["materia/Usabilidad","tema/1.3"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Prototipado

> [!abstract] En una frase
> El **prototipado** es la fase del [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]] (y una técnica central del [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]]) en la que se construyen **representaciones concretas y evaluables** del sistema a distintos niveles de fidelidad, para iterar con los usuarios antes de implementar nada en código (p. 32, 62–68).

## ¿Qué problema resuelve?
Escribir código es caro; cambiarlo cuando el usuario descubre que el flujo es confuso, lo es aún más. Los prototipos permiten **probar el diseño con usuarios reales mucho antes de implementarlo**, cuando corregirlo cuesta minutos (papel, Figma) en vez de semanas (código ya desplegado).

## Qué es
En [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]] es la **Fase 3** (después de Diseño) y aparece también como "**prototipado contextual**" (p. 32).

### Jerarquía de técnicas por fidelidad

De menor a mayor fidelidad (p. 32, 62):

1. **Bocetos o esbozos**: dibujos a mano. La idea más barata y rápida.
2. **Storyboards**: secuencia de bocetos que cuentan un uso.
3. **Prototipos de papel**: pantallas dibujadas en papel que el usuario "clica" señalando.
4. **Maquetas**: representaciones físicas o digitales con más detalle.
5. **Maquetas digitales**: en herramientas como Figma, Sketch, Adobe XD.
6. **Storyboards navegacionales (wireframes)**: estructura de pantallas e interacciones.
7. **Vídeos**: para flujos difíciles de capturar en estático.
8. **Prototipos software**: ya con código funcional parcial.

### Representaciones narrativas (p. 62)

Complementan a las visuales:

- **Escenarios**: historias cortas que describen un uso.
- **Lenguaje natural**: descripción textual de la interacción.
- **Casos de uso UML**: la variante formal, también de Ingeniería del Software.

### Niveles de fidelidad

Convención (no literal del material pero estándar en HCI):

- **Baja fidelidad**: bocetos, prototipos de papel, wireframes. Baratos, rápidos, fáciles de desechar.
- **Media fidelidad**: maquetas digitales clicables sin lógica real.
- **Alta fidelidad**: prototipos software con interacción casi final.

### Regla del DCU (p. 13)

> *"El usuario debe tratar de realizar tareas reales (factibles) usando el diseño que presenta soluciones potenciales y su feedback debe ser usado para desarrollar o modificar un nuevo diseño más adelante."*

El prototipo **tiene que ser suficientemente concreto** para que el usuario intente **tareas reales**; si no, el feedback es decorativo.

## Cómo podrías haberlo descubierto
Si quieres probar un diseño con el usuario sin pagar el coste de implementarlo, necesitas algo que **se vea y se toque** sin ser código real. La escalera papel → maqueta → prototipo software emerge sola de ir subiendo la fidelidad conforme el diseño madura.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/DCU\|DCU]]: el prototipado es su herramienta principal de iteración.
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/MPIU+a\|MPIU+a]]: su Fase 3.

## Permite entender
- Por qué los **prototipos de papel** siguen siendo útiles pese a Figma: su desechabilidad es la ventaja, no un defecto.
- Por qué un **prototipo clicable** es tan importante en la evaluación con [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Conceptos/Evaluación de usabilidad\|thinking aloud]]: permite tareas reales sin código.
- La diferencia entre **wireframe** (estructura, sin estilo) y **mockup** (estructura + estilo visual).
- Por qué el DCU rechaza "entregar un diseño perfecto a la primera": el prototipado presume que **habrá iteraciones**.

## Ejemplo
> [!example]
> **App de reserva de restaurante**:
> - **Boceto (día 1)**: 4 pantallas garabateadas en una hoja para discutir el flujo con el equipo.
> - **Prototipo de papel (día 3)**: 10 pantallas pintadas en folios; se enseña a 3 usuarios que "pulsan" sobre el papel.
> - **Wireframe digital (semana 2)**: lo mismo en Figma, con transiciones.
> - **Maqueta digital (semana 3)**: con colores, tipografía y lógica simulada.
> - **Prototipo software (semana 5)**: con backend real.
>
> Cada paso se evalúa; si falla, se vuelve atrás antes de subir de fidelidad.

## Errores comunes
> [!warning]
> - **Saltar directo al prototipo software**: pierdes la ventaja del boceto desechable.
> - **Enamorarse del prototipo**: cuanto más esfuerzo pones, menos lo tiras; por eso empezar en papel ayuda.
> - **Enseñar un wireframe pidiendo opinión estética**: la gente dice "le pondría más color"; el feedback útil viene de **tareas reales**.
> - **Confundir prototipo con MVP**: el prototipo *no se vende*; el MVP sí.

## Autoevaluación
> [!question]- Enumera, de menor a mayor fidelidad, las técnicas principales de prototipado del material.
> **Bocetos → storyboards → prototipos de papel → maquetas → maquetas digitales → storyboards navegacionales (wireframes) → vídeos → prototipos software** (p. 32, 62).

> [!question]- ¿Qué regla del DCU exige el principio 3 sobre lo que el usuario hace con el prototipo?
> Que trate de **realizar tareas reales (factibles)**, no mirarlo abstractamente (p. 13).

> [!question]- ¿Por qué un boceto en papel puede ser mejor para iterar que un prototipo bonito en Figma?
> Porque **es más fácil tirarlo**: menos esfuerzo invertido = menos resistencia a cambiarlo cuando el usuario señala un problema.

## Contraste
> [!success] Verificado
> La jerarquía de fidelidades (baja/media/alta) es canónica en IPO y aparece así en Nielsen (*Usability Engineering*, 1993), Rogers, Sharp & Preece (*Interaction Design*) y en el currículo de HCI de la ACM. Las técnicas listadas en el material coinciden con ese canon.

## Fuentes
- [[Usabilidad /Tema 1.3-DCU-MPIUa-26-27/Fuente - Tema 1.3-DCU-MPIUa-26-27\|Fuente - Tema 1.3-DCU-MPIUa-26-27]], p. 13, 32, 61–68.
- Externas: Nielsen (Usabilidad, Prentice Hall 2000); Krug (*No me hagas pensar*, 2001–2015).

## Mis notas
