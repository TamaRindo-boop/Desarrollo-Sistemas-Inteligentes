
## 3.1 ALGORITMOS DE BÚSQUEDA

**1. Problemas de búsqueda**
Consiste en encontrar una secuencia de acciones que lleve del estado inicial al estado objetivo. Se define con cinco componentes: estado inicial, acciones, modelo de transición, prueba de meta y costo del camino.

**2. Espacios de estados**
Conjunto de todos los estados alcanzables desde el estado inicial. Se representa como un grafo donde los nodos son estados y las aristas son acciones.

**3. Estado inicial**
Estado donde comienza el agente. Es el punto de partida de la búsqueda.

**4. Acciones**
Operadores que permiten pasar de un estado a otro. Cada acción genera un estado sucesor.

**5. Modelo de transición**
Función que describe el resultado de aplicar una acción: Resultado(s, a) = s'.

**6. Prueba de meta**
Función booleana que verifica si un estado es objetivo (explícita o implícita).

**7. Costo del camino**
Valor numérico g(n) que representa el costo desde el estado inicial hasta el nodo n.

**8. Solución**
Secuencia de acciones que lleva del estado inicial a la meta. Es óptima si tiene el menor costo.

**9. Frontera**
Conjunto de nodos generados pero no expandidos. Cola en BFS, pila en DFS, cola de prioridad en UCS.

**10. Nodo**
Estructura con estado, padre, acción, costo g(n) y profundidad. Varios nodos pueden compartir el mismo estado.

**11. Agente de resolución de problemas**
Formula el objetivo, define el problema, busca la solución y la ejecuta.


### Sistemas de búsqueda (ciega)

**1. Búsqueda no informada (ciega)**
No usa información adicional; solo distingue meta de no-meta.

Es un método de inteligencia artificial que explora un conjunto de datos o estados paso a paso sin tener pistas adicionales ni información sobre qué tan cerca está de la meta

**2. Búsqueda en amplitud**
Expande el nodo menos profundo. Usa cola FIFO. Completa y óptima (si costos iguales). Tiempo y espacio: O(b^d).

La búsqueda en amplitud (o en anchura, conocida como BFS por sus siglas en inglés) es un algoritmo de búsqueda ciega que explora el grafo nivel por nivel.

**3. Búsqueda en profundidad**
Expande el nodo más profundo. Usa pila LIFO. No completa ni óptima. Tiempo: O(b^m). Espacio: O(bm).

Prioriza avanzar verticalmente en el árbol o grafo antes de expandirse hacia los lados

**4. Búsqueda de costo uniforme**
Expande el nodo de menor costo g(n). Usa cola de prioridad. Completa y óptima. Tiempo y espacio: O(b^(1+⌊C*/ε⌋)).

Es un algoritmo de búsqueda ciega o no informada

**5. Cola**
Estructura FIFO: el primero en entrar es el primero en salir. Se usa en BFS.

 Es una colección lineal de elementos diseñada bajo el principio FIFO (First In, First Out), lo que significa que el primer elemento en entrar es el primero en salir.
 
**6. Pila**
Estructura LIFO: el último en entrar es el primero en salir. Se usa en DFS.

Es una colección lineal de elementos diseñada bajo el principio LIFO (Last In, First Out), lo que significa que el último elemento en entrar es el primero en salir.

**7. Completitud**
Garantiza encontrar una solución si existe.

Es la propiedad que garantiza que un algoritmo siempre encontrará una solución si esta existe

**8. Optimalidad**
Garantiza encontrar la solución de menor costo.

Propiedad que garantiza que un algoritmo siempre encontrará la solución con el menor costo posible

**9. Complejidad en tiempo**
Número de nodos generados/expandidos. BFS: O(b^d). DFS: O(b^m). UCS: O(b^(1+⌊C*/ε⌋)).

Mide el **número de nodos generados o visitados** antes de encontrar la solución o terminar la exploración

**10. Complejidad en espacio**
Memoria necesaria para la frontera. BFS: O(b^d). DFS: O(bm). UCS: O(b^(1+⌊C*/ε⌋)).

Mide la cantidad máxima de memoria (nodos) que el algoritmo necesita almacenar al mismo tiempo para gestionar la exploración


##### Sistemas de busqueda:
Un sistema de búsqueda es un método que permite resolver un problema encontrando una secuencia de acciones que lleva desde un estado inicial hasta un estado meta, siguiendo ciertas reglas.

Un sistema de búsqueda se compone de cinco elementos principales:

1. Estado inicial: es la situación en la que comienza el problema.
2. Acciones: son los movimientos o las operaciones que se pueden realizar para cambiar de un estado a otro.
3. Modelo: describe cómo cambia el estado cuando se realiza una acción; es decir, cuál será el resultado de cada acción.
4. Prueba de meta: permite comprobar si se ha alcanzado el objetivo deseado.
5. Costo del camino: es el costo total de las acciones realizadas desde el estado inicial hasta el estado meta. Puede representar distancia, tiempo, dinero o cantidad de pasos.

1
![[Pasted image 20261008181225.png]]
![[Pasted image 20261008181259.png|672]]
**1. ¿Qué es lo que hace?**

