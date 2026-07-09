
# METODO  MONTECARLO
Cuando gestionas proyectos complejos, la incertidumbre es una constante. No siempre puedes predecir con exactitud cuánto tiempo llevará una tarea, cuánto costará o qué impacto tendrá un riesgo inesperado. El método Montecarlo ofrece una solución rigurosa: en lugar de asumir un único escenario, genera miles de simulaciones de Montecarlo para mostrar el rango completo de resultados posibles. Gracias al análisis de Montecarlo, los equipos pueden cuantificar la incertidumbre, identificar riesgos con mayor precisión y tomar decisiones estratégicas con una base sólida

## ¿Qué es el metodo Montecarlo?
El método Montecarlo es una técnica computacional que utiliza muestras aleatorias repetidas para obtener resultados numéricos y estimar la probabilidad de distintos desenlaces en procesos con variables inciertas. Se aplica en ámbitos como la gestión de proyectos, las finanzas, la ingeniería y la ciencia, y resulta especialmente útil cuando las variables de un sistema son demasiado complejas o numerosas para resolverse mediante fórmulas analíticas directas.
En la práctica, ejecuta un modelo matemático miles de veces, cada vez con valores aleatorios diferentes dentro de rangos definidos, y analiza la distribución de los resultados para orientar la toma de decisiones, por ejemplo en la elaboración de una proyección de ventas.
Con el aumento de la capacidad de cómputo, lo que antes requería semanas de cálculo manual ahora puede ejecutarse en segundos. Hoy en día, empresas de todos los sectores lo usan para evaluar riesgos, optimizar procesos y validar estrategias antes de comprometer recursos reales.

### Ejemplos de dónde poner en practica el metodo Montecarlo
La versatilidad del método Montecarlo lo convierte en una herramienta valiosa en múltiples contextos. Estos son algunos de los casos de uso más frecuentes en entornos empresariales:
- Gestión de presupuestos con variables inciertas, como costes de materiales fluctuantes o plazos de entrega variables
- Análisis financiero para calcular el valor en riesgo de una cartera de inversiones o el retorno esperado
- Planificación de lanzamientos de productos, evaluando la probabilidad de cumplir con fechas y objetivos de ventas
- Estimación del ROI de iniciativas estratégicas con múltiples supuestos
- Modelado de cadenas de suministro para anticipar cuellos de botella o retrasos
- Aplicaciones de Inteligencia Artificial y aprendizaje automático, donde se usa para entrenar modelos, validar hipótesis estadísticas y estimar la incertidumbre en predicciones
Antes de ejecutar una simulación, define con precisión los límites de cada variable de entrada. Cuanto más ajustado esté el rango a la realidad de tu sector, más útiles serán los resultados obtenidos.

### ¿Cuál es la importancia de éste método?
En lugar de presentar una única cifra como si fuera un hecho, muestra una distribución de resultados posibles junto con la probabilidad de cada uno. Eso transforma radicalmente cómo el personal directivo evalúa las restricciones de un proyecto, actualiza el registro de riesgos o compara distintos modelos de planificación estratégica.
<img width="711" height="391" alt="image" src="https://github.com/user-attachments/assets/5c0d41b3-6b01-471d-ac49-08b8d3dda98e" />

## ¿Cómo aplicarlo paso a paso?
Documenta cada paso del proceso en una herramienta de gestión de proyectos como Asana para que todo el equipo tenga acceso a los supuestos utilizados, las fuentes de datos y las conclusiones del análisis. Así garantizas la trazabilidad y facilitas futuras revisiones del modelo. A continuacion se presentan los pasos a seguir para la ejecución del método.

**1. Definir el problema y el modelo.** Antes de generar ninguna simulación, debes establecer qué variable quieres analizar y construir el modelo matemático que la describe. Este modelo relaciona las variables de entrada con el resultado que te interesa.

**2. Identificar las variables de entrada.** Determina qué parámetros del modelo son inciertos. Para cada uno, define una distribución de probabilidad adecuada basándote en datos históricos, opinión de expertos o estudios de mercado. Una estimación descuidada de las distribuciones de entrada puede invalidar todo el análisis posterior.

**3. Generar valores aleatorios.** El software selecciona aleatoriamente un valor de cada distribución de entrada. Esta combinación de valores representa un escenario posible. La calidad de este proceso depende del generador de números pseudoaleatorios empleado.

**4. Ejecutar las simulaciones.** El proceso anterior se repite miles de veces para producir una distribución completa de resultados. Cada iteración equivale a un escenario diferente. Cuantas más simulaciones ejecutes, más estable y fiable será la distribución resultante.

**5. Analizar los resultados.** Con la distribución de resultados en mano, interpreta los datos: identifica el valor esperado, los percentiles clave y el rango de variación. Esta información permite comunicar el riesgo de forma objetiva y tomar decisiones fundamentadas sobre plazos, presupuestos o estrategias de contingencia.

El método de Montecarlo no utiliza una única fórmula universal, sino que aplica técnicas estadísticas y muestreos aleatorios repetidos para aproximar resultados. Su enfoque central es la Ley de los Grandes Números, utilizando la media muestral como estimador del valor real

<img width="830" height="189" alt="image" src="https://github.com/user-attachments/assets/d02888e0-8041-46ee-b5fe-31dadda4fe0e" />

Para que este modelo funcione, se aplican varias fórmulas matemáticas fundamentales:
- Generación de Números AleatoriosPara iniciar la simulación, se generan números pseudoaleatorios uniformemente distribuidos en el intervalo [0, 1). Una de las fórmulas matemáticas más comunes es el generador lineal congruencial:
  
<img width="524" height="69" alt="image" src="https://github.com/user-attachments/assets/cbc98137-8e8d-4a31-afea-d2581426c31f" />

Donde x₀ es la semilla, a es el multiplicador, c es el incremento y m es el módulo.
- Transformación a Distribuciones EspecíficasUna vez obtenidos los números aleatorios U = [0, 1), se convierten a la distribución de probabilidad de la variable que se desea estudiar (normal, binomial, etc.) utilizando el Método de la Transformada Inversa:
  
<img width="247" height="55" alt="image" src="https://github.com/user-attachments/assets/936df3e7-5b34-4b92-b4a9-a518fb0e117a" />

Donde F⁻¹ es la función de distribución acumulada inversa.

A continucon un jemplo:
- Indica la función con la que quieres trabajar en la casilla de entrada.
- Define el intervalo [a,b] en el que calcular el área moviendo los puntos correspondientes sobre el eje OX.
- Desplaza el deslizador n para indicar el número de puntos aleatorios que deben generarse.
- Observa la aproximación obtenida del área.

  <img width="610" height="336" alt="image" src="https://github.com/user-attachments/assets/73ea5727-fbe7-4e9a-a15b-327aeaca549b" />

- Fórmula de Integración EstocásticaEn problemas matemáticos, como el cálculo de integrales complejas, el método evalúa la función f(x) en puntos aleatorios xi dentro de un dominio V:
  
<img width="342" height="184" alt="image" src="https://github.com/user-attachments/assets/aa590b7c-7a16-414b-ba42-2a3c2d7616c6" />


