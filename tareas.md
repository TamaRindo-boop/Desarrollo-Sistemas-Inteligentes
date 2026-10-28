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


## 3.4 ¿Que relacion tiene las GPUs y las redes neuronales?

Las GPU y las redes neuronales están  conectadas porque, las redes neuronales son gigantescas operaciones de álgebra lineal que las GPU pueden resolver de forma masiva y simultánea. Mientras que una CPU procesa tareas complejas en orden secuencial, la arquitectura de una GPU está diseñada con miles de núcleos independientes ideales para el cálculo paralelo.

#### Desarrollar un mapa mental acerca de las redes neuronales

![[Mayela.jpg]]




-----------------------------------------------------------------------
# Práctica: entrenar y probar un clasificador con Teachable Machine


**Herramienta:** https://teachablemachine.withgoogle.com
**Modalidad:** por equipos
**Entrega:** un solo archivo (PDF o Markdown en su repositorio) con las evidencias y respuestas que se piden abajo.

---

## 1. Objetivo

Entrenar un clasificador, medir qué tan bien funciona con pocos ejemplos, medir de nuevo con más ejemplos y, después, cambiar las opciones avanzadas para observar cómo se comporta el entrenamiento.

---

## 2. Antes de empezar: elijan el proyecto

Elijan **una** idea en la que la clase se vea en la imagen (no un estado interno como cansancio o miedo):

- Clasificar basura (papel, plástico, orgánico)



Mínimo **2 clases**. Escriban en su entrega el proyecto elegido y las clases.

---

## 3. Instrucciones

### Fase A. Entrenamiento con 15 fotos por clase

1. Entren a Teachable Machine y elijan **Get Started**.
2. Creen un proyecto de **Imagen** (o **Pose**, si es el de postura) y elijan el modelo estándar.
3. Renombren las clases con lo que van a reconocer.
4. Capturen **15 imágenes por clase** (con la cámara o subiendo archivos). Varíen el ángulo, el fondo y la luz.
5. **Antes de entrenar**, separen **10 imágenes por clase para prueba**. Estas imágenes **no se suben a la plataforma ni se usan para entrenar**. Guárdenlas en una carpeta aparte.
6. Pulsen **Train Model** y esperen sin cerrar la pestaña. No cambien nada en **Advanced** en esta fase.
7. Midan la precisión:
   - Prueben el modelo con sus **imágenes de prueba** (las 10 por clase que no usaron) en la vista de **Preview**, una por una.
   - Anoten cuántas acertó.
   - Calculen el porcentaje: `aciertos / total de imágenes de prueba × 100`.
8. Tomen las capturas de pantalla que se piden en la sección 4 (Evidencia A).

### Fase B. Agregar 10 fotos más por clase

1. Agreguen **10 imágenes nuevas por clase** al entrenamiento (pasan a 25 por clase). Deben ser distintas de las 10 de prueba.
2. Vuelvan a entrenar con **los mismos ajustes** que en la fase A (sin tocar **Advanced**).
3. Prueben con **las mismas imágenes de prueba** de la fase A. Es importante que sean las mismas para poder comparar.
4. Calculen el nuevo porcentaje y tomen las capturas (Evidencia B).

### Fase C. Opciones avanzadas

1. Usen como base el modelo de la fase B (25 por clase).
2. Abran **Advanced**. Cambien **un solo ajuste a la vez** y vuelvan a entrenar.
3. Prueben con las mismas imágenes de prueba y registren los resultados en la tabla de la sección 5.
4. Después de cada experimento, regresen el ajuste a su valor original antes de cambiar el siguiente.

> Nota: si cambian dos ajustes al mismo tiempo no podrán saber cuál produjo el efecto.

---

## 4. Evidencias que deben entregar

### Evidencia A. Modelo con 15 fotos por clase

