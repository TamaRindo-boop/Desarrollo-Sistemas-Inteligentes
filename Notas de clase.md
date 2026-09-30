

##### UNIDAD_1
## **¿Qué es un Sistema inteligente?**
Entidad que percibe su etorno mediante sensores y actua sobre ese entono mediando actuadres, seleccionando en cada momento la accion que maximiza ssu medida de desempeño, dado lo  que ha percibido hasta ese punto y el conocimiento con el que cuenta

## Basados en reglas y conocimientos

El conociemiento se codifica de forma explicita como hechos y reglas, y un motor de intereferencia razona con ellos para llegar a conclusion

## Machine learning
El sistema induce su funcion de decision a partir de datos de ejemplo, en vez de que un humano la escriba regla por regla
Tres formas principales: Supervisado, no supervisado, por refuerzo

## Redes neuronales y aprendizaje profundo
Modelo compuesto por capas de unidades interconectadas que aprenden representaciones  cada vez mas abstractas de los datos


## Sistemas difusos (fuzzy logic)
Sistema que maneja grados de pertenencia entre 0 y 1, en vez de una logica estrictamente verdadero/falso

## Algoritmos geneticos y computacion evolutiva

Metodo de busqueda que evoluciona una poblacion de soluciones candidatas mediante seleccion, cruce y mutacion, imitando la seleccion natural

## Sistemas multiagentes
Sistema compuesto por varios agentess autonomos que interactuan entre si, cooperando o compitiendo, dentro de un mismo entorno

## Razonamiento basado en casos (Case-Based Reasoning)


-Trabajo, en google academico en una area de trabajo pero donde se aplico y que se resolvio, 10 articulos en total 



##### UNIDAD_2

Machine Learning:
 El machine learning es el subconjunto de inteligencia artificial (IA) centrado en algoritmos que pueden "aprender" los patrones de los datos de entrenamiento y, posteriormente, hacer _inferencias_ precisas sobre nuevos datos. Esta capacidad de reconocimiento de patrones permite que los modelos de machine learning tomen decisiones o predicciones sin instrucciones explícitas y codificadas.

###### Ejemplos
Prediccion de precion de  una casa
T: predecir el precio de una casa
P: error cuadratico medio entre precio predicho y precio real
E: base de datos de ventas pasadas


###### Flujo de trabajo
1.  **Definir la tarea (T)**: que se quiere predecir  o decidir
2.  **Reunir la experiencia (E)**: los datos de los que el sistema va a aprender
3.  **Elegir como medir el desempeño(P)**: la metrica que dira si el modelo sirve
4.  **Entrenar** : el algoritmo ajusta sus parametros internos para minimizar el error sobre los datos de entrenamiento
5. **Evaluar**: se mide P sobre datos que el modelo nunca vio durante el entrenamiento
6. **Usar o ajustar**: si P es suficiente, se despluega; si no, se repite el ciclo con mas datos o un modelo distinto

PROYECTO FINAL: 
1. que tarea hace su sistema?
2. que algoritmo?
3. Experiencia
4. Evaluar 



###### Clasificacion de Machine Learning

| Tipo                  | Definición                                                                                                                                                         | Ejemplo                                                                                                                                                              |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Supervisado**    | El modelo aprende usando datos que ya tienen una **respuesta o etiqueta conocida**. Aprende a relacionar las características de entrada con el resultado esperado. | **Detección de spam:** se le dan correos marcados como “spam” o “no spam” y aprende a clasificar nuevos correos.                                                     |
| **2. No supervisado** | El modelo trabaja con datos **sin etiquetas** y busca encontrar patrones, grupos o relaciones por sí mismo.                                                        | **Segmentación de clientes:** agrupa clientes según sus compras, edad o hábitos, sin que previamente se le indique a qué grupo pertenece cada uno.                   |
| **3. Por Esfuerzo**   | El modelo aprende mediante **prueba y error**, recibiendo recompensas o penalizaciones según sus acciones.                                                         | **Un robot que aprende a caminar:** recibe una recompensa cuando avanza sin caerse y una penalización cuando se cae, aprendiendo gradualmente qué acciones realizar. |


##### Glosario (Todo con base de Machine Learning)

1. Pandas
2. Matplotlib
3. Scikit-learn (Investigar que datos de prueba maneja)
4. Google Colab
5. Arbol de decision
6. Matriz de confusion
7. Sobreajuste

##### Caja negra (Black Box Testing)

Se prueba el software **sin conocer su código ni estructura interna**. Solo importa qué entra y qué sale.

- **Enfoque:** Entrada → Salida (comportamiento externo)
    
- **Qué se prueba:** Funcionalidad, requisitos, casos de uso
    
- **Quién lo hace:** Testers, usuarios, QA (no necesitan saber programar)
    
- **Ventajas:** Simula el uso real; no requiere conocimiento técnico
    
- **Desventajas:** No detecta errores en lógica interna; puede dejar caminos sin probar
    
- **Ejemplo:** Probar un login ingresando usuario/contraseña y verificando si entra o no
    

##### Caja blanca (White Box Testing)

Se prueba el software **conociendo su código, estructura y lógica interna**.

- **Enfoque:** Estructura interna, flujo de control, caminos de ejecución
    
- **Qué se prueba:** Cobertura de código, ramas, condiciones, bucles
    
- **Quién lo hace:** Desarrolladores o testers con conocimiento técnico
    
- **Ventajas:** Detecta errores lógicos ocultos; alta cobertura
    
- **Desventajas:** Costoso, requiere acceso al código, no detecta requisitos faltantes
    
- **Ejemplo:** Verificar que cada rama de un `if/else` se ejecute al menos una vez