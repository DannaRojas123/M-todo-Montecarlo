# Metodo Montecarlo README
# Método de Montecarlo

El método de Montecarlo es una técnica computacional que utiliza **números pseudoaleatorios** para aproximar soluciones a problemas donde intervienen variables inciertas, aplicando la Ley de los Grandes Números: entre más simulaciones se ejecuten, más se acerca el resultado promedio al valor real del sistema.

A continuación se presentan dos ejemplos aplicados: la aproximación del valor de **PI** y la estimación de **pérdidas financieras** por riesgo cibernético.

---

## 1. Aproximación del valor de PI

Tienes un tablero cuadrado y dentro dibujas un círculo perfecto que toca los bordes del cuadrado. Si lanzas dardos al azar y a ciegas sobre el cuadrado, la proporción de dardos que caen dentro del círculo te permite calcular PI.

### Planteamiento

- Radio del círculo: `r = 1`
- Lado del cuadrado: `L = 2`
- Área del cuadrado: `A_cuadrado = L² = 2 × 2 = 4`
- Área del círculo: `A_circulo = π × r² = π × 1² = π`

La probabilidad de que un dardo aleatorio caiga dentro del círculo es la proporción entre las dos áreas:

```
P = A_circulo / A_cuadrado = π / 4
```

Despejando π:

```
π = 4 × P
```

### Algoritmo con números pseudoaleatorios

1. Generar dos números pseudoaleatorios uniformes, `x` e `y`, en el intervalo `[0, 1)`. Cada par `(x, y)` representa la coordenada de un "dardo".
2. Para saber si el punto está dentro del cuarto de círculo, se evalúa la ecuación de la circunferencia:
   ```
   x² + y² ≤ r²      (con r = 1, la condición es x² + y² ≤ 1)
   ```
3. Repetir el proceso `N` veces y contar cuántos puntos cumplen la condición (caen dentro del círculo).
4. Calcular la proporción `P = dentro / N` y estimar `π = 4 × P`.

### Simulación con datos reales (N = 5)

| Iteración | x | y | x² + y² | Resultado | ¿Dentro? |
|---|---|---|---|---|---|
| 1 | 0.23 | 0.85 | 0.0529 + 0.7225 = 0.7754 | ≤ 1 | Sí |
| 2 | 0.91 | 0.45 | 0.8281 + 0.2025 = 1.0306 | > 1 | No |
| 3 | 0.35 | 0.12 | 0.1225 + 0.0144 = 0.1369 | ≤ 1 | Sí |
| 4 | 0.78 | 0.72 | 0.6084 + 0.5184 = 1.1268 | > 1 | No |
| 5 | 0.05 | 0.60 | 0.0025 + 0.3600 = 0.3625 | ≤ 1 | Sí |

### Resultados

Tras 5 lanzamientos, 3 de 5 puntos cayeron dentro del círculo:

```
P = 3 / 5 = 0.6
π ≈ 4 × 0.6 = 2.4
```

Con solo 5 iteraciones el resultado se aleja bastante del valor real de π (3.14159...), lo cual es esperado: la precisión del método mejora conforme `N` crece, ya que el error decrece proporcionalmente a `1/√N`. Para obtener una aproximación confiable se requieren miles o millones de iteraciones.

---

## 2. Estimación de pérdidas financieras (riesgo cibernético)

En el mundo empresarial, Montecarlo se usa para predecir escenarios futuros económicos donde las variables son inciertas. Supongamos que una empresa quiere calcular la pérdida económica esperada por ataques cibernéticos en el próximo año.

### Planteamiento

La pérdida anual depende de dos variables inciertas:

- **Frecuencia**: cuántos ataques exitosos ocurrirán al año. Sigue una distribución de **Poisson** con una media de 2 ataques por año.
- **Severidad**: cuánto dinero cuesta reparar cada ataque. Sigue una distribución **uniforme** entre $10,000 y $50,000 dólares.

La fórmula de la pérdida anual total es:

```
Pérdida_anual = S₁ + S₂ + ... + S_F
```

donde `F` es el número de ataques ocurridos en el año y `Sᵢ` es el costo de cada ataque individual.

### Algoritmo con números pseudoaleatorios

Como las distribuciones no son uniformes planas, se usan algoritmos de transformación para convertir números pseudoaleatorios estándar `[0, 1)` en valores que correspondan a las distribuciones del problema (Poisson para la frecuencia, uniforme para la severidad):

1. Generar un número aleatorio para determinar cuántos ataques ocurren en el año (frecuencia `F`).
2. Para cada ataque detectado ese año, generar otro número aleatorio para determinar su costo (severidad `Sᵢ`).
3. Sumar los costos individuales para obtener la pérdida total de ese año simulado.
4. Repetir el proceso `N = 5,000` veces para observar el comportamiento del riesgo.

### Simulación

**Año simulado 1:**
- Frecuencia generada: `F = 1` ataque.
- Costo generado: `S₁ = $15,000`.
- **Pérdida del Año 1: $15,000**

**Año simulado 2:**
- Frecuencia generada: `F = 0` ataques (año sin incidentes).
- **Pérdida del Año 2: $0**

**Año simulado 3:**
- Frecuencia generada: `F = 3` ataques (año negro).
- Costos generados: `S₁ = $45,000`, `S₂ = $20,000`, `S₃ = $35,000`.
- **Pérdida del Año 3: $45,000 + $20,000 + $35,000 = $100,000**

### Resultados

Si se promedian los resultados de los `N = 5,000` años simulados, la empresa obtiene la **Pérdida Esperada Promedio** anual por riesgo cibernético.

Sin embargo, el valor más útil que aporta Montecarlo aquí es el **análisis de percentiles**: por ejemplo, se puede observar que en el 95% de los años simulados la pérdida no superó los $120,000. Con esta información, la empresa puede decidir con base científica cuánto dinero debe asegurar o reservar en un fondo de emergencias para contingencias, en lugar de basarse en una única estimación puntual.

---

## Conclusión

Ambos ejemplos ilustran el mismo principio central: generar múltiples escenarios aleatorios a partir de números pseudoaleatorios y usar la proporción o el promedio de los resultados para aproximar una cantidad que sería difícil o imposible de calcular de forma analítica directa. Mientras el ejemplo de PI usa una condición geométrica simple (dentro/fuera del círculo), el ejemplo financiero combina dos distribuciones distintas (Poisson y uniforme) para modelar un riesgo real de negocio. En ambos casos, la calidad y cantidad de los números pseudoaleatorios generados determina directamente la precisión del resultado final.
