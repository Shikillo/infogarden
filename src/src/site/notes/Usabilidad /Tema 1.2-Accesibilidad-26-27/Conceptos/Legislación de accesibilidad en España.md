---
{"dg-publish":true,"permalink":"/usabilidad/tema-1-2-accesibilidad-26-27/conceptos/legislacion-de-accesibilidad-en-espana/","tags":["materia/Usabilidad","tema/1.2"],"dg-note-properties":{"tipo":"concepto","aliases":["LSSICE","RD 1494/2007","RD 1112/2018","UNE 139803","EN 301 549"],"tags":["materia/Usabilidad","tema/1.2"],"nivel":2,"fuentes":["[[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27]]"],"contraste":"verificado","estado":"nuevo"}}
---

# Legislación de accesibilidad en España

> [!abstract] En una frase
> La accesibilidad web en España se exige mediante **tres normas principales**: la **LSSICE 34/2002**, el **RD 1494/2007** (basado en la UNE 139803) y el **RD 1112/2018** (basado en la EN 301 549 y las [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]] 2.1 AA) (p. 13–16).

## ¿Qué problema resuelve?
Sin una referencia legal, las administraciones y empresas pueden ignorar la [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]. La legislación convierte las directrices técnicas de la [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WAI\|WAI]] en una obligación con sanciones, al menos para el sector público y, en algunos casos, para el privado.

## Qué es
### LSSICE — Ley 34/2002 (p. 14)

**Ley 34/2002, de 11 de julio, de servicios de la sociedad de la información y de comercio electrónico**.

- BOE 12 de julio de 2002; en vigor a los 3 meses (12-oct-2002).
- Disposición final quinta: las Administraciones Públicas tomarán las medidas necesarias para que la información de sus páginas de Internet sea **accesible a personas con discapacidad y de edad avanzada**, aplicando los **criterios de accesibilidad generalmente reconocidos antes del 31-dic-2005**.
- Permite exigir accesibilidad a las webs cuyo mantenimiento financien las administraciones.

### RD 1494/2007 (p. 15)

**Real Decreto 1494/2007, de 12 de noviembre**, sobre condiciones básicas para el acceso de personas con discapacidad a las TIC.

- Las páginas de la administración pública deben cumplir la **UNE 139803:2004** — norma española que se corresponde con WCAG 1.0.
- Calendario:
  - **Páginas nuevas** → prioridad 1 desde 22-11-2007.
  - **Páginas existentes** → prioridad 1 desde 22-05-2008.
  - **Todas las páginas** → prioridad 2 desde 31-12-2008.

### RD 1112/2018 (p. 16)

**Real Decreto 1112/2018, de 7 de septiembre**, sobre accesibilidad de sitios web y aplicaciones móviles del sector público.

- Transpone la **Directiva (UE) 2016/2102** sobre accesibilidad del sector público.
- Se aplica la norma **EN 301 549 v1.1.2** (que a su vez referencia WCAG 2.1 nivel **AA**).
- Entrada en vigor: 20-sep-2018.
- Calendario de aplicación:
  - **Sitios web públicos**: aplicación **inmediata**.
  - **Apps nativas**: desde **23-06-2021**.
  - **Intranets y extranets**: desde **23-09-2019**, solo si son nuevas o sufren reforma sustancial.

### Marco europeo (p. 48)

- **Directiva Europea de Accesibilidad** (EU Web Accessibility Directive 2016/2102 + EAA 2019/882).
- Comisión Europea publica guías propias de accesibilidad.
- La **EN 301 549** es la norma técnica europea que referencia WCAG 2.1 AA y aplica a sector público y, con el EAA, a muchos productos y servicios privados a partir de 2025.

## Cómo podrías haberlo descubierto
La UE legisla accesibilidad con directivas; cada estado miembro las traspone a su derecho interno. En España, la cadena natural es: UE → directiva → RD español → norma UNE/EN → WCAG.

## Depende de
- [[Usabilidad /Tema 1.1-Introd_Ing_Usab_26-27/Conceptos/Accesibilidad\|Accesibilidad]]: el objeto que la ley regula.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/WCAG\|WCAG]]: la norma técnica referenciada.
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Conceptos/Niveles de conformidad WCAG\|Niveles de conformidad WCAG]]: la ley exige AA en RD 1112/2018.

## Permite entender
- Por qué una administración pública española que publique una app móvil **tiene que** cumplir WCAG 2.1 AA: lo dice el RD 1112/2018 por vía de la EN 301 549.
- Por qué cuando una ley cita una **versión concreta** de una norma técnica, basta con **actualizar la norma** (sin tocar la ley) para elevar el estándar.
- Por qué la legislación distingue "sitio nuevo" / "sitio existente" / "reforma sustancial": da plazos razonables.

## Ejemplo
> [!example]
> **Un ayuntamiento publica un nuevo portal en 2026**: debe cumplir WCAG 2.1 **AA** desde el día uno. Debe publicar una **declaración de accesibilidad** (obligatoria por RD 1112/2018) y un mecanismo para que la ciudadanía reporte problemas. Si no lo hace, incumple ley y puede ser requerido por la Secretaría General de Administración Digital.

## Errores comunes
> [!warning]
> - **Confundir UNE 139803 con WCAG**: la UNE es la traducción/adaptación española de WCAG 1.0; la EN 301 549 referencia WCAG 2.1 AA.
> - **Pensar que la ley solo aplica a webs**: desde 2021 también aplica a apps móviles y, con el EAA, a muchos productos y servicios digitales privados en 2025.
> - **Confundir "aplicación inmediata" con "retroactivo"**: aplicación inmediata es *para nuevos sitios*; los existentes tenían plazos específicos.

## Autoevaluación
> [!question]- ¿Qué nivel de conformidad WCAG exige el RD 1112/2018 por la EN 301 549?
> **Nivel AA** de WCAG 2.1.

> [!question]- ¿Qué norma UNE referencia el RD 1494/2007?
> **UNE 139803:2004** (correspondiente a WCAG 1.0).

> [!question]- ¿Desde cuándo las apps móviles del sector público españolas tienen que ser accesibles?
> Desde el **23 de junio de 2021** (RD 1112/2018, p. 16).

## Contraste
> [!success] Verificado
> Las fechas y el contenido de las tres normas se verifican en el BOE: [LSSICE 34/2002](https://www.boe.es/buscar/doc.php?id=BOE-A-2002-13758), [RD 1494/2007](https://www.boe.es/buscar/doc.php?id=BOE-A-2007-19968), [RD 1112/2018](https://www.boe.es/diario_boe/txt.php?id=BOE-A-2018-12699). La transposición de la Directiva 2016/2102 por el RD 1112/2018 está confirmada.

## Fuentes
- [[Usabilidad /Tema 1.2-Accesibilidad-26-27/Fuente - Tema 1.2-Accesibilidad-26-27\|Fuente - Tema 1.2-Accesibilidad-26-27]], p. 13–16, 48.
- Externas: [BOE-A-2002-13758 (LSSICE)](https://www.boe.es/buscar/act.php?id=BOE-A-2002-13758), [BOE-A-2007-19968 (RD 1494/2007)](https://www.boe.es/buscar/doc.php?id=BOE-A-2007-19968), [BOE-A-2018-12699 (RD 1112/2018)](https://www.boe.es/diario_boe/txt.php?id=BOE-A-2018-12699).

## Mis notas
