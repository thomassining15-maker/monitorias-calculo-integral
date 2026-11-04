# REPASO SERIES MONITORIA ACADÉMICA
(Basado en el texto de James Stewart, 7ma Edicion)

---

## 1. Resumen de Sucesiones

### Definicion de Sucesion
Una sucesion es una funcion cuyo dominio es el conjunto de los enteros positivos. En terminos mas simples, es una lista ordenada de numeros escrita en forma de una secuencia:
{a1, a2, a3, ..., an, ...}

Donde:
- an es el termino general de la sucesion.
- El indice n indica la posicion del termino en la lista.

### Conceptos Clave
- **Convergencia:** Una sucesion {an} converge si el limite de an cuando n tiende a infinito es un numero real L.
- **Divergencia:** Si el limite no existe o tiende a infinito, la sucesion diverge.

---

## 2. Guia de Series

### ¿Que es una Serie?
Una serie es la suma de los terminos de una sucesion infinita. Se representa mediante la notacion de sumatoria (sigma):
Sumatoria desde n=1 hasta infinito de (an)

**Ilustracion Conceptual:**
Imagina que tienes un pastel. 
- Primero tomas la mitad (1/2).
- Luego tomas la mitad de lo que queda (1/4).
- Luego la mitad de lo que queda (1/8).
La suma de todas esas piezas (1/2 + 1/4 + 1/8 + ...) es una serie. Si la suma total se acerca a un numero finito (en este caso, 1), la serie converge.

### Tipos Comunes de Series
1. **Serie Geometrica:** Cada termino se obtiene multiplicando el anterior por una constante r (razon).
   - Forma: a + ar + ar^2 + ...
   - Converge si |r| < 1.
2. **Serie p:** De la forma Sumatoria de (1 / n^p).
   - Converge si p > 1.
   - Diverge si p <= 1 (como la serie armonica donde p=1).

---

## 3. Criterios de Convergencia y Divergencia

Para determinar si una serie converge o diverge sin calcular la suma exacta, utilizamos los siguientes criterios:

### A. Test de la Divergencia (Test del Termino n-esimo)
Si el limite de an cuando n -> infinito NO es cero, entonces la serie diverge.
*Importante:* Si el limite es cero, el test NO concluye nada (la serie podria converger o divergir).

### B. Criterio de la Integral
Si f(x) es una funcion continua, positiva y decreciente, la serie Sumatoria(an) converge si y solo si la integral impropia de f(x) desde 1 hasta infinito converge.

### C. Criterio de Comparacion Directa
Si tenemos dos series con terminos positivos:
- Si la serie "mas grande" converge, la "mas pequeña" tambien converge.
- Si la serie "mas pequeña" diverge, la "mas grande" tambien diverge.

### D. Criterio de Comparacion por Limite
Se utiliza cuando la comparacion directa es dificil. Se calcula el limite de (an / bn). Si el resultado es un numero finito y positivo, ambas series tienen el mismo comportamiento.

### E. Criterio de la Razon (Ratio Test)
Se calcula L = limite de |a(n+1) / an| cuando n -> infinito.
- Si L < 1: La serie converge absolutamente.
- Si L > 1: La serie diverge.
- Si L = 1: El test no es concluyente.

---

## 4. Ejercicios Resueltos (Estilo Stewart)

### Ejercicio 1: Serie Geometrica
**Enunciado:** Analice la convergencia de la serie Sumatoria de (2^n / 3^n) desde n=1 al infinito.

**Solucion Paso a Paso:**
1. **Identificar el tipo:** Podemos reescribir la serie como Sumatoria de (2/3)^n. Es una serie geometrica.
2. **Identificar la razon (r):** r = 2/3.
3. **Aplicar Criterio:** Para series geometricas, convergen si |r| < 1.
4. **Evaluacion:** |2/3| = 0.66... que es menor que 1.
**Resultado:** La serie CONVERGE.

---

### Ejercicio 2: Serie p y Serie Armonica
**Enunciado:** Determine si la serie Sumatoria de (1 / sqrt(n)) converge o diverge.

**Solucion Paso a Paso:**
1. **Reescribir el termino:** 1 / sqrt(n) es lo mismo que 1 / n^(1/2).
2. **Identificar el tipo:** Es una serie p con p = 1/2.
3. **Aplicar Criterio:** Una serie p converge solo si p > 1.
4. **Evaluacion:** 1/2 es menor que 1.
**Resultado:** La serie DIVERGE.

---

### Ejercicio 3: Criterio de la Razon
**Enunciado:** Analice la serie Sumatoria de (n! / 2^n) desde n=1 al infinito.

**Solucion Paso a Paso:**
1. **Identificar el termino:** an = n! / 2^n.
2. **Aplicar Criterio de la Razon:** Calculamos el limite de |a(n+1) / an|.
   - a(n+1) = (n+1)! / 2^(n+1)
   - an = n! / 2^n
3. **Simplificar la expresion:**
   L = limite n->inf [ (n+1)! / 2^(n+1) ] * [ 2^n / n! ]
   L = limite n->inf [ (n+1) * n! / (2 * 2^n) ] * [ 2^n / n! ]
   L = limite n->inf [ (n+1) / 2 ]
4. **Evaluacion:** Cuando n tiende a infinito, (n+1)/2 tiende a infinito.
5. **Conclusio:** Como L = infinito (L > 1), la serie diverge.
**Resultado:** La serie DIVERGE por el Criterio de la Razon.
