## 1. Definición del Problema

Los semáforos de tiempo fijo son ineficientes cuando el flujo vehicular es variable. El objetivo es diseñar un sistema que calcule el **Tiempo de Luz Verde** (variable de salida) basándose en la densidad del tráfico en las calles que confluyen en un crucero (variables de entrada).

## 2. Variables del Sistema

Para este modelo, utilizaremos dos entradas (sensores en el asfalto) y una salida (el control del semáforo).

### 🔴 Variables de Entrada (Antecedentes)

1. **Flujo Vial Principal (FVP):** Número de autos detectados en la avenida principal.
    
    - _Universo de discurso:_ 0 a 100 autos/min.
        
    - _Términos lingüísticos:_ `Bajo`, `Medio`, `Alto`.
        
2. **Flujo Vial Secundario (FVS):** Número de autos detectados en la calle que cruza.
    
    - _Universo de discurso:_ 0 a 50 autos/min.
        
    - _Términos lingüísticos:_ `Bajo`, `Medio`, `Alto`.
        

### 🟢 Variables de Salida (Consecuente)

1. **Tiempo de Luz Verde (TLV):** Duración en segundos que se le asignará a la avenida principal.
    
    - _Universo de discurso:_ 10 a 90 segundos.
        
    - _Términos lingüísticos:_ `Corto`, `Normal`, `Largo`.
        

---

## 3. Funciones de Pertenencia (Fuzzificación)

_Basado en la gráfica "Nivel de Dolor" de la clase, definimos los grados de pertenencia._

### Para las Entradas (Ejemplo FVP)

- **Bajo:** Función triangular que baja a 0 en el auto 40.
    
- **Medio:** Función triangular entre los autos 20 y 80.
    
- **Alto:** Función trapezoidal que empieza a subir desde el auto 60.
    

### Para la Salida (TLV)

- **Corto:** Triángulo centrado en 20s (de 10s a 40s).
    
- **Normal:** Triángulo centrado en 45s (de 30s a 60s).
    
- **Largo:** Triángulo centrado en 80s (de 60s a 90s).
    

---

## 4. Base de Reglas Difusas

_Siguiendo la lógica `SI [Entrada 1] Y [Entrada 2] ENTONCES [Salida]`._

|Regla|SI (FVP)|Y (FVS)|ENTONCES (TLV)|Prioridad / Lógica|
|---|---|---|---|---|
|**R1**|Bajo|Bajo|**Corto**|Poca gente en ambos lados, no hace falta esperar mucho.|
|**R2**|Bajo|Medio|**Corto**|La principal está vacía, hay que darle paso a la secundaria.|
|**R3**|Bajo|Alto|**Corto**|La principal está vacía, urgencia de desahogar la secundaria.|
|**R4**|Medio|Bajo|**Normal**|Flujo moderado en principal, poco en secundaria.|
|**R5**|Medio|Medio|**Normal**|Flujo equilibrado, tiempo estándar.|
|**R6**|Medio|Alto|**Corto**|La secundaria está saturada, reducir tiempo de la principal.|
|**R7**|Alto|Bajo|**Largo**|Saturada la principal, vacía la secundaria. Dar prioridad.|
|**R8**|Alto|Medio|**Largo**|Saturada la principal, flujo moderado cruzando.|
|**R9**|Alto|Alto|**Normal**|Ambas saturadas (hora pico), mantener un flujo constante.|

---

## 5. Ejemplo Práctico (Evaluación)

**Escenario:** Es hora pico. El sensor de la avenida principal detecta 75 autos/min (FVP = _Alto 0.8_) y el sensor secundario detecta 15 autos/min (FVS = _Bajo 1.0_).

1. **Evaluación de reglas activas:**
    
    - R7 se activa: `SI FVP es Alto (0.8) Y FVS es Bajo (1.0) ENTONCES TLV es Largo`.
        
    - _Peso de la regla (Mínimo de los dos): 0.8_
        
    - (Las demás reglas se activan en menor grado o se descartan).
        
2. **Combinación:** El motor de inferencia recorta la función de pertenencia de "Largo" al 0.8 (método Mandani).
    
3. **Defuzzificación (Centroide):** Se calcula el área bajo la curva resultante para obtener un número exacto en segundos (Ej. **72 segundos** de luz verde).
    


