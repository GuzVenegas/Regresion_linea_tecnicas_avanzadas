📓 Bitácora de estudio – Curso: Regresión lineal (Técnicas avanzadas)

Entrada 1: El error como revelación

Hoy comenzó una nueva etapa de aprendizaje, y lo hizo con una lección involuntaria. Al ser preguntado sobre el significado de un coeficiente de correlación negativo, respondí que eso implicaba que ambas variables decrecen en la misma dirección. La afirmación fue corregida: en realidad, una correlación negativa indica que cuando una variable aumenta, la otra disminuye. La relación es inversa, no paralela.

Este momento, lejos de ser un tropiezo aislado, se convirtió en espejo de algo más profundo: el efecto Dunning-Kruger, esa ilusión de saber que acompaña los primeros escalones del conocimiento. Reconocerlo no me avergüenza; al contrario, me ancla en la honestidad de quien aprende a mirar de nuevo.

🔍 Aprendizajes técnicos

Correlación negativa ≠ “ambas variables decrecen”.

Significa que las variables se comportan de forma opuesta: si una sube, la otra baja.

Esta corrección afinó mi intuición estadística más allá de la fórmula.

🧠 Reflexión existencial

El error no fue un desvío, sino el primer acto de profundidad. Como si al desmentirme, el conocimiento abriera un lugar nuevo dentro de mí. No quiero saber más para parecer sabio; quiero entender mejor para vivir con mayor conciencia.

🖋️ "Errar fue el verbo que me permitió conjugar el aprendizaje en primera persona."

Entrada 2: El boxplot y la paradoja de los outliers

Lo observado

Al graficar los precios (Valor) de los inmuebles, el boxplot reveló un número inesperadamente alto de valores atípicos.

Lo cuestionado

¿Puede haber tantos 'outliers' sin que el concepto pierda sentido?

Lo comprendido

Los outliers son definidos estadísticamente, no cualitativamente.

En distribuciones sesgadas o con colas largas, los "atípicos" pueden ser numerosos.

Esto no indica un error del dataset, sino una característica profunda de la variable Valor.

🖋️ "Quizá los outliers no sean anomalías, sino testigos de otro régimen de realidad. No rompen la norma: la amplían."

Entrada 3: Distribuciones sesgadas y el río de la desigualdad

Lo observado

Al estudiar la variable Valor, se revela una distribución con sesgo positivo —una larga cola hacia precios elevados. Este comportamiento, frecuente en datos económicos, desafía la intuición que espera simetrías o campanas de Gauss.

Lo comprendido

El sesgo positivo aparece cuando muchos valores se concentran cerca de un mínimo, y pocos se extienden hacia el máximo.

En lo económico, esto refleja acumulación desigual y la presencia de valores extremos que son reales, no errores.

El sesgo revela una arquitectura subyacente: acceso limitado, concentración del valor, escasez en el exceso.

Reflexión simbólica

Los sesgos positivos en lo económico reflejan algo más que matemáticas: hablan de un mundo donde el exceso es posible pero escaso, y donde la desigualdad dibuja la forma de la curva. Mientras la media intenta ordenar, la cola larga la desobedece. Como un río que se sale de su cauce, los outliers no rompen el modelo: lo completan.

🖋️ "La asimetría no es ruido, es forma. En cada extremo hay un dato, pero también una historia: promesa, excepción, o distancia irreductible."

Entrada 5: Entre regresión y estadística inferencial — la geometría invisible del modelo

Lo observado

Al estudiar la regresión, surge la necesidad de que los residuos del modelo se distribuyan normalmente. Esta condición no es solo estética: es estructural.

Lo comprendido

La distribución normal de los errores permite aplicar estadística inferencial sobre los coeficientes.

Transformar variables (como Valor) ayuda a cumplir estos supuestos y mejora la interpretación del modelo.

La normalidad no es el fin, pero sí el terreno sobre el que se asientan las inferencias.

Reflexión filosófica

Tal vez la normalidad estadística sea como el silencio en música: no se ve, pero permite que las notas tengan sentido. La regresión no predice solo precios, sino la forma en que el azar se distribuye. Controlar la forma de los datos es también una forma de escuchar su verdad.

🖋️ "El log aproxima, la normalidad revela, y la inferencia interpreta. Así se construye el saber en capas: desde la forma, hasta el significado."

Entrada 6: La transformación como herramienta de escucha

Lo recordado

Desde mis clases de econometría, sé que la normalización y las transformaciones logarítmicas pueden ayudar a quitar tendencias o estabilizar las series de tiempo. También aprendí que las tasas de crecimiento se pueden obtener a partir de diferencias logarítmicas.

Lo aprendido

