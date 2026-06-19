# Prompts modelo — Sesión 5: IA y análisis textual

Estos son los prompts que usamos en la sesión. La idea no es que los copies y pegues
sin pensar, sino que veas CÓMO se le pide bien a la IA. Un buen prompt da contexto,
dice qué columnas hay, qué herramienta usar y qué querés de vuelta. Un prompt vago te
devuelve código genérico que no corre sobre TU corpus.

---

## 1. Palabras más frecuentes (sacando palabras vacías)

> "Tengo un CSV de notas de prensa con las columnas id, fecha, diario, seccion, titular
> y texto. Quiero unir titular y texto, pasar todo a minúsculas, tokenizar, sacar una
> lista corta de palabras vacías en español (de, la, el, en, y, a, los, las, que...) y
> mostrarme el top 15 de palabras más frecuentes. En R usá tidytext; en Python usá
> pandas con re y collections.Counter. Comentá el código en español."

**Por qué es un buen prompt:** le das las columnas exactas, el orden de los pasos
(unir → minúsculas → tokenizar → sacar vacías → contar) y la herramienta. Sin eso, la
IA inventa nombres de columna que no existen y te hace perder tiempo.

---

## 2. Buscar un término y ver su contexto (en qué notas aparece)

> "Buscá la palabra 'paro' como palabra entera (que no matchee dentro de 'disparo') en
> el contenido de cada nota y devolveme una tabla con id, fecha y titular de las notas
> donde aparece. Ordenala por fecha."

**Por qué es un buen prompt:** aclarás "como palabra entera" y das el caso problemático
('disparo'). Eso obliga a usar límites de palabra (\b) en lugar de un `contains` ingenuo
que te ensuciaría los resultados.

---

## 3. Conteo de notas por sección

> "Contame cuántas notas hay por cada valor de la columna seccion, ordenadas de mayor a
> menor, y hacé un gráfico de barras horizontal."

**Por qué es un buen prompt:** es preciso sobre la columna y el orden, y pide además la
visualización. Pedir el gráfico junto con la tabla evita una segunda vuelta.

---

## 4. Pedir que explique qué es tokenizar

> "Explicame en lenguaje sencillo, con un ejemplo concreto sobre una frase en español,
> qué es tokenizar un texto y por qué lo necesito antes de contar palabras. No me des
> código todavía, solo la explicación."

**Por qué es un buen prompt:** usás la IA como tutora, no solo como generadora de código.
Pedir "sin código todavía" y "con un ejemplo concreto" te asegura entender el CONCEPTO
antes de aplicarlo. Entender primero, ejecutar después.

---

## 5. (Variación) Comparar el efecto de la lista de vacías

> "Mostrame el top 15 de palabras dos veces: una sin sacar palabras vacías y otra
> sacándolas. Poné las dos tablas lado a lado para que pueda comparar qué cambió y
> entender por qué las vacías ensucian el análisis."

**Por qué es un buen prompt:** pedís una comparación, no un resultado suelto. Ver el
"antes y después" es la mejor forma de entender PARA QUÉ sirve filtrar palabras vacías.

---

## 6. (Variación) Validar el conteo a mano

> "Elegí una palabra del top 15 y mostrame cómo verificar su frecuencia con un método
> distinto al que usaste para contar, así puedo chequear que el número está bien."

**Por qué es un buen prompt:** le pedís a la IA que te ayude a DESCONFIAR de la IA. El
rigor lo ponemos nosotros: validar a mano es parte del método, no un extra opcional.
