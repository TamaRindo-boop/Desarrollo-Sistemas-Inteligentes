
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

