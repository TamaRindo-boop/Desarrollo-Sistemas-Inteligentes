## 3.3 Actividad Busquedas Heuristicas

### Pregunta 1

¿Cuántas casillas exploró **amplitud**, **voraz** y **A***? ¿Cuántos pasos tiene el camino de cada uno?

Amplitud explorados = 94 , pasos = 13 , costo = 13 
Voraz explorados = 14 , pasos = 13 , costo = 13 
A* explorados = 44 , pasos = 13 , costo = 13

### Pregunta 2

Con tus palabras: ¿por qué la heurística hace que se exploren menos casillas?

La heuristica busca la meta mas directo que andar buscando por otros cuadros

### Pregunta 3

¿Cuántas casillas exploró cada algoritmo? Comparado con el campo abierto, ¿A* ahorró tanto como antes? ¿Por qué crees que la pared le afecta?

Amplitud explorados = 98 , pasos = 17 , costo = 17 
Voraz explorados = 26 , pasos = 17 , costo = 17
A* explorados = 87 , pasos = 17 , costo = 17
No, A* no ahorro, de hecho aumento por tener barreras, esto afecta por buscar una meta, Manhattan la ignora y lo lleva hacia una zona bloqueada.

### Pregunta 4

Anota **pasos** y **costo** de costo uniforme, voraz y A*. ¿Cuántas casillas exploró costo uniforme y cuántas A*?

Uniforme: Explora muchas casillas
Voraz:Explora menos casillas
A*: explora muchi menos que los otros dos

Costo uniforme   explorados =  44 , pasos = 14 , costo = 14
Voraz            explorados =   9 , pasos =  8 , costo = 24
A*               explorados =  25 , pasos = 14 , costo = 14

### Pregunta 5

¿Por qué voraz eligió un camino tan caro? ¿Qué toma en cuenta A* que voraz ignora?

Lo que tiene voraz es que ignora lo edmas, se va directo a la meta. A* considera el costo acumulado 

### Pregunta 6

Compara A* con h = 0 contra costo uniforme. ¿Qué observas? ¿Qué conclusión sacas sobre la relación entre A* y la búsqueda ciega?

Saca lo mismo, lo que hace es quitandole un peso hace que este no ande buscando o rodeando 
### Pregunta 7

Con `peso = 3`, ¿cuántas casillas exploró y cuánto costó el camino? Compara con A* normal. ¿Cuál es la ventaja y cuál el riesgo de dar más peso a la pista?

4x4, este dobletea en explorador pero baja en pasos, haciendp que le costo tenga dos mas de lo normal. Aunque sus ventajas esten por ser mas corto, este sera mas caro
###  Pregunta 8

Con `INTENTOS = 20`: ¿cuántas combinaciones probó cada método, qué exactitud obtuvo y cuánto tardó?

Random search -> probó 20 combinaciones | exactitud 0.905 | 0.3 s Usó el 5% de las combinaciones y el 5% del tiempo
### Pregunta 9

Prueba con 5 y con 50 intentos. ¿Mejoró la exactitud al aumentar los intentos? ¿Qué te dice eso?

Si, pero con mas intentos este mejora pero el rendimiento decrece

###  Pregunta 10

¿En qué situación usarías grid search y en cuál random search? Relaciónalo con búsqueda ciega y heurística.

- **Grid search:** espacio pequeño, tiempo suficiente, se quiere garantía de optimalidad - como búsqueda ciega.

- **Random search:** espacio grande, se necesita rapidez, se acepta solución cercana a la óptima - como heurística.