# ESTIMACIÓN DE PERDIDAS FINANCIERAS
En el mundo empresarial, Montecarlo se usa para predecir escenarios futuros económicos donde las variables son inciertas. Supongamos que una empresa quiere calcular la pérdida económica esperada por ataques cibernéticos en el próximo año.

## Planteamiento
La pérdida anual depende de dos variables inciertas:
- Frecuencia: Cuántos ataques exitosos ocurrirán al año. Sigue una distribución de Poisson con una media de 2 ataques por año.
- Severidad: Cuánto dinero cuesta reparar cada ataque. Sigue una distribución uniforme entre $10,000 y $50,000 dólares.
La fórmula de la pérdida anual total es:

<img width="541" height="88" alt="image" src="https://github.com/user-attachments/assets/6fdb37f5-9e06-435b-8a17-21f5d340373d" />

## Algoritmo con Números Pseudoaleatorios
Como las distribuciones no son planas, usamos algoritmos matemáticos para transformar números pseudoaleatorios estándar entre [0,1) en los valores de nuestro problema:
1. Generar un número aleatorio para determinar cuántos ataques ocurren este año.
2. Para cada ataque detectado en ese año, generar otro número aleatorio para determinar su costo.
3. Sumar los costos para obtener la pérdida de ese año simulado.
4. Repetir el proceso N = 5,000 veces para ver el comportamiento del riesgo.

## Simulación
- Año Simulado 1:
    - Generamos un número aleatorio para la frecuencia que se traduce en F = 1 ataque.
    - Generamos un número aleatorio para el costo de ese único ataque. Nos da S1 = $15,000.
    - Pérdida del Año 1: $15,000.
- Año Simulado 2:
    -  Generamos el número aleatorio de frecuencia y el modelo nos dice que este año no hubo incidentes: F = 0 ataques.
    - Pérdida del Año 2: $0.
- Año Simulado 3:
    - El número aleatorio de frecuencia arroja un año negro: F = 3 ataques.
    - Generamos tres números aleatorios independientes para los costos de cada ataque:Ataque 1: S1 = $45,000. Ataque 2: S2 = $20,000. Ataque 3:        S3 = $35,000
    - Pérdida del Año 3: $45,000 + $20,000 + $35,000 = $100,000.

## Resultados
Si promediamos los resultados de miles de años simulados, la empresa obtendrá la Pérdida Esperada Promedio.

Pero lo más valioso de Montecarlo aquí es el análisis de percentiles: la empresa podrá observar que, por ejemplo, en el 95% de los años simulados la pérdida no superó los $120,000. Esto les permite decidir con base científica cuánto dinero deben asegurar o guardar en un fondo de emergencias para contingencias.
