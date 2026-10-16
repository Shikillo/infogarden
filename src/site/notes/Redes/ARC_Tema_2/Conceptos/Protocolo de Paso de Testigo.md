---
{"dg-publish":true,"permalink":"/redes/arc-tema-2/conceptos/protocolo-de-paso-de-testigo/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Token Ring","Token Bus","Paso de Testigo","Token Passing"],"tags":["materia/redes","tema/protocolos"],"nivel":1,"fuentes":["[[Redes/ARC_Tema_2/Fuente - ARC_Tema_2]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Protocolo de Paso de Testigo

> [!abstract] En una frase
> Protocolo **libre de colisiones** en el que un mensaje de control llamado **testigo (*token*)** circula entre las estaciones en un orden prefijado; **solo la estación que posee el testigo puede transmitir**.

## ¿Qué problema resuelve?
Los protocolos tipo [[Redes/ARC_Tema_2/Conceptos/ALOHA\|ALOHA]] o [[Redes/ARC_Tema_2/Conceptos/CSMA_CD\|CSMA/CD]] permiten que dos estaciones empiecen a emitir a la vez y colisionen, con la pérdida de ancho de banda que señala el material (p. 15): **las colisiones aumentan el tiempo para enviar una trama** y resultan **mal ajustadas al tráfico en tiempo real** (VoIP, vídeo, teleconferencia). El paso de testigo elimina las colisiones por diseño: nunca hay dos estaciones autorizadas a transmitir al mismo tiempo.

## Qué es
Según el material (p. 17): **"El mensaje (llamado testigo) se pasa a la siguiente estación en el orden predefinido. Los protocolos Token Ring o Token Bus funcionan de la misma manera"**. El testigo recorre las estaciones; quien lo recibe puede enviar su trama, y después pasa el testigo a la siguiente.

Características que indica el material (p. 17):
- Las estaciones se organizan en un **orden predefinido** (anillo o bus lógico).
- Solo quien **posee el testigo** tiene derecho a transmitir ⇒ **no hay colisiones**.
- Variantes citadas: **Token Ring** (anillo físico) y **Token Bus** (orden lógico sobre bus).
- Si el testigo **no se elimina de la circulación**, "terminará allí para siempre": es un fallo típico del protocolo. Lo normal es que lo retire la **estación receptora** o la **emisora** (p. 17).

> [!example]
> En un Token Ring con 4 estaciones (A→B→C→D→A), si B tiene algo que enviar espera a recibir el testigo; cuando lo recibe transmite su trama, y a continuación lo entrega a C. Si nadie quiere transmitir, el testigo sigue dando vueltas, un consumo mínimo del canal (p. 17).

## Depende de
- [[Redes/ARC_Tema_2/Conceptos/Subcapa MAC\|Subcapa MAC]]: es un **protocolo de acceso al medio** libre de colisiones (p. 15, 17).

## Permite entender
- Por qué en entornos de **tráfico en tiempo real** (VoIP, vídeo) resultaba más predecible que CSMA/CD: en paso de testigo el **tiempo máximo de espera está acotado** por el tiempo que tarda el testigo en completar una vuelta (p. 15).
- Por qué, aun así, acabó perdiendo frente a **[[Redes/ARC_Tema_2/Conceptos/Ethernet\|Ethernet]]**: la Ethernet conmutada con switches eliminó las colisiones por otro camino (p. 29).

## Errores comunes
> [!warning]
> El "testigo" **no es la trama de datos**: es un mensaje de control muy breve que concede el turno. Confundirlo con la trama lleva a pensar erróneamente que el "testigo" se pierde si se envían muchos datos: lo que circula siempre es el testigo, lo demás son las tramas que la estación con testigo transmite (p. 17).

## Autoevaluación
> [!question]- ¿Por qué el material dice que el paso de testigo encaja mejor que CSMA/CD con VoIP y vídeo?
> Porque en estos tráficos importa un **retardo máximo acotado**. CSMA/CD puede sufrir colisiones y reintentos aleatorios, lo que genera latencias impredecibles. En paso de testigo el peor caso es el tiempo de una vuelta completa del testigo, que es un valor conocido (p. 15, 17).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_2/Fuente - ARC_Tema_2\|Fuente - ARC_Tema_2]], p. 15, 17

## Mis notas