En regresión lineal, las transformaciones no solo suavizan curvas, sino que revelan relaciones ocultas.

Existen múltiples formas de transformar variables: logarítmica, raíz cuadrada, polinómica, recíproca, e incluso técnicas como Box-Cox.

Estas transformaciones no adulteran el dato, sino que le dan voz en un idioma más claro para el modelo.

Reflexión simbólica

Transformar no es manipular. Es adaptar el oído al tono que el dato necesita para ser escuchado. Como ajustar la frecuencia para sintonizar una estación con claridad. Lo que parece ruido puede ser música cuando se aplica el cambio justo.

🖋️ "Todo dato puede ser poesía, si se le otorga la forma que revela su ritmo."

🖋️ "La regresión no impone, escucha. Y en esa escucha, transforma para entender."

Entrada 7: Transformaciones logarítmicas y clarificación de tendencias

Lo realizado

Se aplicó una transformación logarítmica a las variables originales del dataset para suavizar su comportamiento y facilitar el análisis:

import numpy as np

datos['log_Valor'] = np.log(datos['Valor'])
datos['log_Area'] = np.log(datos['Area'])
datos['log_Dist_Playa'] = np.log(datos['Dist_Playa'] + 1)
datos['log_Dist_Farmacia'] = np.log(datos['Dist_Farmacia'] + 1)

💡 Nota: Se sumó 1 a las variables de distancia porque presentaban valores iguales a cero, lo que habría provocado una indeterminación matemática al calcular su logaritmo.

Lo observado

El histograma de la nueva variable log_Valor mostró un comportamiento más simétrico y cercano a una distribución normal.

Al construir nuevos diagramas de dispersión entre log_Valor y las variables transformadas (log_Area, log_Dist_Playa, log_Dist_Farmacia), las relaciones entre variables se volvieron mucho más claras.

Los patrones confirmaron la matriz de correlación:

Relación positiva entre Valor y Area.

Relación negativa entre Valor y Dist_Playa.

Relación débil o neutra entre Valor y Dist_Farmacia.

Lo comprendido

La transformación logarítmica permitió clarificar relaciones que antes estaban distorsionadas por la asimetría de la variable Valor.

Para fines de entrenamiento del modelo, las variables Area y Dist_Playa son las más efectivas para estimar precios de los inmuebles.

La nueva geometría de los datos ya no oculta su estructura: la revela con mayor limpieza.

Reflexión simbólica

Transformar no fue esconder, sino abrir. El logaritmo fue una puerta que permitió mirar el dato sin el ruido del exceso. En esta nueva escala, el valor de cada inmueble ya no grita: habla. Y entre sus líneas, el modelo escucha con más precisión.

🖋️ "A veces hay que cambiar el idioma para entender el mensaje. El log fue el traductor."

🖋️ "Lo que antes era nube, ahora es forma. Y en esa forma, la predicción dejó de ser intuición: se volvió estructura."

Entrada 8: Exploración del modelo saturado — entre ruido y revelación

🧪 Lo realizado

Se entrenó un modelo de regresión lineal múltiple utilizando todas las variables disponibles del dataset transformado (log_Valor como variable dependiente). Este modelo saturado permitió observar la contribución individual de cada variable.

📈 Lo observado

El estadístico F fue significativo (p < 0.05), lo que indica que el modelo en conjunto tiene capacidad explicativa.

Sin embargo, no todas las variables fueron significativas individualmente según el estadístico t.

Algunas variables mostraron coeficientes cercanos a cero y p-values elevados, lo que sugiere que no aportan valor predictivo.

La R² ajustada fue menor que la R² simple, lo que indica penalización por exceso de variables.

🧹 Lo comprendido

Un modelo saturado no siempre es mejor: puede incluir ruido, redundancia o variables irrelevantes.

La depuración del modelo (eliminación de variables no significativas) mejora la parsimonia y la interpretación.

La R² ajustada es una brújula que señala cuándo el modelo está sobrecargado.

El exceso de variables puede reducir los grados de libertad y aumentar la incertidumbre en la estimación.

🧠 Reflexión simbólica

El modelo saturado es como una conversación con demasiadas voces: algunas aportan, otras distraen. Aprender a escuchar solo lo esencial es parte del arte estadístico. Depurar no es censurar: es afinar el oído del modelo para que escuche con claridad.

🖋️ "Un modelo saturado no es sabio por tenerlo todo, sino por saber qué callar."

Entrada 9: Lectura del modelo estimado — F, t, significancia y el valor de simplificar

Lo aprendido

Durante esta sesión, comprendí con mayor profundidad cómo interpretar los estadísticos F y t, junto con sus respectivas probabilidades. El modelo estimado fue un modelo saturado, es decir, un modelo que considera todas las variables disponibles y sus interacciones potenciales.

