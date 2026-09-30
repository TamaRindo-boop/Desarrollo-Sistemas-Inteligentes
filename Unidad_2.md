## Act_2.1 Dos ejemplos de T, P y E

### Ejemplo 1: Detección de intrusos

- **T:** Detectar si una persona no autorizada entra a un lugar.
- **P:** Porcentaje de intrusos detectados correctamente.
- **E:** Videos o imágenes de cámaras de seguridad con ejemplos de entradas autorizadas y no autorizadas.

### Ejemplo 2: Detección de fraude

- **T:** Identificar si una transacción bancaria es fraudulenta.
- **P:** Porcentaje de fraudes detectados correctamente.
- **E:** Historial de transacciones bancarias clasificadas como normales o fraudulentas.

### Proyecto: Detección de URLs seguras

- **T:** Determinar si una URL es segura o maliciosa.
- **P:** Porcentaje de URLs clasificadas correctamente.
- **E:** Base de datos de URLs conocidas como seguras y maliciosas. (deteccion de tres comando de creaciones realizadas)

## Act_2.2 Tres artefactos Machine Learning

**Supervisado**: Enseñar a una computadora utilizando datos que se sabe una respuesta o respuestas conocidad. Como estudiar un ejercicio que tiene la respuesta

En correos spam y los normales. El modelo recibe correros nuevos y trata de clasificarlos.

Es cuando la computadora aprende con ejemplos que ya tienen la respuesta y utiliza lo aprendido para resolver casos nuevos.

**Sin supervisar**: Los datos no tienen una respuesta o categoria indicada de esta. La computadora analizaa los datos y busca si misma caracteristicas similares

Es cuando la computadora recibe información sin categorías establecidas y busca por sí sola cuáles datos se parecen para formar grupos o descubrir patrones.


**Por refuerzo**: Una computadora aprende mediante pruebas y errores. Una accion con recompensa. Eso quiere decir que aprende con acciones que le ayudan 

Es cuando la computadora aprende experimentando, tomando decisiones y observando si obtiene una recompensa o una penalización por lo que hizo.


## Act_2.3 Glosario (Todo con base de Machine Learning)


1. Pandas
Esta diseñado especificamente para la manipulacion y el analisis de datos en el penguaje Python. Permite cargar, limpiar, explorar y transformar datos tabulares antes de entrenar cualquier modelo

2. Matplotlib
Una biblioteca de Python diseñada para crear visualizaciones de datos de alta calidad y evolucionado para convertiirse en una de las herramienras comunidad de visualización más utilizadas en la comunidad científica y de datos.

3. Scikit-learn (Investigar que datos de prueba maneja)
Optimiza la inteligencia artificial y el modelado estadistico con ML y una interfaz coherente

-Conjuntos de datos pequeños (Toy Datasets)
-Conjuntos de datos del mundo rela (Real-world Datasets)
-Generadores de datos sinteticos

3. Google Colab
Es un laboratorio de programacion accesible para todo el mundo, directamente desde el navegador. 
En realidad, Colab es una versión en la nube de Jupyter Notebook integrada en el ecosistema de Google.

4. Arbol de decision
Es un algoritmo de aprendizaje automatico superviisado que predice resultados dividiendo los datos en partes mas pequeñas mediante preguntas de tipo si o no. En ML funciona con datos, analizan caracteristicaas para tomar decisiones y predecir resultados

5. Matriz de confusion
Es un metodo de visualizacion parra los resultados del algoritmmo clasificador.  Ayuda a evaluar el rendimiento del modelo de clasificación en el aprendizaje automático comparando los valores previstos con los valores reales de un conjunto de datos. 

Estas matrices se utilizan con frecuencia para evaluar los resultados predictivos en machine learning y ciencia de datos, ya sea para propósitos académicos o comerciales.


6. Sobreajuste
Es un error de Machine Learning que ocurre cuando un modelo aprende demasiado los datos de entrenamiento y memoriza detalles específicos o ruido en lugar de entender la regla general

------
Falso Positivo: Es un resultado que indica de forma erronea la presencia de una condiccion, enfermedad o evento que en realisdad no existe

Falso negativo: Es un resultado de una prueba o diagnostico que indica de forma equivocada la ausencia de una afeccion, enfermedad o estado cuando en realidad si esta presente


## Act_2.4  Definiciones 


