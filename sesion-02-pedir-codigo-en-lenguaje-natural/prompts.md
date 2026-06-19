# Prompts modelo — Sesión 2: Cómo pedir código en lenguaje natural

La regla de oro de esta sesión: **el resultado depende de cómo preguntás**. La IA no adivina, ejecuta lo que entiende. Estos son los prompts modelo. Compará el vago con el preciso y vas a ver por qué uno falla y el otro no.

---

## 1. El pedido vago (así NO)

> "Contá cuántas notas hay."

**Por qué falla:** no dice dónde están las notas, en qué archivo, en qué formato, ni qué tenés que devolver. La IA no tiene tu contexto: o inventa un dataframe de la nada, o alucina un nombre de archivo que no existe. Un pedido sin datos es una invitación a que la IA improvise.

---

## 2. El mismo pedido, preciso (así SÍ)

> "Tengo un archivo CSV en la ruta `../datos/notas_prensa.csv`. Cada fila es una nota de prensa y la columna `id` la identifica. Escribime código en R, con tidyverse, que cargue ese CSV y me diga cuántas notas hay en total. Mostrame el número en una frase clara."

**Por qué funciona:** trae los cinco ingredientes —archivo y ruta, formato, qué representa cada fila, lenguaje y resultado esperado—. La IA no tiene que adivinar nada, así que el código corre sobre TUS datos a la primera.

---

## 3. Darle contexto de quién sos y para qué

> "Soy historiador y trabajo con prensa como fuente. Estoy aprendiendo a programar para analizar corpus de notas de diario. Necesito que el código sea simple y esté comentado en español, porque recién empiezo. A partir de ahora, cuando te pida algo, asumí ese nivel."

**Por qué es bueno:** el contexto de quién sos ajusta el tono, la complejidad y hasta el lenguaje de los comentarios. La IA que sabe que sos principiante no te tira una solución con cinco librerías raras: te explica.

---

## 4. Pedir que la IA explique el código

> "Tomá el código que me devolviste para contar las notas y explicámelo línea por línea, en castellano y sin tecnicismos, como si nunca hubiera programado. Quiero entender qué hace cada parte antes de usarlo."

**Por qué es bueno:** entender > copiar. Pedir la explicación te da el control: si no entendés el código, no podés validarlo ni detectar cuándo la IA se equivocó. La herramienta ejecuta; el criterio lo ponés vos.

---

## 5. Iterar sobre una respuesta (cambiar X)

> "Ahora, sobre el mismo código, además del total decime cuántas notas hay por diario. No me vuelvas a explicar todo: solo agregá lo nuevo."

**Por qué es bueno:** iterar es seguir la conversación, no empezar de cero. Le pedís un cambio puntual sobre lo que ya tenés. Así se trabaja de verdad con la IA: pedir, leer, ajustar, repetir.

---

## 6. Iterar cambiando el formato de salida

> "Cambiá la salida: en vez de una frase, mostrame el conteo de notas por sección en una tabla ordenada de mayor a menor."

**Por qué es bueno:** mismo dato, otra forma de verlo. Separar *qué calculás* de *cómo lo mostrás* te da flexibilidad sin reescribir la lógica. Y recordá: cualquiera sea la salida, validá el número a mano sobre el CSV antes de creerle.
