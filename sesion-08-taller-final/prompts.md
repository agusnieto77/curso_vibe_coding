# Prompts del taller final — andamios para tu proyecto

Estos no son prompts cerrados para copiar y pegar tal cual. Son **andamios**: plantillas con huecos (`[entre corchetes]`) que tenés que rellenar con TU tema, TUS datos y TU pregunta. Un buen prompt es como una buena consigna: cuanto más contexto le das a la IA, menos se inventa y mejor te responde.

Recordá la regla de oro del curso: la IA ejecuta, **vos dirigís y validás**. Si el resultado no te cierra, no es que vos no entendés: es que el prompt todavía no era lo bastante claro, o la IA alucinó. Volvé, precisá, y pedí de nuevo.

---

## 1. Definir la pregunta de investigación

> "Soy [tu rol: historiadora, estudiante de Letras, investigador del CONICET...] y trabajo con [tu tema: prensa obrera, actas municipales, correspondencia...]. Tengo [describí tus datos: un CSV con X notas, una carpeta con Y textos...]. Quiero formular una pregunta de investigación concreta y abordable con análisis de datos sencillo. Proponeme tres preguntas posibles, de la más amplia a la más acotada, y explicame qué necesitaría cada una para responderse."

**Por qué funciona:** le das rol, tema y materia prima, y pedís OPCIONES en vez de una respuesta cerrada. Así la IA te ayuda a pensar la pregunta en lugar de imponerte una. Un prompt vago como *"dame una buena pregunta de investigación"* devuelve obviedades que no sirven para nada.

---

## 2. Describir y entender los datos

> "Tengo un archivo `[nombre.csv]` con estas columnas: [pegá los nombres de las columnas y una fila de ejemplo]. Son datos sobre [qué representan]. Antes de analizarlos, ayudame a entenderlos: ¿qué tipo de dato es cada columna, qué problemas típicos de calidad debería revisar y qué preguntas se pueden responder con esta estructura?"

**Por qué funciona:** le mostrás la estructura REAL (columnas y un ejemplo) en vez de describirla de memoria. La IA no puede ver tu archivo: si no se lo pegás, adivina. Pegarle una fila concreta es la diferencia entre una respuesta a tu medida y una genérica.

---

## 3. Armar el pipeline (cargar → limpiar → analizar)

> "Escribime código en [R con tidyverse / Python con pandas] para: (1) cargar el archivo `[ruta relativa, ej. ../datos/mi_archivo.csv]`, (2) sacar espacios sobrantes y [otros problemas que viste: HTML, mayúsculas...], y (3) contar [lo que querés medir: frecuencia de palabras / registros por categoría]. Comentá cada paso en español y, después de cada bloque, agregá una línea que me deje verificar que salió bien."

**Por qué funciona:** pedís el flujo completo en pasos numerados, fijás el lenguaje y —clave— exigís comentarios en español y una verificación por bloque. Pedir el chequeo dentro del propio prompt te ahorra confiar a ciegas. Si solo dijeras *"limpiá mis datos"*, no sabrías qué hizo ni si lo hizo bien.

---

## 4. Visualizar el resultado

> "Tengo esta tabla de resultados: [pegá las primeras filas]. Quiero un gráfico en [ggplot2 / matplotlib] que muestre [qué querés que se vea: las 10 palabras más frecuentes, la evolución por fecha...]. Que sea claro y legible: título que explique el hallazgo, ejes etiquetados y una nota al pie con la fuente. Explicame por qué este tipo de gráfico es el adecuado para estos datos."

**Por qué funciona:** un gráfico es un argumento, así que le pedís que el título comunique el HALLAZGO, no solo el nombre de la variable. Y pedir que justifique el tipo de gráfico te enseña a vos a elegir, en vez de aceptar el primero que aparezca.

---

## 5. Validar (chequear que no te están vendiendo humo)

> "Este código me dio como resultado [pegá el número o la tabla]. Ayudame a validarlo a mano: ¿qué dos o tres chequeos independientes puedo hacer para confirmar que el resultado es correcto y no un error de carga o de limpieza? Dame los pasos concretos para verificarlo yo mismo/a sobre la fuente original."

**Por qué funciona:** acá usás la IA para que te enseñe a desconfiar de la IA. En vez de pedirle que confirme su propio trabajo (lo haría con total seguridad aunque esté mal), le pedís un método para que VOS controles contra la fuente. Ese es el corazón del rigor humanístico.

---

## 6. Presentar y documentar el proyecto

> "Terminé un análisis sobre [tu tema] usando [tus datos]. Mi pregunta era [pregunta] y encontré [hallazgo principal]. Ayudame a redactar una conclusión breve y honesta para cerrar el notebook: que responda la pregunta, mencione la evidencia concreta y reconozca los límites de los datos. Tono claro, sin exagerar lo que muestran los números."

**Por qué funciona:** le das pregunta, datos y hallazgo, y pedís explícitamente honestidad y reconocimiento de límites. Así evitás la conclusión inflada y vendedora que la IA tiende a escribir por defecto. La investigación seria también dice lo que NO pudo saber.