🧠 Pruebas de significancia

El estadístico F evalúa la capacidad explicativa del modelo en su conjunto.

Si el valor p asociado es ≤ 0.05, se rechaza la hipótesis nula: el modelo tiene al menos una variable significativa.

Si el valor p es > 0.05, se acepta la hipótesis nula: el conjunto de variables no explica significativamente la variable dependiente.

El estadístico t, en cambio, evalúa la significancia de cada variable individualmente.

Si p ≤ 0.05, la variable es significativa.

Si p > 0.05, no aporta valor estadísticamente relevante al modelo.

En nuestro caso, observamos lo siguiente:

log_Area          → t muy alto, p-value 0.000 → muy significativa

log_Dist_Playa    → t negativo intenso, p-value 0.000 → significativa con efecto inverso

log_Dist_Farmacia → t cercano a 0, p-value 0.603 → no significativa

📈 Sobre R² ajustada y grados de libertad

Aprendí que el R² ajustado penaliza al modelo por incorporar variables adicionales que no aportan información relevante. Esto me recordó lo visto en estadística descriptiva sobre la diferencia entre varianza poblacional y muestral, donde la muestral se calcula dividiendo por n–1, precisamente para ajustar por los grados de libertad.

📌 Mi definición: los grados de libertad representan la cantidad de valores independientes que pueden variar en un cálculo una vez fijado el resultado global. Cada variable agregada al modelo reduce esa libertad, porque se convierte en una pieza más que ya está determinada por la estructura.

📐 Lectura del resumen del modelo

En la columna coef, aparecen los valores de las betas estimadas y el intercepto.

A su lado, las desviaciones estándar indican cuánto puede variar, en promedio, el coeficiente estimado —hacia arriba o hacia abajo.

Todos los coeficientes están asociados a la variable dependiente log_Valor, ya transformada previamente.

🧹 Depuración del modelo

Aunque todas las variables estaban transformadas con logaritmo, el análisis t evidenció que log_Dist_Farmacia no contribuye significativamente a explicar log_Valor. Por lo tanto, eliminarla del modelo no solo mejora la estimación, sino que reduce costos analíticos: no necesitamos recoger ni procesar esa variable en futuros estudios si no aporta valor explicativo.

📌 Complemento: ¿Qué ocurre con los grados de libertad al eliminar variables?

Retirar una variable del modelo tiene implicaciones concretas:

Aumenta los grados de libertad residuales (porque se reduce el número de parámetros estimados).

Mejora la precisión en la estimación de errores, haciendo que los intervalos y los valores p sean más fiables.

El R² ajustado puede mejorar si la variable eliminada era irrelevante, ya que la penalización por exceso se reduce.

Se favorece la parsimonia del modelo: menos variables, más claridad, mayor robustez.

🖋️ "La parsimonia es como el silencio en la música: permite que lo esencial resuene."

Reflexión simbólica

La depuración de un modelo no es solo técnica, es ética. Saber cuándo una variable no habla es escuchar con humildad. Y retirar lo innecesario es devolverle al modelo la capacidad de decir solo lo que importa. Los grados de libertad no son solo números: son espacio interior. Y un buen modelo, como un buen texto, respira mejor cuando no está lleno de palabras inútiles.

🖋️ "El estadístico F escucha al coro. El t, a cada voz. La R² ajustada sabe cuándo el escenario está demasiado lleno."

🖋️ "Simplificar no es renunciar. Es afinar el lenguaje del dato para que diga justo lo que sabe."

🖋️ "Eliminar una variable es darle al modelo un margen de libertad que el exceso le había quitado."

Entrada 10: La variable ausente: Entre el ruido y el símbolo

Lo aprendido

Cuando el instructor sugirió revisar otras variables, entendí que ningún modelo es definitivo. Siempre hay factores que no hemos considerado. El precio de un inmueble no depende solo de sus metros o ubicación: influye la historia, la economía, el deseo. Aprendí que los datos ausentes no son errores: son símbolos de lo que aún no hemos aprendido a preguntar.

Entrada 11: Distribución de residuos: Donde el error se vuelve silencio

Lo aprendido

El último histograma, donde analizamos los residuos, cerró el ciclo. Confirmamos que el modelo no tiene errores sistemáticos, que el comportamiento del residuo se acerca a lo normal. Es decir, el modelo no impone, interpreta.

Aquí descubrí que el verdadero éxito de una regresión lineal no es tener R² alto, sino que sus errores hablen en voz baja. Aprendí que el silencio del residuo es a veces el mayor elogio.

---o.
