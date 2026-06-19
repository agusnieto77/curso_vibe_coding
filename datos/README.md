# Datos de ejemplo

Este es el **corpus de trabajo del curso**. No es un dataset real: son datos **sintéticos**, inventados para enseñar, aunque inspirados en un terreno que conozco bien —la prensa y la conflictividad obrera—. Los armé así a propósito: prefiero que practiquemos sobre algo parecido a una fuente de verdad y no sobre `iris` o `mtcars`, que no le dicen nada a quien viene de las Humanidades.

> ⚠️ **Importante:** los diarios, las fechas y las noticias son ficticios. Sirven para aprender el método, no para citar como fuente.

## Qué hay acá

| Archivo / carpeta | Qué es | Dónde se usa |
|---|---|---|
| `notas_prensa.csv` | Corpus principal: ~22 notas de prensa sobre un conflicto portuario | Sesiones 5 y 6 |
| `textos/nota_ejemplo.txt` | Una sola nota en texto plano | Sesión 3 |
| `crudos/` | Archivos "sucios", con nombres y formato desprolijos | Sesión 4 |

## Diccionario de `notas_prensa.csv`

| Columna | Tipo | Descripción |
|---|---|---|
| `id` | texto | Identificador de la nota (`n01`, `n02`, …) |
| `fecha` | fecha (`AAAA-MM-DD`) | Día de publicación |
| `diario` | texto | Nombre del diario (ficticio) |
| `seccion` | texto | Sección del diario (Gremiales, Política, Locales) |
| `titular` | texto | Título de la nota |
| `texto` | texto | Cuerpo breve de la nota |

La idea es que este corpus cuente un arco: tensión → asamblea → paro → negociación → acuerdo. Cuando en la sesión 5 cuentes palabras o busques términos, vas a ver ese relato aparecer en los números. Eso es análisis de texto: hacer que la fuente hable a otra escala.