- **Simula algoritmos:** Permite elegir entre diferentes métodos matemáticos (como A*, Dijkstra, BFS, etc.) para calcular la ruta óptima.
- **Visualiza el proceso:** Muestra gráficamente cómo el algoritmo "explora" el espacio (las áreas celestes) antes de decidir el camino final (la línea amarilla).
- **Permite la interacción:** El usuario puede dibujar los obstáculos (muros grises), mover el punto de inicio (cuadrado verde) y el punto de destino (cuadrado rojo).
    

**2. Elementos que se ven en la imagen:**

- **Cuadrícula (Grid):** Es el "mundo" donde se mueve el algoritmo.
- **Nodo de Inicio (Verde):** El punto de partida.
- **Nodo de Destino (Rojo):** A donde se quiere llegar.
- **Muros (Gris oscuro):** Obstáculos que el camino no puede atravesar.
- **Estadísticas (Abajo a la izquierda):** Muestra datos técnicos como la longitud del camino ("length"), el tiempo que tardó ("time") y cuántas operaciones realizó.
    

2
![[Pasted image 20261008181321.png]]
![[Pasted image 20261008181340.png]]

## ¿Qué hace cada imagen?

### 1. Imagen superior

- El cuadro verde es el punto de inicio.
- El cuadro rojo es el destino.
- Los cuadros grises son obstáculos.
- La zona azul representa los lugares que el algoritmo ha explorado.
- La línea amarilla muestra el camino encontrado.
- Está activada la opción Allow Diagonal, que permite moverse en diagonal.
    
### 2. Imagen inferior

Se utiliza el mismo algoritmo, pero con otras opciones:

- Bi-directional: busca desde el inicio y desde la meta al mismo tiempo.
- Don't Cross Corners: impide pasar en diagonal entre dos obstáculos que forman una esquina.
- Allow Diagonal: está desactivada, por lo que el movimiento diagonal no está permitido.


## El problema de la busqueda ciega

#### Heuristica:
Regla practica que estima que tan lejos esta un estado de la meta

#### La pista: distancia Manhattan:
El agente solo se mueve arriba, abajo, izquierda y derecha

###### Tres numeros para cada casilla
g: lo que ya costo llegar desde S hasta esta casilla
h: lo que se estima que falta desde aqui hasta G
f = g + h: costo toal estimado de un camino que pasa por aqui

## 3.2 Actividad A*



**1. ¿Qué longitud tiene cada algoritmo?**  
El A* tuvo una longitud de 30, y el ciego (BFS) de 23.8. La diferencia es porque en el BFS permití movimiento en diagonal.

**2. ¿Cuánto tiempo se tardó cada algoritmo?**  
El A* tardó 0.7000 ms y el BFS 0.9000 ms. El A* fue más rápido porque usa una heurística que lo guía hacia la meta.

**3. ¿Qué diferencia observas?**  
La gran diferencia está en las operaciones. El A* fue muy eficiente, revisó solo 346 cuadros yendo directo a la meta. El BFS, al ser ciego, revisó 2212 cuadros y se expandió por casi toda la pantalla. 


## 3.3 Actividad Busquedas Heuristicas

### Pregunta 1

¿Cuántas casillas exploró **amplitud**, **voraz** y **A***? ¿Cuántos pasos tiene el camino de cada uno?


### Pregunta 2

Con tus palabras: ¿por qué la heurística hace que se exploren menos casillas?


### Pregunta 3

¿Cuántas casillas exploró cada algoritmo? Comparado con el campo abierto, ¿A* ahorró tanto como antes? ¿Por qué crees que la pared le afecta?


### Pregunta 4

Anota **pasos** y **costo** de costo uniforme, voraz y A*. ¿Cuántas casillas exploró costo uniforme y cuántas A*?


### Pregunta 5

¿Por qué voraz eligió un camino tan caro? ¿Qué toma en cuenta A* que voraz ignora?

### Pregunta 6

Compara A* con h = 0 contra costo uniforme. ¿Qué observas? ¿Qué conclusión sacas sobre la relación entre A* y la búsqueda ciega?

### Pregunta 7

Con `peso = 3`, ¿cuántas casillas exploró y cuánto costó el camino? Compara con A* normal. ¿Cuál es la ventaja y cuál el riesgo de dar más peso a la pista?


###  Pregunta 8

Con `INTENTOS = 20`: ¿cuántas combinaciones probó cada método, qué exactitud obtuvo y cuánto tardó?


### Pregunta 9

Prueba con 5 y con 50 intentos. ¿Mejoró la exactitud al aumentar los intentos? ¿Qué te dice eso?


###  Pregunta 10

¿En qué situación usarías grid search y en cuál random search? Relaciónalo con búsqueda ciega y heurística.



### ¿Que es una red neuronal?
Un programa que aprende a resolver una tarea a partir de ejemplos, en lugar de seguir reglas escritas por una persona. Esta hecha de muchas unidades pequeñas, las neuronas artificiales, conectadas entre si. Cada una hace un calculo sencillo; la respuesta sale de todas trabajando juntas.

