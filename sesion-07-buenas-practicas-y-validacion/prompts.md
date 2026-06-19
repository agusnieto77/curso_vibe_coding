# Prompts modelo — Sesión 7: Buenas prácticas y validación

Estos son los prompts que de verdad importan en todo el curso. No sirven para que
la IA HAGA más, sino para que vos CONTROLES lo que hace. La IA es la herramienta;
el rigor lo ponés vos. Acá van los pedidos que te conviene tener siempre a mano.

---

## 1. Pedirle a la IA que revise su propio código y diga qué puede fallar

> "Revisá este código en R/Python que cuenta cuántas veces aparece la palabra
> *paro* en una columna de textos. Antes de que lo use, decime QUÉ puede salir
> mal: ¿cuenta la palabra completa o también la cuenta cuando está dentro de otra
> palabra como *amparo* o *disparo*? Mostrame un caso concreto donde fallaría."

Por qué es bueno: no le pedís que escriba más, le pedís que se AUTOCRITIQUE con un
caso de prueba concreto. Forzar un contraejemplo ("amparo", "disparo") es lo que
saca a la luz el error de subcadena. Igual, ojo: que la IA diga "está todo bien"
no es prueba de nada; el chequeo final lo hacés vos sobre tus datos.

---

## 2. Preguntarle si una función existe DE VERDAD

> "Me sugeriste usar la función `str_count_words()` en R (o el método
> `.str.count_words()` en pandas). ¿Esa función existe realmente en el paquete, o
> la estás inventando? Si existe, pasame el enlace a la documentación oficial. Si
> no existe, decime cuál es la forma real de hacerlo."

Por qué es bueno: ataca de frente la *alucinación*. Pedir el enlace a la
documentación oficial es un filtro brutal: si la función es inventada, no hay doc
que mostrar. De todos modos, no te quedes con la respuesta: verificá vos con
`?funcion` / `exists()` en R, o `help()` / `hasattr()` en Python.

---

## 3. Pedir un control para validar el resultado

> "Tengo este conteo de la palabra *paro* sobre un corpus chico de 22 notas de
> prensa. Escribime un código que me deje VALIDAR el resultado a mano: que me
> muestre cada texto donde aparece *paro* y resalte el fragmento exacto que contó,
> así puedo revisar con mis ojos si cada coincidencia es realmente la palabra que
> busco."

Por qué es bueno: convierte un número solitario en algo AUDITABLE. Pedir que
resalte el fragmento contado, sobre un corpus chico, es la mejor forma de validar
a mano. La validación humana caso por caso es justo lo que esta sesión defiende.

---

## 4. Pedir que documente el script para que sea reproducible

> "Documentá este script para que sea reproducible. Agregá comentarios en español
> que expliquen qué hace cada parte, una cabecera que diga QUÉ datos usa (el
> archivo `../datos/notas_prensa.csv`, corpus sintético), CÓMO se corre y qué
> librerías necesita, y una línea final que imprima las versiones de R/Python y de
> los paquetes para dejar registro."

Por qué es bueno: la reproducibilidad no se improvisa al final, se pide explícito.
Nombrar las tres cosas (qué datos, cómo correr, qué versiones) hace que la IA
genere documentación útil de verdad y no comentarios decorativos.

---

## 5. Pedirle que compare dos versiones del mismo cálculo

> "Tengo dos formas de contar la palabra *paro*: una busca la cadena suelta y otra
> usa límites de palabra (`\bparo\b`). Escribime un código que corra las dos sobre
> el mismo corpus y me muestre los dos totales y la diferencia entre ellos, en una
> tabla."

Por qué es bueno: la comparación es prueba, no opinión. Ver la versión ingenua y
la corregida lado a lado, con la diferencia explícita, te muestra el tamaño real
del error en TUS datos. Un total solo no dice nada; dos totales comparados, sí.

---

## 6. Un mal prompt (para que veas el contraste)

> "Contá las palabras del corpus." ❌

Por qué falla: es vago hasta la inutilidad. ¿Qué palabra? ¿Palabra completa o
subcadena? ¿Con mayúsculas o sin? ¿En qué columna? La IA va a rellenar todos esos
huecos con suposiciones que NO te va a contar, y vos vas a recibir un número sin
saber qué cuenta. Un prompt vago no te da menos control: te da la ILUSIÓN de un
resultado mientras la herramienta decide sola lo que vos deberías estar dirigiendo.