| ALGORITMO                         | DEFINICIÓN                                                                                                                                                                                                                   | CÓMO FUNCIONA                                                                                                                                                                                                                                                                                                                                                                           | UN CASO DE USO                                                                                                                                                 | REFERENCIA                                                                                                               |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Árbol de decisión**             | Un árbol de decisiones es un diagrama que representa de forma gráfica las opciones de una decisión y sus posibles resultados, costos y consecuencias, con el fin de comparar alternativas y elegir el mejor camino a seguir. | • **Nodos:** representan puntos críticos donde se toman decisiones.• **Ramas:** representan las acciones u opciones posibles.• **Resultados:** los nodos terminales representan los posibles resultados.• **Probabilidades:** cuantifican la probabilidad de resultados específicos.• **Valores esperados:** se calculan multiplicando las probabilidades por los resultados asociados. | **Segmentación de clientes:** Las empresas de marketing clasifican a los compradores según su probabilidad de adquirir un producto.                            | [https://miro.com/es/diagrama/decision-tree-analysis-steps/](https://miro.com/es/diagrama/decision-tree-analysis-steps/) |
| **Regresión logística**           | Es un algoritmo de aprendizaje supervisado utilizado principalmente para problemas de clasificación, especialmente cuando se desea determinar la probabilidad de que una observación pertenezca a una determinada categoría. | Utiliza una función logística para transformar una combinación de variables de entrada en una probabilidad entre 0 y 1. Después, se establece un umbral para asignar la observación a una clase.                                                                                                                                                                                        | **Predicción de abandono de clientes:** puede estimar la probabilidad de que un cliente deje de utilizar un servicio.                                          | https://aws.amazon.com/es/what-is/logistic-regression/                                                                   |
| **K vecinos más cercanos (K-NN)** | Es un algoritmo de aprendizaje supervisado que clasifica una observación según las clases de las observaciones que se encuentran más cerca de ella.                                                                          | Primero se selecciona un valor **K**. Para una nueva observación, calcula la distancia respecto a los datos existentes y selecciona los K vecinos más cercanos. La clase más frecuente entre ellos determina la clasificación.                                                                                                                                                          | **Reconocimiento de escritura:** puede identificar un número escrito a mano comparándolo con ejemplos similares previamente registrados.                       | https://www.elastic.co/es/what-is/knn                                                                                    |
| **Naive Bayes**                   | Es un algoritmo de clasificación basado en el teorema de Bayes que supone que las características de los datos son independientes entre sí dadas las clases.                                                                 | Calcula la probabilidad de que una observación pertenezca a cada clase utilizando las probabilidades previas y las probabilidades de las características observadas. Finalmente, selecciona la clase con mayor probabilidad.                                                                                                                                                            | **Análisis de sentimientos:** puede clasificar comentarios de usuarios como positivos, negativos o neutrales.                                                  | https://www.ibm.com/mx-es/think/topics/naive-bayes                                                                       |
| **SVM**                           | Una Máquina de Vectores de Soporte (Support Vector Machine) es un algoritmo de aprendizaje supervisado utilizado principalmente para clasificación y también para regresión.                                                 | Busca encontrar un hiperplano que separe las diferentes clases maximizando la distancia entre el hiperplano y los datos más cercanos de cada clase. Mediante funciones kernel puede trabajar con datos que no son separables linealmente.                                                                                                                                               | **Detección de rostros:** puede utilizarse para clasificar imágenes según si contienen determinadas características faciales.                                  | https://la.mathworks.com/discovery/support-vector-machine.html                                                           |
| **Bosque aleatorio**              | Es un método de aprendizaje supervisado que combina múltiples árboles de decisión para realizar tareas de clasificación o regresión.                                                                                         | Construye numerosos árboles de decisión utilizando diferentes muestras y subconjuntos de características. En clasificación, cada árbol emite una predicción y el resultado final se obtiene mediante votación entre los árboles.                                                                                                                                                        | **Predicción de precios de viviendas:** puede analizar características como ubicación, tamaño y número de habitaciones para estimar el precio de una vivienda. | https://www.inesdi.com/blog/random-forest-que-es/                                                                        |
| **Red neuronal**                  | Es un modelo de aprendizaje automático inspirado en la estructura de las redes neuronales biológicas. Está formado por capas de nodos o neuronas que procesan información y aprenden patrones a partir de los datos.         | Los datos pasan por una o varias capas de neuronas. Cada neurona realiza cálculos sobre sus entradas mediante pesos y funciones de activación. Durante el entrenamiento, los pesos se ajustan para reducir el error de las predicciones.                                                                                                                                                | **Reconocimiento de voz:** puede aprender patrones del audio para convertir palabras habladas en texto.                                                        | https://aws.amazon.com/es/what-is/neural-network/                                                                        |