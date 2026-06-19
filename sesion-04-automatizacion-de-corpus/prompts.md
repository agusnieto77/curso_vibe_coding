# Prompts modelo — Sesión 4: Automatización sobre un corpus

La idea de estos prompts es siempre la misma: vos sabés QUÉ querés y POR QUÉ;
la IA escribe el código. Cuanto más claro le digas sobre qué archivos trabajar,
qué tiene que hacer y qué NO debe tocar, mejor te va a salir. Un prompt vago te
devuelve código vago.

---

## 1. Limpiar HTML y espacios sobre TODA una carpeta

> "Tengo una carpeta `../datos/crudos/` con varios archivos `.txt` de notas de
> prensa que están sucios. Escribime un script que recorra TODOS los `.txt` de
> esa carpeta y, a cada uno, le saque los restos de HTML (etiquetas como `<p>`
> y entidades como `&nbsp;` y `&amp;`), colapse los espacios de más en uno solo
> y elimine las líneas vacías que sobran. Comentá el código en español."

**Por qué es bueno:** dice la carpeta exacta, enumera la basura concreta a sacar
y deja claro que es sobre TODOS los archivos, no uno. El vago ("limpiame estos
textos") te obliga a tres idas y vueltas para que la IA adivine qué es "limpiar".

---

## 2. Renombrar en lote a un patrón consistente

> "Cuando guardes los archivos limpios, renombralos con el patrón `nota_01.txt`,
> `nota_02.txt`, `nota_03.txt`, etcétera, con dos dígitos y cero a la izquierda,
> respetando el orden alfabético de los nombres originales."

**Por qué es bueno:** define el patrón con un ejemplo concreto (`nota_01.txt`) y
aclara el detalle que casi siempre se olvida —el cero a la izquierda— que es lo
que hace que `nota_10` no quede antes que `nota_2` al ordenar.

---

## 3. Convertir varios .txt a un único CSV

> "Juntá todos los `.txt` limpios en un solo archivo CSV con dos columnas: `id`
> (el nombre del archivo) y `texto` (el contenido completo de la nota en una sola
> línea). Que el CSV tenga encabezado y use codificación UTF-8."

**Por qué es bueno:** especifica la estructura exacta de salida (las dos columnas
y qué va en cada una) y dos detalles que evitan dolores de cabeza después: el
encabezado y el UTF-8 para que no se rompan los acentos.

---

## 4. No pisar los originales (la red de seguridad)

> "Importante: el script NO debe modificar ni borrar los archivos originales de
> `../datos/crudos/`. Que guarde todo lo limpio en una carpeta nueva `./salida/`
> que cree desde el código si no existe."

**Por qué es bueno:** es la instrucción que te salva. Limpiar es destructivo; si
la IA escribe sobre los originales y algo sale mal, perdiste la fuente. Pedir
explícitamente carpeta de salida separada te garantiza que siempre podés volver
atrás y comparar.

---

## 5. Validar el resultado (cerrar el círculo)

> "Después de limpiar, mostrame una comparación: cuántos restos de HTML quedaban
> en cada archivo original y cuántos quedan en cada archivo limpio. Quiero
> confirmar a ojo que la limpieza funcionó."

**Por qué es bueno:** automatizar sin validar es confiar a ciegas, y la IA se
equivoca. Pedirle el chequeo en el mismo paso te da la prueba de que el trabajo
salió bien, en vez de asumirlo.

---

## 6. El prompt vago (lo que NO conviene hacer)

> "Limpiá estos archivos y dejalos prolijos."

**Por qué falla:** no dice qué carpeta, qué es "limpiar", qué archivos, ni dónde
guardar. La IA va a inventar un criterio cualquiera y, peor, puede pisar tus
originales sin avisar. Acordate: vos dirigís, la IA ejecuta. Si no le das el
rumbo, te lleva a cualquier lado.