- [ ] Captura de pantalla del proyecto con las clases y el número de imágenes de cada una (deben verse 15 por clase).
- [ ] Captura de **Preview** probando con una imagen de prueba, donde se vea el porcentaje de confianza por clase.
- [ ] Si la plataforma muestra métricas después de entrenar (por ejemplo, en el apartado **Under the hood**), captura de la **precisión por clase**.
- [ ] Tabla de resultados de su prueba manual (formato de abajo).

### Evidencia B. Modelo con 25 fotos por clase

- [ ] Captura del proyecto con las clases y el número de imágenes (deben verse 25 por clase).
![[Pasted image 20261022183732.png]]
- [ ] Captura de **Preview** probando con una de las mismas imágenes de prueba.
![[Pasted image 20261022183800.png]]


### Tabla de resultados (una por fase)

| Imagen de prueba      | Clase real | Clase que predijo el modelo | Confianza (%) | ¿Acertó? |
| --------------------- | ---------- | --------------------------- | ------------- | -------- |
| 1 manzana             | organico   | organico                    | 99            | si       |
| 2 Botella de plastico | inorganico | inorganico                  | 100           | si       |
| 3 Hojas dde papel     | inorganico | inorganico                  | 89            | si       |
| 4 Mano                | organico   | organico                    | 89            | si       |
| 5 Comida              | organico   | organico                    | 99            | si       |

**Precisión de la fase** = aciertos / total de imágenes de prueba × 100 = ______ 100 %

### Comparación A contra B

| Fase | Fotos de entrenamiento por clase | Imágenes de prueba                   | Aciertos | Precisión (%) |
| ---- | -------------------------------- | ------------------------------------ | -------- | ------------- |
| A    | 15                               | ![[Pasted image 20261022184321.png]] | 5 bien   | 100           |
| B    | 15                               | ![[Pasted image 20261022184334.png]] | 5 bien   | 100           |

---

## 5. Experimentos con las opciones avanzadas

En **Advanced** encontrarán, según la versión de la página, ajustes como **Epochs**, **Batch Size** y **Learning Rate**. Usen los valores que ofrezca la lista; los de abajo son solo una guía de qué probar (un valor menor y uno mayor que el predeterminado).

| # | Ajuste | Qué probar | Qué observar |
|---|---|---|---|
| 1 | **Epochs** (cuántas veces recorre los ejemplos) | Un valor muy bajo (por ejemplo, 1 a 5), el predeterminado y uno más alto | ¿Con pocas épocas falla en todo? ¿Con muchas deja de mejorar o empieza a memorizar? |
| 2 | **Learning Rate** (qué tan grande es cada ajuste) | Un valor mucho menor y otro mucho mayor que el predeterminado | ¿Cuál se estabiliza? ¿Cuál se comporta de forma errática o no aprende? |
| 3 | **Batch Size** (cuántos ejemplos ve antes de ajustar) | Uno menor y uno mayor que el predeterminado | ¿Cambia la rapidez o la estabilidad del entrenamiento? ¿Cambia la precisión? |
| 4 | **Cantidad de datos** (no está en Advanced, pero conviene probarlo) | 5 imágenes por clase contra 25 por clase, con los demás ajustes iguales | ¿Qué cambia más: los ajustes avanzados o la cantidad de datos? |

### Tabla de registro (una fila por experimento)

| Experimento | Ajuste cambiado | Valor usado | Aciertos en prueba | Precisión (%) | Observación |
|---|---|---|---|---|---|
| Base (fase B) | ninguno | predeterminado | | | |
| 1a | Epochs | | | | |
| 1b | Epochs | | | | |
| 2a | Learning Rate | | | | |
| 2b | Learning Rate | | | | |
| 3a | Batch Size | | | | |
| 3b | Batch Size | | | | |
| 4 | Cantidad de datos | 5 por clase | | | |

Si la plataforma muestra gráficas de exactitud o pérdida por época, tomen captura de la gráfica de al menos un experimento de Epochs y uno de Learning Rate.

---

## 6. Preguntas para responder en la entrega

