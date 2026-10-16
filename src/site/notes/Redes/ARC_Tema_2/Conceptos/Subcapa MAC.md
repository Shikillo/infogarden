---
{"dg-publish":true,"permalink":"/redes/arc-tema-2/conceptos/subcapa-mac/","tags":["materia/redes","tema/protocolos"],"dg-note-properties":{"tipo":"concepto","aliases":["Media Access Control","Subcapa MAC"],"tags":["materia/redes","tema/protocolos"],"nivel":0,"fuentes":["[[Redes/ARC_Tema_2/Fuente - ARC_Tema_2]]"],"contraste":"pendiente","estado":"nuevo"}}
---

# Subcapa MAC

> [!abstract] En una frase
> Subcapa de la capa de enlace de datos que gestiona el **acceso al canal compartido** en redes de difusión, determinando cuándo una estación puede transmitir.

## ¿Qué problema resuelve?
Evitar que varias estaciones transmitan simultáneamente en un canal compartido (colisiones), y si ocurren, manejarlas para mantener eficiencia de red.

## Qué es
La **subcapa MAC** pertenece a la capa de enlace de datos. Es especialmente relevante en **LAN** y **redes inalámbricas** con enlaces de difusión; las WAN usan enlaces punto a punto salvo satélite (p. 4-6).

Características:
- **Asignación dinámica** para tráfico independiente, canal único, colisiones observables
- Protocolos: ALOHA, CSMA/CD, paso de testigo, mapa de bits
- **Colisión** detectable: si una estación lee datos distorsionados, detecta colisión (p. 12-14)

> [!example]
> Ethernet clásica usa CSMA/CD: escucha el canal, transmite si libre, detecta colisión y retransmite según retroceso exponencial (p. 12-14, 18).

## Depende de
- (raíz)

## Permite entender
- [[Redes/ARC_Tema_2/Conceptos/ALOHA\|ALOHA]] / [[CSMA/CD\|CSMA/CD]] / [[Redes/ARC_Tema_2/Conceptos/Ethernet\|Ethernet]]: protocolos específicos

## Errores comunes
> [!warning]
> MAC ≠ todo el enlace de datos; es solo la parte de acceso al medio. La parte de enlace también incluye control de errores y direccionamiento (LLC / IEEE 802.2).

## Autoevaluación
> [!question]- ¿Por qué el protocolo MAC es especialmente importante en LAN y comunicación inalámbrica?
> Porque usan **enlaces de difusión** (canal compartido); sin MAC, múltiples estaciones transmitirían simultáneamente, provocando colisiones constantes (p. 4-6).

## Contraste
*(pendiente)*

## Fuentes
- [[Redes/ARC_Tema_2/Fuente - ARC_Tema_2\|Fuente - ARC_Tema_2]], p. 3-6, 12-14, 18

## Mis notas
