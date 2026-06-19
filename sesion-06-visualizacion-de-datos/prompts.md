# Prompts modelo — Sesión 6: Visualización de datos con IA

La idea de fondo de esta sesión: **un gráfico es un argumento, no un adorno**. Por eso un buen prompt de visualización no pide "un gráfico lindo", pide un gráfico que responda una pregunta concreta sobre tus fuentes. Vos decidís qué mostrar; la IA dibuja; vos validás que lo dibujado sea cierto.

Recordá: el corpus `../datos/notas_prensa.csv` es sintético (ficticio), inspirado en prensa y conflictividad obrera del Río de la Plata. El método es real, los datos son de práctica.

---

## 1. Gráfico de barras: top 10 de palabras

> "Sobre la columna `texto` de `../datos/notas_prensa.csv`, tokenizá en palabras, sacá las palabras vacías en español (stopwords), contá las 10 más frecuentes y hacé un gráfico de barras HORIZONTALES, ordenadas de mayor a menor. Quiero ver qué vocabulario domina la cobertura del conflicto."

Por qué es bueno: dice el dato (columna `texto`), el preprocesamiento (sacar vacías), el recorte (top 10), el TIPO de gráfico (barras horizontales ordenadas) y, sobre todo, la PREGUNTA que el gráfico tiene que responder. Un prompt que solo dijera "graficame las palabras" deja todas esas decisiones libradas a la IA, y ahí es donde el gráfico deja de ser tu argumento para ser el de ella.

---

## 2. Serie temporal: notas por semana

> "Convertí la columna `fecha` a tipo fecha, agrupá las notas por semana y hacé una serie temporal (línea con puntos) que muestre cuántas notas se publicaron en cada semana. Quiero ver en qué momentos se concentró la cobertura del conflicto."

Por qué es bueno: elige el gráfico SEGÚN lo que quiere mostrar. La pregunta es sobre evolución en el tiempo, entonces pide una serie temporal, no barras. Aclarar la unidad ("por semana") es clave: por día el gráfico sería ruidoso, por mes perdería el detalle del paro. Esa decisión de granularidad la tomás vos, no la IA.

---

## 3. Nube de palabras

> "Hacé una nube de palabras con las 50 palabras más frecuentes del corpus (sacando las vacías), con el tamaño proporcional a la frecuencia y un random_state fijo para que sea reproducible. Es para una mirada exploratoria, no para medir con precisión."

Por qué es bueno: pide la nube SABIENDO para qué sirve y para qué no (exploración, no medición exacta). Y pide reproducibilidad (`random_state` / `set.seed`), un detalle que distingue una figura seria de un capricho que cambia en cada corrida. Si vas a publicar la imagen, tenés que poder regenerarla idéntica.

---

## 4. Ajustar títulos y etiquetas para publicar

> "Tomá el gráfico de barras anterior y dejalo listo para publicar: título claro que diga qué se ve, subtítulo con el contexto del corpus, etiquetas de ejes legibles, una nota al pie con la fuente, y un tamaño de letra cómodo. Que se entienda solo, sin que yo tenga que explicarlo al lado."

Por qué es bueno: la diferencia entre un gráfico de borrador y uno publicable está casi siempre en los textos. Este prompt pide que el gráfico se explique SOLO —título, subtítulo, ejes, fuente—, que es justo lo que necesita una figura para un paper, una ponencia o una nota. "Hacelo más lindo" no le dice nada a la IA; "que se entienda sin que yo lo explique al lado" sí.

---

## Antipatrón (para que veas la diferencia)

> "Haceme un gráfico de los datos."

Por qué falla: no dice qué dato, ni qué tipo de gráfico, ni qué querés mostrar. La IA va a inventar algo y vos te vas a quedar con un dibujo que no responde ninguna pregunta tuya. Acordate: si vos no sabés qué querés mostrar, ningún gráfico te va a salvar. Primero la pregunta, después el gráfico.