¿La precisión subió, bajó o se mantuvo al pasar de 15 a 25 fotos por clase? ¿A qué creen que se debe?
en algunos si acerto por ejemplo en la manzana y en la hoja de papel, en la botella no pudo ya que detecta botellas trasparentes y la que usamos esta forrada de plastico y no se alcanza a observar

¿Qué imágenes de prueba falló el modelo? fallo con el plato de plastico y botella  ¿Qué tenían de distinto respecto a las de entrenamiento (fondo, luz, ángulo)? podria ser el angulo ya que se ocupa estar acomodando

¿Qué ajuste avanzado tuvo más efecto en el resultado? la manzana ¿Y cuál casi no cambió nada? manzana
¿Su modelo mostró señales de sobreajuste (muy bueno con los ejemplos de entrenamiento, malo con los de prueba) o de subajuste (malo en ambos)? Expliquen con sus resultados. si ya que cambiaba mucho la precision con el fondo que estuviera
En su proyecto, ¿qué error sería peor: un falso positivo o un falso negativo? Justifiquen. podrian ser los desechables ya que algunos tienen comida y su precision llegaria a fallar
¿Confiarían en este modelo para usarlo en la vida real? ¿Qué le faltaría? la verdad no aun le falta mas por aprender y identificar mas modelos e imagenes y no seria preciso.

---


---

## 8. Recomendaciones

- Guarden el proyecto (en la plataforma o descargando el archivo del proyecto, si lo ofrece) antes de empezar los experimentos, para poder regresar al modelo base.
- No cierren la pestaña mientras entrena.
- Si usan imágenes de internet, revisen la licencia y no usen fotos de personas sin su permiso.




 -----------------------------------------------------------------------
## INVESTIGAR SOBRE GPU Y CPU DIFERENCIAS

#### ¿Qué es la CPU y qué es la GPU?

- CPU (Unidad Central de Procesamiento): es el cerebro general de la computadora. Ejecuta instrucciones, controla el sistema operativo, organiza datos y coordina las tareas.
- GPU (Unidad de Procesamiento Gráfico): está diseñada para realizar muchas operaciones matemáticas simultáneamente. Se utiliza en gráficos, simulaciones e inteligencia artificial.

#### Diferencias principales

|CPU|GPU|
|---|---|
|Tiene pocos núcleos potentes.|Tiene muchas unidades de cálculo.|
|Destaca en tareas secuenciales y variadas.|Destaca en tareas paralelas.|
|Controla y organiza procesos.|Acelera cálculos masivos.|
|Ejecuta programas y gestiona datos.|Procesa matrices y redes neuronales.|

#### ¿Por qué no utilizar solamente la GPU?

Porque la GPU no es eficiente para todas las tareas:

1. Necesita que el software y la CPU organicen gran parte del trabajo.
2. Algunas operaciones dependen de resultados anteriores y no pueden ejecutarse en paralelo.
3. La transferencia de datos entre memoria y procesadores consume tiempo.
4. Las tareas pequeñas pueden ejecutarse más rápido en la CPU.
5. La GPU consume energía y necesita refrigeración

#### ¿Cómo funciona cada procesador?

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

#### ¿Por qué la GPU es tan buena para la inteligencia artificial?

La IA utiliza enormes cantidades de operaciones matemáticas, especialmente multiplicaciones de matrices.

La GPU es excelente para estas operaciones porque:

- Paralelismo: realiza muchas operaciones al mismo tiempo.
- Velocidad: acelera los cálculos de las redes neuronales.
- Memoria: algunas GPU disponen de memoria de gran ancho de banda para mover datos rápidamente.
- Hardware especializado: ciertas GPU incluyen unidades diseñadas para acelerar operaciones de IA.

#### ¿Cómo se utilizan en la inteligencia artificial?

Durante el entrenamiento de una IA:

- La CPU organiza los datos y coordina el programa.
- La GPU calcula predicciones y gradientes.
- El modelo ajusta sus parámetros para reducir errores.
- El proceso se repite hasta obtener el rendimiento deseado.

Durante el uso de una IA, la GPU puede acelerar los cálculos necesarios para generar respuestas.