Neuronal: LA IDEA SE INSPIRA EN EL CEREBRO, PERO NO FUNCIONA COMO UN CEREBRO


## 3.4 ¿Que relacion tiene las GPUs y las redes neuronales?

Las GPU y las redes neuronales están  conectadas porque, las redes neuronales son gigantescas operaciones de álgebra lineal que las GPU pueden resolver de forma masiva y simultánea. Mientras que una CPU procesa tareas complejas en orden secuencial, la arquitectura de una GPU está diseñada con miles de núcleos independientes ideales para el cálculo paralelo.


## Una neurona artificial (Recibe, pondera, decide)

1. Recibe  varios datos de entrada (ej: tamaño, edad, precio)
2. A cada dato de la una importancia, llamada peso. Un dato importante pesa mucho; uno irrelevante, casi nada.
3. Junta todo y decide que tan fuerte es su respuesta


## De una neurona a una red
Una sola neurona resuelve cosas muy simples. Al conectar muchas, en capas, la red capta patrones complejas.

- Capa de entrada: reccibe los datos 
- Capas ocultas: cada una combina lo que le entrega la anterior
- Capa de salida: da laa respuesta

## Como aprende una red: entrenar
El entrenamiento repite este ciclo miles o millones de veces

1. La red recibe un ejemplo y da una respuesta
2. Se compara con la respuesta correcta (aprendizaje supervisado)
3. Si se equivoco, se ajustan los pesos un poco para que se equivoque menos la proxima vez.

## Lo que ya conocen, ahora con redes

- Dattos de entrenamient y de prueba: se separsn para saber si la red funcioona con casos nuevos
- Sobrwajuste: un ared grande puede memorizar los ejemplos en vez de aprender el patron, y falla con datos nuevos
- Falsos positivos y falsos negativos: el costo de cada error sigue deccidiendo si el modelo sirve
- Hiperparametros: numeros de capas, numero de neuronnas, cuanto se ajusta cada vez. Se buscan con grid search o busqueda aleatoria

## ¿Que la hace profunda?

E


## Un poco de historia

## Tipos de redes segun el dato







## INVESTIGAR SOBRE GPU Y CPU DIFERENCIAS

## 1. ¿Qué es la CPU y qué es la GPU?

- CPU (Unidad Central de Procesamiento): es el cerebro general de la computadora. Ejecuta instrucciones, controla el sistema operativo, organiza datos y coordina las tareas.
    
- GPU (Unidad de Procesamiento Gráfico): está diseñada para realizar muchas operaciones matemáticas simultáneamente. Se utiliza en gráficos, simulaciones e inteligencia artificial.
    

## 2. Diferencias principales

|CPU|GPU|
|---|---|
|Tiene pocos núcleos potentes.|Tiene muchas unidades de cálculo.|
|Destaca en tareas secuenciales y variadas.|Destaca en tareas paralelas.|
|Controla y organiza procesos.|Acelera cálculos masivos.|
|Ejecuta programas y gestiona datos.|Procesa matrices y redes neuronales.|

## 3. ¿Por qué no utilizar solamente la GPU?

Porque la GPU no es eficiente para todas las tareas:

1. Necesita que el software y la CPU organicen gran parte del trabajo.
    
2. Algunas operaciones dependen de resultados anteriores y no pueden ejecutarse en paralelo.
    
3. La transferencia de datos entre memoria y procesadores consume tiempo.
    
4. Las tareas pequeñas pueden ejecutarse más rápido en la CPU.
    
5. La GPU consume energía y necesita refrigeración.
    

## 4. ¿Cómo funciona cada procesador?

CPU:

1. Busca una instrucción.
    
2. La interpreta.
    
3. Prepara los datos.
    
4. Ejecuta la operación.
    
5. Guarda el resultado y continúa.
    

GPU:

1. Recibe las tareas.
    
2. Prepara los datos en su memoria.
    
3. Divide el trabajo en operaciones paralelas.
    
4. Ejecuta miles de operaciones simultáneamente cuando es posible.
    
5. Entrega o almacena los resultados.
    

## 5. ¿Por qué la GPU es tan buena para la inteligencia artificial?

La IA utiliza enormes cantidades de operaciones matemáticas, especialmente multiplicaciones de matrices.

La GPU es excelente para estas operaciones porque:

- Paralelismo: realiza muchas operaciones al mismo tiempo.
    
- Velocidad: acelera los cálculos de las redes neuronales.
    
- Memoria: algunas GPU disponen de memoria de gran ancho de banda para mover datos rápidamente.
    
- Hardware especializado: ciertas GPU incluyen unidades diseñadas para acelerar operaciones de IA.
    

## 6. ¿Cómo se utilizan en la inteligencia artificial?

Durante el entrenamiento de una IA:

- La CPU organiza los datos y coordina el programa.
    
- La GPU calcula predicciones y gradientes.
    
- El modelo ajusta sus parámetros para reducir errores.
    
- El proceso se repite hasta obtener el rendimiento deseado.
    

Durante el uso de una IA, la GPU puede acelerar los cálculos necesarios para generar respuestas.


## Conocimientos: Sistemas difusos

