-----------------------------------------------------------------------
# Práctica: entrenar y probar un clasificador con Teachable Machine



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

##  Experimentos con las opciones avanzadas

En **Advanced** encontrarán, según la versión de la página, ajustes como **Epochs**, **Batch Size** y **Learning Rate**. Usen los valores que ofrezca la lista; los de abajo son solo una guía de qué probar (un valor menor y uno mayor que el predeterminado).

| #   | Ajuste            | Qué probar                                                                                           | Qué observar                                                                                                                                 |
| --- | ----------------- | ---------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Epochs            | Se probaron 2 épocas, el valor predeterminado de 50 y un valor alto de 100.                          | Con 2 épocas, el modelo confundió algunos residuos. Con 50 mejoró la clasificación y con 100 la mejora fue mínima.                           |
| 2   | Learning Rate     | Se probaron valores de 0.0001 y 0.01, comparados con el predeterminado de 0.001.                     | Con el valor menor, el aprendizaje fue más lento. Con el valor mayor, la clasificación fue menos estable.                                    |
| 3   | Batch Size        | Se probaron valores de 8 y 32, comparados con el predeterminado de 16.                               | Con el lote menor, el entrenamiento presentó más variaciones. Con el mayor, el entrenamiento fue más estable, pero la precisión cambió poco. |
| 4   | Cantidad de datos | Se compararon 5 imágenes por clase con 15 imágenes por clase, manteniendo los demás ajustes iguales. | Con 5 imágenes hubo más confusiones entre los residuos. Con 15 imágenes, el modelo reconoció mejor algunos objetos.                          |

### Tabla de registro (una fila por experimento)

Supongamos una prueba de 20 imagenes, en vez de 5

| Experimento   | Ajuste cambiado   | Valor usado    | Aciertos en prueba | Precisión (%) | Observación                                                      |
| ------------- | ----------------- | -------------- | ------------------ | ------------- | ---------------------------------------------------------------- |
| Base (fase B) | Ninguno           | Predeterminado | 16/20              | 80 %          | El modelo confundió algunos residuos de plástico.                |
| 1a            | Epochs            | 2              | 11/20              | 55 %          | Con pocas épocas, tuvo dificultades para clasificar.             |
| 1b            | Epochs            | 100            | 17/20              | 85 %          | Mejoró la clasificación, aunque no reconoció todos los residuos. |
| 2a            | Learning Rate     | 0.0001         | 14/20              | 70 %          | El aprendizaje fue más lento.                                    |
| 2b            | Learning Rate     | 0.01           | 10/20              | 50 %          | Los resultados fueron menos precisos.                            |
| 3a            | Batch Size        | 8              | 15/20              | 75 %          | La precisión fue ligeramente menor que la base.                  |
| 3b            | Batch Size        | 32             | 16/20              | 80 %          | La precisión se mantuvo igual que en la base.                    |
| 4a            | Cantidad de datos | 5 por clase    | 12/20              | 60 %          | Con pocos ejemplos, confundió varios residuos.                   |
| 4b            | Cantidad de datos | 15 por clase   | 16/20              | 80 %          | Con más ejemplos, mejoró la clasificación.                       |



---

##  Preguntas para responder en la entrega

¿La precisión subió, bajó o se mantuvo al pasar de 15 a 25 fotos por clase? ¿A qué creen que se debe?
en algunos si acerto por ejemplo en la manzana y en la hoja de papel, en la botella no pudo ya que detecta botellas trasparentes y la que usamos esta forrada de plastico y no se alcanza a observar

¿Qué imágenes de prueba falló el modelo? fallo con el plato de plastico y botella  ¿Qué tenían de distinto respecto a las de entrenamiento (fondo, luz, ángulo)? podria ser el angulo ya que se ocupa estar acomodando

¿Qué ajuste avanzado tuvo más efecto en el resultado? la manzana ¿Y cuál casi no cambió nada? manzana
¿Su modelo mostró señales de sobreajuste (muy bueno con los ejemplos de entrenamiento, malo con los de prueba) o de subajuste (malo en ambos)? Expliquen con sus resultados. si ya que cambiaba mucho la precision con el fondo que estuviera
En su proyecto, ¿qué error sería peor: un falso positivo o un falso negativo? Justifiquen. podrian ser los desechables ya que algunos tienen comida y su precision llegaria a fallar
¿Confiarían en este modelo para usarlo en la vida real? ¿Qué le faltaría? la verdad no aun le falta mas por aprender y identificar mas modelos e imagenes y no seria preciso.





