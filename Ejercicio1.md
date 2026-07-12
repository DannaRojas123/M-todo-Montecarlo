# APROXIMACION DEL VALOR DE PI

Tienes un tablero cuadrado y dentro dibujas un círculo perfecto que toca los bordes del cuadrado. Si lanzas dardos al azar y a ciegas sobre el cuadrado, la proporción de dardos que caen dentro del círculo te permite calcular PI.

### Planteamiento
- Radio = 1
- Lado del cuadrado = 2
- Área cuadrado = L² = 2 x 2 = 4
- Área circulo = PI x r² = PI x 1² = PI
La probabilidad de que un dardo aleatorio caiga dentro del círculo es la proporción entre las dos áreas:

<img width="382" height="84" alt="image" src="https://github.com/user-attachments/assets/8a355217-7870-4f34-b578-d27d2fd4fe2e" />

Por lo tanto, si despejamos PI:
#### PI = 4 x P
## Algorimo con números pseudoaleatorios
1. Generamos dos números pseudoaleatorios uniformes, x e y, en el intervalo [0, 1). Cada par (x, y) representa la coordenada de un "dardo".
2. Para saber si el punto está dentro del cuarto de círculo, usamos la ecuación de la circunferencia (x² + y² <= r²). Como r=1:

<img width="358" height="47" alt="image" src="https://github.com/user-attachments/assets/916af58a-b847-4694-b101-b5c9132ef2e9" />

4. Repetimos esto N veces y contamos cuántos puntos cumplen la condición.

## Simulación con datos reales
Simulación en miniatura con solo 5 iteraciones N=5:
- Iteración 1: Generamos x = 0.23, y = 0.85. Calculamos: 0.23² + 0.85² = 0.0529 + 0.7225 = 0.7754. Como 0.7754 <= 1, está dentro.
- Iteración 2: Generamos x = 0.91, y = 0.45. Calculamos: 0.91² + 0.45² = 0.8281 + 0.2025 = 1.0306. Como 1.0306 > 1, está fuera.
- Iteración 3: Generamos x = 0.35, y = 0.12. Calculamos: 0.35² + 0.12² = 0.1225 + 0.0144 = 0.1369 <= 1 dentro.
- Iteración 4: Generamos x = 0.78, y = 0.72.Calculamos: 0.78² + 0.72² = 0.6084 + 0.5184 = 1.1268 > 1 fuera.
- Iteración 5: Generamos x = 0.05, y = 0.60. Calculamos: 0.05² + 0.60² = 0.0025 + 0.3600 = 0.3625 <= 1 dentro.

## Resultados
Tras 5 lanzamientos, la probabilidad estimada es P = 3/5 = 0.6.
Calculamos PI:

<img width="335" height="53" alt="image" src="https://github.com/user-attachments/assets/4e578d81-81b9-4af6-8693-3ff803d73622" />

