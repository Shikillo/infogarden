---
{"dg-publish":true,"permalink":"/redes/arc-tema-2/conceptos/aloha/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["ALOHA Protocol","ALOHA puro","ALOHA ranurado","Slotted ALOHA"],"tags":["materia/redes","tema/protocolos"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_2/Fuente - ARC_Tema_2]]"],"contraste":"verificado","estado":"nuevo"}}
---

# ALOHA

> [!abstract] En una frase
> Primer **protocolo de acceso múltiple aleatorio** (Hawaii, 1970): **transmite en cuanto hay datos** y, si colisiona, **reintenta tras un tiempo aleatorio**; existe en versión **pura** y **ranurada**.

## ¿Qué problema resuelve?
Antes de ALOHA, compartir un canal entre muchos emisores exigía una **asignación estática** (TDM, FDM) o una **coordinación central**. Norman Abramson y su equipo se enfrentaron a un problema distinto en la Universidad de Hawaii: conectar terminales dispersos por **varias islas** con una computadora central en Honolulu, por **radio**, sin un árbitro central y con tráfico muy irregular. La solución radical fue: *"transmite y, si choca, vuelve a intentarlo"*. Nace así la familia de **protocolos de acceso múltiple aleatorio**.

## Qué es
Según el material (p. 7-9), ALOHA tiene **dos versiones**:

### ALOHA puro
- Un conjunto potencialmente **infinito** de usuarios con terminales (p. 8).
- Estados: **EN ESPERA** o **ENVIANDO**.
- Cuando el usuario termina una línea, la estación la encapsula en un **cuadro** y lo envía por el **canal compartido** al computador central, verificando después si llegó bien (p. 8).
- Si fue bien, el usuario ve la respuesta y vuelve a escribir.
- Si no (hubo colisión), la estación **retransmite el cuadro una y otra vez** hasta que se envía con éxito (p. 8).

Clave: **no se escucha el canal antes de transmitir**. Esto hace que cualquier solapamiento, aunque sea mínimo, destruya ambas tramas. La **eficiencia máxima** teórica es muy baja (~18 % del canal).

### ALOHA ranurado
Propuesto por Roberts en 1972 (p. 9). Introduce una idea sencilla:

- El tiempo se divide en **intervalos discretos ("ranuras")**.
- **Cada ranura corresponde a una trama**.
- Los usuarios **tienen que ponerse de acuerdo sobre los límites de las ranuras**: la sincronización es **obligatoria**.
- Una **estación especial** emite un *pip* al comienzo de cada intervalo, como un **reloj común** (p. 9).

Con solo esta regla, dos tramas o colisionan por completo o no colisionan en absoluto, y la eficiencia **se duplica** (~37 %) respecto al ALOHA puro.

## Cómo podrías haberlo descubierto
Si no tienes un árbitro ni un reloj común, lo más barato es *"habla cuando quieras y repite si no te oyeron"*. Esa idea mínima es **ALOHA puro**. Al medir su rendimiento se descubre que es malo porque **cualquier solapamiento parcial** destruye las dos tramas. La pregunta natural es: *¿y si al menos las colisiones fueran "o nada, o totales"?* Eso se consigue **sincronizando los inicios de trama** con ranuras fijas: ALOHA **ranurado**. Es el patrón habitual en redes: una idea sencilla y una pequeña restricción extra que duplica el rendimiento.

## Depende de
- [[Redes/ARC_Tema_2/Conceptos/Subcapa MAC\|Subcapa MAC]]: ALOHA es un protocolo de acceso múltiple de asignación dinámica.

## Permite entender
- [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]]: evolución natural de ALOHA cuando se puede **escuchar el canal** antes de transmitir.
- Por qué una pequeña restricción (ranuras sincronizadas) puede **duplicar** la eficiencia de un protocolo.

## Ejemplo
> [!example]
> La red original ALOHANET (p. 7) conectaba por radio terminales en varias islas de Hawaii con el computador central del campus en Honolulu. No había cable entre islas ni posibilidad práctica de un árbitro común; cualquier estación emitía su trama cuando el usuario pulsaba *enter* y, si no llegaba acuse, la reenviaba.

## Errores comunes
> [!warning]
> **ALOHA puro no es *simplex***: hay sentido de ida (trama) y vuelta (acuse implícito via respuesta de la central). Confundirlo con *"no hay retorno"* es un error típico (p. 8).

> [!warning]
> La **eficiencia** citada (18 % puro, 37 % ranurado) es un **máximo teórico** en un modelo ideal; no "la velocidad de ALOHA en kbps".

> [!warning]
> ALOHA **no escucha el canal antes de transmitir** (eso ya es [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA]]).

## Autoevaluación
> [!question]- ¿Por qué ALOHA ranurado dobla la eficiencia de ALOHA puro?
> Porque obliga a que las transmisiones comiencen solo en los **límites de ranura**. Así, dos tramas que coinciden en el tiempo o chocan completamente o no chocan nada: desaparecen los **solapamientos parciales**, que es lo que estropeaba más tramas en el caso puro (p. 9).

> [!question]- ¿Qué requisito extra pide ALOHA ranurado respecto al puro?
> Un **reloj común**: todas las estaciones tienen que estar sincronizadas con los inicios de ranura, señalados por un *pip* periódico desde una estación especial (p. 9).

## Contraste
> [!success] Verificado
> El origen (Abramson, Hawaii, 1970), la versión ranurada de Roberts (1972) y las eficiencias ~18 %/~37 % coinciden con Wikipedia (*ALOHAnet*, *Slotted ALOHA*). No se han detectado discrepancias.

## Fuentes
- [[Redes/ARC_Tema_2/Fuente - ARC_Tema_2\|Fuente - ARC_Tema_2]], p. 6-9

## Mis notas
