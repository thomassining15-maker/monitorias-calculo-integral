# Taller de Cálculo Integral: Series Infinitas

**Curso:** Cálculo Integral (segundo semestre)
**Referencia:** J. Stewart, *Cálculo*, 7.ª ed., Capítulo 11 (secciones 11.2 a 11.6)
**Modalidad:** Presencial, resuelto y explicado paso a paso
**Alcance:** Definición de convergencia, criterio de la divergencia, series conocidas, comparación y comparación en el límite, integral, serie alternante, convergencia absoluta, razón y raíz.

---

## Índice

0. Antes de empezar: notación y estrategia
1. Definición de convergencia (sumas parciales)
2. Criterio de la divergencia
3. Series conocidas (geométrica, p, armónica, telescópica)
4. Criterio de comparación y comparación en el límite
5. Criterio de la integral
6. Criterio de la serie alternante
7. Convergencia absoluta y condicional
8. Criterio de la razón (cociente)
9. Criterio de la raíz
10. Ejercicios integradores: ¿qué criterio usar?
11. Tabla resumen y errores frecuentes

---

## 0. Antes de empezar

Dada una serie $\sum_{n=1}^{\infty} a_n$, su **n-ésima suma parcial** es

$$s_n = a_1 + a_2 + \cdots + a_n .$$

La serie **converge** si la sucesión $\{s_n\}$ tiene límite finito $s$; entonces $\sum a_n = s$. Si el límite no existe o es infinito, la serie **diverge**.

**Estrategia general** (de lo más rápido a lo más pesado):

1. ¿$a_n \to 0$? Si no, diverge (criterio de la divergencia).
2. ¿Se parece a una serie conocida (geométrica, $p$, telescópica)?
3. ¿Es de términos positivos? Comparación, comparación en el límite, integral, razón o raíz.
4. ¿Alterna signo? Serie alternante y/o convergencia absoluta.
5. ¿Tiene factoriales o potencias $n$-ésimas? Razón o raíz.

---

## 1. Definición de convergencia (sumas parciales)

**Idea:** hallar una fórmula cerrada para $s_n$ y calcular $\lim_{n\to\infty} s_n$.

### Ejercicio 1.1
Calcule $\displaystyle\sum_{n=1}^{\infty}\frac{1}{n(n+1)}$.

**Solución.**

*Paso 1: fracciones parciales.*
$$\frac{1}{n(n+1)}=\frac{1}{n}-\frac{1}{n+1}.$$

*Paso 2: escribir la suma parcial.* Es una suma **telescópica** (los términos intermedios se cancelan):
$$s_n=\left(1-\tfrac12\right)+\left(\tfrac12-\tfrac13\right)+\cdots+\left(\tfrac1n-\tfrac1{n+1}\right)=1-\frac{1}{n+1}.$$

*Paso 3: límite.*
$$\lim_{n\to\infty}s_n=\lim_{n\to\infty}\left(1-\frac1{n+1}\right)=1.$$

**Respuesta:** la serie converge y su suma es $1$.

---

### Ejercicio 1.2
Calcule $\displaystyle\sum_{n=2}^{\infty}\frac{2}{n^2-1}$.

**Solución.**

*Paso 1:* $n^2-1=(n-1)(n+1)$. Por fracciones parciales,
$$\frac{2}{(n-1)(n+1)}=\frac{1}{n-1}-\frac{1}{n+1}.$$

*Paso 2:* escribimos los primeros términos y los últimos:

| $n$ | término |
|---|---|
| 2 | $1-\frac13$ |
| 3 | $\frac12-\frac14$ |
| 4 | $\frac13-\frac15$ |
| $\vdots$ | $\vdots$ |
| $N-1$ | $\frac1{N-2}-\frac1N$ |
| $N$ | $\frac1{N-1}-\frac1{N+1}$ |

Se cancelan casi todos. Sobreviven $1$ y $\tfrac12$ al inicio, y $-\tfrac1N$ y $-\tfrac1{N+1}$ al final:
$$s_N=1+\frac12-\frac1N-\frac1{N+1}.$$

*Paso 3:* $\displaystyle\lim_{N\to\infty}s_N=\frac32$.

**Respuesta:** converge a $\dfrac32$.

> Nota: aquí se cancelan los términos con **salto de 2**, por eso sobreviven dos términos al inicio y dos al final.

---

### Ejercicio 1.3
Determine si $\displaystyle\sum_{n=1}^{\infty}\ln\!\left(\frac{n}{n+1}\right)$ converge.

**Solución.**

*Paso 1:* por propiedades del logaritmo, $\ln\frac{n}{n+1}=\ln n-\ln(n+1)$.

*Paso 2:* suma parcial (telescópica):
$$s_n=(\ln1-\ln2)+(\ln2-\ln3)+\cdots+(\ln n-\ln(n+1))=\ln 1-\ln(n+1)=-\ln(n+1).$$

*Paso 3:* $\displaystyle\lim_{n\to\infty}\bigl(-\ln(n+1)\bigr)=-\infty$.

**Respuesta:** la serie **diverge**.

> Observe que $a_n=\ln\frac{n}{n+1}\to\ln1=0$, y aun así la serie diverge. Que el término tienda a 0 **no** basta para convergir.

---

### Ejercicio 1.4
La suma parcial de una serie $\sum a_n$ es $s_n=\dfrac{n}{3n+1}$. Halle $a_n$ y la suma de la serie.

**Solución.**

*Paso 1:* como $s_n-s_{n-1}=a_n$ para $n\ge2$ y $a_1=s_1$:
$$a_n=\frac{n}{3n+1}-\frac{n-1}{3n-2}=\frac{n(3n-2)-(n-1)(3n+1)}{(3n+1)(3n-2)}.$$

*Paso 2:* numerador: $3n^2-2n-(3n^2-2n-1)=1$. Entonces
$$a_n=\frac{1}{(3n+1)(3n-2)},\qquad n\ge 2.$$
Para $n=1$: $a_1=s_1=\tfrac14$, y la fórmula da $\tfrac{1}{4\cdot1}=\tfrac14$. Coincide, así que la fórmula vale para todo $n\ge1$.

*Paso 3:* la suma es el límite de $s_n$:
$$\sum_{n=1}^\infty a_n=\lim_{n\to\infty}\frac{n}{3n+1}=\frac13.$$

---

## 2. Criterio de la divergencia

**Enunciado (Stewart, 11.2).**
Si $\displaystyle\lim_{n\to\infty}a_n$ no existe o es distinto de $0$, entonces $\sum a_n$ **diverge**.

**Advertencia:** el recíproco es **falso**. Si $a_n\to0$, el criterio **no concluye nada** (la serie armónica $\sum 1/n$ tiene $a_n\to0$ y diverge).

### Ejercicio 2.1
Pruebe que $\displaystyle\sum_{n=1}^{\infty}\frac{n^2}{5n^2+4}$ diverge.

**Solución.** Dividimos numerador y denominador por $n^2$:
$$\lim_{n\to\infty}\frac{n^2}{5n^2+4}=\lim_{n\to\infty}\frac{1}{5+4/n^2}=\frac15\neq0.$$
Por el criterio de la divergencia, la serie **diverge**.

---

### Ejercicio 2.2
Determine si $\displaystyle\sum_{n=1}^{\infty}\left(1+\frac1n\right)^n$ converge.

**Solución.** Recordamos el límite notable $\lim_{n\to\infty}(1+1/n)^n=e$. Como $e\neq0$, la serie **diverge**.

---

### Ejercicio 2.3
Determine si $\displaystyle\sum_{n=1}^{\infty}n\,\operatorname{sen}\!\left(\frac1n\right)$ converge.

**Solución.** Sea $x=1/n\to0^+$:
$$\lim_{n\to\infty}n\,\operatorname{sen}\frac1n=\lim_{x\to0^+}\frac{\operatorname{sen}x}{x}=1\neq0.$$
La serie **diverge**.

---

### Ejercicio 2.4
Determine si $\displaystyle\sum_{n=1}^{\infty}(-1)^n\frac{n}{n+1}$ converge.

**Solución.** Los términos son $a_n=(-1)^n\frac{n}{n+1}$. Como $\frac{n}{n+1}\to1$, los términos pares se acercan a $+1$ y los impares a $-1$. El límite de $a_n$ **no existe**. Por el criterio de la divergencia, la serie **diverge**.

---

### Ejercicio 2.5 (trampa)
¿Qué concluye el criterio de la divergencia para $\displaystyle\sum_{n=1}^{\infty}\frac{1}{n}$ y para $\displaystyle\sum_{n=1}^{\infty}\frac{1}{n^2}$?

**Solución.** En ambas, $a_n\to0$. El criterio **no concluye** en ninguna. Hay que usar otro criterio: la primera (armónica) diverge y la segunda ($p=2$) converge, como veremos en las secciones 3 y 5.

---

## 3. Series conocidas

### Resumen

**Geométrica.** $\displaystyle\sum_{n=1}^\infty ar^{n-1}$ (con $a\ne0$):
- Si $|r|<1$ converge y $\displaystyle\sum_{n=1}^\infty ar^{n-1}=\frac{a}{1-r}$ (primer término sobre $1-r$).
- Si $|r|\ge1$ diverge.

**Serie $p$.** $\displaystyle\sum_{n=1}^\infty\frac1{n^p}$ converge si $p>1$ y diverge si $p\le1$. Con $p=1$ es la **armónica**.

**Telescópica.** Se escribe $a_n=b_n-b_{n+1}$ y $s_n=b_1-b_{n+1}$.

### Ejercicio 3.1
Calcule $\displaystyle\sum_{n=1}^{\infty}3\left(-\frac23\right)^{n-1}$.

**Solución.** Es geométrica con $a=3$ y $r=-\tfrac23$. Como $|r|=\tfrac23<1$, converge:
$$\sum=\frac{3}{1-(-2/3)}=\frac{3}{5/3}=\frac95.$$

---

### Ejercicio 3.2
Calcule $\displaystyle\sum_{n=1}^{\infty}\frac{3^{n+1}}{4^n}$.

**Solución.**

*Paso 1:* reescribimos para identificar $a$ y $r$:
$$\frac{3^{n+1}}{4^n}=3\cdot\frac{3^n}{4^n}=3\left(\frac34\right)^n=\frac94\left(\frac34\right)^{n-1}.$$

*Paso 2:* $a=\tfrac94$, $r=\tfrac34$, $|r|<1$:
$$\sum=\frac{9/4}{1-3/4}=\frac{9/4}{1/4}=9.$$

---

### Ejercicio 3.3
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{4^n}{3^{n-1}}$ converge.

**Solución.** $\dfrac{4^n}{3^{n-1}}=4\left(\dfrac43\right)^{n-1}$, geométrica con $r=\tfrac43$. Como $|r|>1$, **diverge**.

---

### Ejercicio 3.4
Calcule $\displaystyle\sum_{n=1}^{\infty}\frac{2^n+3^n}{6^n}$.

**Solución.**

*Paso 1:* separamos:
$$\frac{2^n+3^n}{6^n}=\left(\frac13\right)^n+\left(\frac12\right)^n.$$

*Paso 2:* ambas son geométricas convergentes (con primer término igual a la razón):
$$\sum_{n=1}^\infty\left(\tfrac13\right)^n=\frac{1/3}{1-1/3}=\frac12,\qquad \sum_{n=1}^\infty\left(\tfrac12\right)^n=\frac{1/2}{1-1/2}=1.$$

*Paso 3:* la suma de series convergentes es la serie de la suma:
$$\sum=\frac12+1=\frac32.$$

---

### Ejercicio 3.5
Exprese el decimal periódico $1.2\overline{45}=1.2454545\ldots$ como fracción.

**Solución.**

*Paso 1:* separamos la parte no periódica: $1.2\overline{45}=1.2+0.0\overline{45}$.

*Paso 2:* $0.0454545\ldots=0.045+0.00045+0.0000045+\cdots$ es geométrica con $a=0.045$ y $r=0.01$:
$$\frac{0.045}{1-0.01}=\frac{0.045}{0.99}=\frac{45}{990}=\frac1{22}.$$

*Paso 3:*
$$1.2\overline{45}=\frac65+\frac1{22}=\frac{132}{110}+\frac{5}{110}=\frac{137}{110}.$$

---

### Ejercicio 3.6
¿Para qué valores de $x$ converge $\displaystyle\sum_{n=0}^{\infty}\frac{(x-2)^n}{3^n}$? Halle la suma.

**Solución.**

*Paso 1:* es geométrica con $a=1$ y $r=\dfrac{x-2}{3}$.

*Paso 2:* converge si $\left|\dfrac{x-2}{3}\right|<1\iff|x-2|<3\iff -1<x<5$.

*Paso 3:* suma:
$$\frac{1}{1-\frac{x-2}{3}}=\frac{3}{3-(x-2)}=\frac{3}{5-x}.$$

---

### Ejercicio 3.7 (serie $p$)
Clasifique: (a) $\sum\dfrac{1}{n^{3/2}}$, (b) $\sum\dfrac{1}{\sqrt n}$, (c) $\sum\dfrac{5}{n^{0.99}}$, (d) $\sum\dfrac{1}{n^{\pi}}$.

**Solución.**
(a) $p=\tfrac32>1$: **converge**.
(b) $\tfrac1{\sqrt n}=\tfrac1{n^{1/2}}$, $p=\tfrac12\le1$: **diverge**.
(c) $p=0.99\le1$ (el factor 5 no cambia la naturaleza): **diverge**.
(d) $p=\pi>1$: **converge**.

---

## 4. Criterio de comparación y comparación en el límite

**Comparación directa** (series de términos positivos). Sean $\sum a_n$ y $\sum b_n$ con $a_n,b_n>0$:
- Si $\sum b_n$ converge y $a_n\le b_n$, entonces $\sum a_n$ converge.
- Si $\sum b_n$ diverge y $a_n\ge b_n$, entonces $\sum a_n$ diverge.

**Comparación en el límite.** Si $a_n,b_n>0$ y $\displaystyle\lim_{n\to\infty}\frac{a_n}{b_n}=c$ con $0<c<\infty$, entonces **ambas series convergen o ambas divergen**.

**Cómo elegir $b_n$:** conserve solo los términos dominantes de $a_n$ cuando $n\to\infty$ (en una fracción de polinomios, el cociente de los términos de mayor grado).

### Ejercicio 4.1 (comparación directa, converge)
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{1}{2n^2+3n+1}$ converge.

**Solución.**

*Paso 1:* para $n\ge1$, $2n^2+3n+1>2n^2$, así que
$$0<\frac{1}{2n^2+3n+1}<\frac1{2n^2}.$$

*Paso 2:* $\sum\frac{1}{2n^2}=\tfrac12\sum\frac1{n^2}$ converge (serie $p$ con $p=2$).

*Paso 3:* por comparación, la serie **converge**.

---

### Ejercicio 4.2 (comparación directa, diverge)
Determine si $\displaystyle\sum_{n=3}^{\infty}\frac{\ln n}{n}$ converge.

**Solución.**

*Paso 1:* para $n\ge3$, $\ln n>\ln e=1$, entonces $\dfrac{\ln n}{n}>\dfrac1n>0$.

*Paso 2:* $\sum\frac1n$ diverge (armónica).

*Paso 3:* por comparación, la serie **diverge**.

---

### Ejercicio 4.3 (comparación directa con geométrica)
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{5}{2+3^n}$ converge.

**Solución.**

*Paso 1:* $2+3^n>3^n$, luego $\dfrac{5}{2+3^n}<\dfrac{5}{3^n}=5\left(\dfrac13\right)^n$.

*Paso 2:* $\sum 5(1/3)^n$ es geométrica con $r=\tfrac13$: converge.

*Paso 3:* la serie **converge**.

---

### Ejercicio 4.4 (comparación en el límite, converge)
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{\sqrt n}{n^2+1}$ converge.

**Solución.**

*Paso 1:* términos dominantes: $\dfrac{\sqrt n}{n^2}=\dfrac1{n^{3/2}}$. Tomamos $b_n=\dfrac{1}{n^{3/2}}$.

*Paso 2:*
$$\lim_{n\to\infty}\frac{a_n}{b_n}=\lim_{n\to\infty}\frac{\sqrt n}{n^2+1}\cdot n^{3/2}=\lim_{n\to\infty}\frac{n^2}{n^2+1}=1.$$
El límite es positivo y finito.

*Paso 3:* $\sum b_n$ converge ($p=\tfrac32>1$). Por comparación en el límite, la serie **converge**.

---

### Ejercicio 4.5 (comparación en el límite, diverge)
Determine si $\displaystyle\sum_{n=2}^{\infty}\frac{1}{\sqrt{n^2-1}}$ converge.

**Solución.**

*Paso 1:* para $n$ grande, $\sqrt{n^2-1}\approx n$. Tomamos $b_n=\dfrac1n$.

*Paso 2:*
$$\lim_{n\to\infty}\frac{1/\sqrt{n^2-1}}{1/n}=\lim_{n\to\infty}\frac{n}{\sqrt{n^2-1}}=\lim_{n\to\infty}\frac{1}{\sqrt{1-1/n^2}}=1.$$

*Paso 3:* $\sum\frac1n$ diverge, así que la serie **diverge**.

---

### Ejercicio 4.6 (comparación en el límite con $\operatorname{sen}$)
Determine si $\displaystyle\sum_{n=1}^{\infty}\operatorname{sen}\!\left(\frac1n\right)$ converge.

**Solución.** Para $n\ge1$, $0<\frac1n\le1<\pi$, así que $a_n>0$. Tomamos $b_n=\frac1n$:
$$\lim_{n\to\infty}\frac{\operatorname{sen}(1/n)}{1/n}=\lim_{x\to0^+}\frac{\operatorname{sen}x}{x}=1.$$
Como $\sum\frac1n$ diverge, la serie **diverge**.

---

### Ejercicio 4.7
Determine si $\displaystyle\sum_{n=1}^{\infty}\ln\!\left(1+\frac1{n^2}\right)$ converge.

**Solución.** Tomamos $b_n=\frac1{n^2}$ y sea $x=\frac1{n^2}\to0^+$:
$$\lim_{n\to\infty}\frac{\ln(1+1/n^2)}{1/n^2}=\lim_{x\to0^+}\frac{\ln(1+x)}{x}\overset{\text{L'H}}{=}\lim_{x\to0^+}\frac{1/(1+x)}{1}=1.$$
Como $\sum\frac1{n^2}$ converge, la serie **converge**.

---

### Ejercicio 4.8 (cuidado con la dirección de la desigualdad)
Analice $\displaystyle\sum_{n=2}^\infty\frac1{n^2-1}$ e indique si la comparación directa con $\sum\frac1{n^2}$ permite concluir, y si lo permite la comparación en el límite.

**Solución.**
- *Comparación directa con $\sum 1/n^2$:* $\dfrac{1}{n^2-1}>\dfrac1{n^2}$, y $\sum 1/n^2$ converge. Pero la desigualdad va en el sentido **contrario** al necesario (una serie mayor que una convergente no se puede concluir). **No permite concluir.**
- *Comparación en el límite con $b_n=1/n^2$:* $\dfrac{a_n}{b_n}=\dfrac{n^2}{n^2-1}\to1$. Como $\sum1/n^2$ converge, la serie **converge**.

(Alternativamente, es telescópica: $\frac1{n^2-1}=\frac12\left(\frac1{n-1}-\frac1{n+1}\right)$ y suma $\tfrac34$.)

---

## 5. Criterio de la integral

**Enunciado (Stewart, 11.3).** Sea $f$ **continua, positiva y decreciente** en $[1,\infty)$ y $a_n=f(n)$. Entonces

$$\sum_{n=1}^\infty a_n \text{ converge}\iff\int_1^\infty f(x)\,dx \text{ converge.}$$

(Si la serie empieza en $n=k$, se integra desde $k$. Basta que $f$ sea decreciente **desde algún punto en adelante**.)

**Importante:** la suma de la serie **no** es igual al valor de la integral; solo comparten convergencia o divergencia.

### Ejercicio 5.1
Demuestre que la serie $p$, $\sum\frac1{n^p}$, converge si y solo si $p>1$.

**Solución.** Sea $f(x)=x^{-p}$, que es continua, positiva y decreciente en $[1,\infty)$ para $p>0$.
- Si $p\ne1$: $\displaystyle\int_1^\infty x^{-p}dx=\lim_{t\to\infty}\frac{x^{1-p}}{1-p}\Big|_1^t=\lim_{t\to\infty}\frac{t^{1-p}-1}{1-p}$.
 - Si $p>1$: $t^{1-p}\to0$, la integral vale $\frac1{p-1}$ y **converge**.
 - Si $0<p<1$: $t^{1-p}\to\infty$, **diverge**.
- Si $p=1$: $\int_1^\infty\frac{dx}{x}=\lim_{t\to\infty}\ln t=\infty$, **diverge**.
- Si $p\le0$: $a_n\not\to0$, diverge por el criterio de la divergencia.

---

### Ejercicio 5.2
Determine si $\displaystyle\sum_{n=2}^{\infty}\frac{1}{n\ln n}$ converge.

**Solución.**

*Paso 1: hipótesis.* $f(x)=\dfrac1{x\ln x}$ es continua y positiva en $[2,\infty)$. Es decreciente porque $x\ln x$ es creciente.

*Paso 2: integral* (sustitución $u=\ln x$, $du=dx/x$):
$$\int_2^\infty\frac{dx}{x\ln x}=\lim_{t\to\infty}\Big[\ln(\ln x)\Big]_2^t=\lim_{t\to\infty}\bigl(\ln(\ln t)-\ln(\ln 2)\bigr)=\infty.$$

*Paso 3:* la integral diverge, luego la serie **diverge**.

---

### Ejercicio 5.3
Determine si $\displaystyle\sum_{n=2}^{\infty}\frac{1}{n(\ln n)^2}$ converge.

**Solución.**

*Paso 1:* $f(x)=\dfrac{1}{x(\ln x)^2}$ es continua, positiva y decreciente en $[2,\infty)$.

*Paso 2:* con $u=\ln x$:
$$\int_2^\infty\frac{dx}{x(\ln x)^2}=\lim_{t\to\infty}\left[-\frac1{\ln x}\right]_2^t=\lim_{t\to\infty}\left(-\frac1{\ln t}+\frac1{\ln2}\right)=\frac1{\ln 2}.$$

*Paso 3:* la integral converge, así que la serie **converge**.

---

### Ejercicio 5.4
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{1}{n^2+1}$ converge.

**Solución.**

*Paso 1:* $f(x)=\dfrac1{x^2+1}$ es continua, positiva y decreciente en $[1,\infty)$.

*Paso 2:*
$$\int_1^\infty\frac{dx}{x^2+1}=\lim_{t\to\infty}\bigl[\arctan x\bigr]_1^t=\frac\pi2-\frac\pi4=\frac\pi4.$$

*Paso 3:* converge. (Ojo: $\pi/4$ **no** es la suma de la serie.)

---

### Ejercicio 5.5
Determine si $\displaystyle\sum_{n=1}^{\infty}n\,e^{-n^2}$ converge.

**Solución.**

*Paso 1: decreciente.* $f(x)=xe^{-x^2}$:
$$f'(x)=e^{-x^2}-2x^2e^{-x^2}=e^{-x^2}(1-2x^2)<0\quad\text{para }x\ge1.$$
Es continua y positiva. Se cumplen las hipótesis.

*Paso 2:* con $u=x^2$:
$$\int_1^\infty xe^{-x^2}dx=\lim_{t\to\infty}\left[-\frac12e^{-x^2}\right]_1^t=\frac{1}{2e}.$$

*Paso 3:* converge.

---

### Ejercicio 5.6 (estimación del residuo)
Sea $s=\sum_{n=1}^\infty\frac1{n^2}$. (a) Aproxime $s$ con $s_{10}$ y acote el error. (b) Acote $s$ entre dos números. (c) ¿Cuántos términos bastan para que el error sea menor que $0.001$?

**Teoría.** Si $f$ cumple las hipótesis del criterio de la integral y $R_n=s-s_n$, entonces
$$\int_{n+1}^\infty f(x)\,dx\le R_n\le\int_n^\infty f(x)\,dx.$$

**Solución.**

*Paso 1:* $\displaystyle\int_n^\infty\frac{dx}{x^2}=\frac1n$ y $\displaystyle\int_{n+1}^\infty\frac{dx}{x^2}=\frac1{n+1}$. Así,
$$\frac1{n+1}\le R_n\le\frac1n.$$

*(a)* $s_{10}=1+\frac14+\frac19+\cdots+\frac1{100}\approx1.549768$ y el error cumple $R_{10}\le\frac1{10}=0.1$.

*(b)* $s_{10}+\frac1{11}\le s\le s_{10}+\frac1{10}$:
$$1.640677\le s\le1.649768.$$
(El valor exacto $\pi^2/6\approx1.644934$ está en el intervalo.)

*(c)* Queremos $R_n\le\frac1n<0.001\Rightarrow n>1000$. **Bastan 1001 términos** (o más).

---

## 6. Criterio de la serie alternante (Leibniz)

**Enunciado (Stewart, 11.5).** Si $\displaystyle\sum_{n=1}^\infty(-1)^{n-1}b_n$ con $b_n>0$ cumple

1. $b_{n+1}\le b_n$ para todo $n$ (o desde algún $n$ en adelante, es decir, $\{b_n\}$ decreciente), y
2. $\displaystyle\lim_{n\to\infty}b_n=0$,

entonces la serie **converge**.

**Estimación del error.** Si $s=\sum(-1)^{n-1}b_n$ converge con las hipótesis anteriores, entonces $|R_n|=|s-s_n|\le b_{n+1}$.

**Cómo verificar que $b_n$ decrece:** (i) mostrar $b_{n+1}\le b_n$ directamente, o (ii) mostrar $f'(x)\le0$ para $f(x)=b_x$.

### Ejercicio 6.1
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{(-1)^{n-1}}{n}$ (serie armónica alternante) converge.

**Solución.** $b_n=\dfrac1n$.
1. $\dfrac1{n+1}<\dfrac1n$: decreciente.
2. $\lim\dfrac1n=0$.

Por el criterio de la serie alternante, **converge**.

---

### Ejercicio 6.2
Determine si $\displaystyle\sum_{n=1}^{\infty}(-1)^n\frac{n}{2n+1}$ converge.

**Solución.** $b_n=\dfrac n{2n+1}\to\dfrac12\ne0$. La condición 2 **falla**. Entonces $a_n=(-1)^nb_n\not\to0$ y, por el criterio de la divergencia, la serie **diverge**.

---

### Ejercicio 6.3
Determine si $\displaystyle\sum_{n=1}^{\infty}(-1)^{n-1}\frac{n^2}{n^3+1}$ converge.

**Solución.** $b_n=\dfrac{n^2}{n^3+1}$.

*Límite:* $\dfrac{n^2}{n^3+1}\to0$ ✔.

*Decreciente:* $f(x)=\dfrac{x^2}{x^3+1}$,
$$f'(x)=\frac{2x(x^3+1)-x^2\cdot3x^2}{(x^3+1)^2}=\frac{2x-x^4}{(x^3+1)^2}=\frac{x(2-x^3)}{(x^3+1)^2}.$$
$f'(x)<0$ cuando $x^3>2$, es decir $x>2^{1/3}\approx1.26$. Entonces $b_n$ es decreciente para $n\ge2$ ✔. (Basta con que decrezca desde algún $n$.)

**Conclusión:** converge.

---

### Ejercicio 6.4
Determine si $\displaystyle\sum_{n=2}^{\infty}(-1)^n\frac{\ln n}{n}$ converge.

**Solución.** $b_n=\dfrac{\ln n}{n}$.

*Límite:* por L'Hôpital, $\displaystyle\lim_{x\to\infty}\frac{\ln x}{x}=\lim\frac{1/x}{1}=0$ ✔.

*Decreciente:* $f(x)=\dfrac{\ln x}{x}$, $f'(x)=\dfrac{1-\ln x}{x^2}<0$ cuando $\ln x>1$, es decir $x>e$. Luego $b_n$ decrece para $n\ge3$ ✔.

**Conclusión:** converge.

---

### Ejercicio 6.5 (estimación del error)
¿Cuántos términos de $\displaystyle\sum_{n=1}^{\infty}\frac{(-1)^{n-1}}{n^2}$ se necesitan para aproximar su suma con error menor que $0.01$?

**Solución.** Hipótesis: $b_n=\frac1{n^2}$ decrece y tiende a 0. Entonces $|R_n|\le b_{n+1}=\dfrac1{(n+1)^2}$.

Exigimos $\dfrac1{(n+1)^2}<0.01\iff(n+1)^2>100\iff n+1>10\iff n\ge10$.

Con $n=10$:
$$s_{10}=1-\tfrac14+\tfrac19-\cdots-\tfrac1{100}\approx0.8180.$$
**Se necesitan 10 términos.** (El valor exacto es $\pi^2/12\approx0.8225$, error $\approx0.0045<0.01$.)

---

## 7. Convergencia absoluta y condicional

**Definiciones (Stewart, 11.6).**
- $\sum a_n$ es **absolutamente convergente** si $\sum|a_n|$ converge.
- $\sum a_n$ es **condicionalmente convergente** si converge pero $\sum|a_n|$ diverge.

**Teorema.** Toda serie absolutamente convergente es convergente.

**Procedimiento:** (1) estudiar $\sum|a_n|$; si converge, la serie es absolutamente convergente. (2) Si no, probar si $\sum a_n$ converge (por ejemplo, con la serie alternante): si converge, es condicional; si no, diverge.

### Ejercicio 7.1
Clasifique $\displaystyle\sum_{n=1}^{\infty}\frac{(-1)^n}{n^2}$.

**Solución.** $\sum\left|\dfrac{(-1)^n}{n^2}\right|=\sum\dfrac1{n^2}$ converge ($p=2$). La serie es **absolutamente convergente**.

---

### Ejercicio 7.2
Clasifique $\displaystyle\sum_{n=1}^{\infty}\frac{(-1)^{n-1}}{\sqrt n}$.

**Solución.**
- *Valor absoluto:* $\sum\frac1{\sqrt n}$ es serie $p$ con $p=\tfrac12\le1$: **diverge**. No es absolutamente convergente.
- *Serie alternante:* $b_n=\frac1{\sqrt n}$ decrece y tiende a 0: **converge**.

**Conclusión:** **condicionalmente convergente**.

---

### Ejercicio 7.3
Clasifique $\displaystyle\sum_{n=1}^{\infty}\frac{\cos n}{n^2}$.

**Solución.** Esta serie **no es alternante** (el signo de $\cos n$ cambia sin patrón). Usamos el valor absoluto:
$$\left|\frac{\cos n}{n^2}\right|\le\frac1{n^2}.$$
Como $\sum\frac1{n^2}$ converge, por comparación $\sum\left|\frac{\cos n}{n^2}\right|$ converge. La serie es **absolutamente convergente** (y por tanto convergente).

---

### Ejercicio 7.4
Clasifique $\displaystyle\sum_{n=1}^{\infty}(-1)^n\frac{n}{n^2+1}$.

**Solución.**
- *Valor absoluto:* $\dfrac n{n^2+1}$. Comparación en el límite con $b_n=\dfrac1n$:
$$\lim\frac{n/(n^2+1)}{1/n}=\lim\frac{n^2}{n^2+1}=1.$$
$\sum\frac1n$ diverge, así que $\sum|a_n|$ diverge.
- *Alternante:* $b_n=\frac n{n^2+1}\to0$. Además $f(x)=\frac{x}{x^2+1}$ tiene $f'(x)=\frac{1-x^2}{(x^2+1)^2}\le0$ para $x\ge1$ ✔.

**Conclusión:** **condicionalmente convergente**.

---

### Ejercicio 7.5
Clasifique $\displaystyle\sum_{n=2}^{\infty}\frac{(-1)^n}{\ln n}$.

**Solución.**
- *Valor absoluto:* para $n\ge2$, $\ln n<n$, luego $\dfrac1{\ln n}>\dfrac1n>0$. Como $\sum\frac1n$ diverge, $\sum\frac1{\ln n}$ diverge.
- *Alternante:* $b_n=\frac1{\ln n}$ decrece (porque $\ln n$ crece) y $\to0$ ✔.

**Conclusión:** **condicionalmente convergente**.

---

## 8. Criterio de la razón (cociente)

**Enunciado (Stewart, 11.6).** Sea $\displaystyle L=\lim_{n\to\infty}\left|\frac{a_{n+1}}{a_n}\right|$.

- Si $L<1$: la serie es **absolutamente convergente** (y por tanto convergente).
- Si $L>1$ (incluye $L=\infty$): la serie **diverge**.
- Si $L=1$: el criterio **no concluye**.

**Cuándo usarlo:** factoriales ($n!$), potencias $c^n$, productos. **No sirve** para series racionales como $\sum\frac1{n^p}$ (siempre da $L=1$).

**Recordatorio:** $(n+1)!=(n+1)\,n!$ y $\displaystyle\lim_{n\to\infty}\left(1+\frac1n\right)^n=e$.

### Ejercicio 8.1
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{n}{3^n}$ converge.

**Solución.**
$$\left|\frac{a_{n+1}}{a_n}\right|=\frac{(n+1)/3^{n+1}}{n/3^n}=\frac{n+1}{n}\cdot\frac13\xrightarrow[n\to\infty]{}\frac13.$$
$L=\tfrac13<1$: **converge** absolutamente.

---

### Ejercicio 8.2
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{2^n}{n!}$ converge.

**Solución.**
$$\frac{a_{n+1}}{a_n}=\frac{2^{n+1}}{(n+1)!}\cdot\frac{n!}{2^n}=\frac{2}{n+1}\to0.$$
$L=0<1$: **converge**.

---

### Ejercicio 8.3
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{n!}{100^n}$ converge.

**Solución.**
$$\frac{a_{n+1}}{a_n}=\frac{(n+1)!}{100^{n+1}}\cdot\frac{100^n}{n!}=\frac{n+1}{100}\to\infty.$$
$L=\infty>1$: **diverge**.

---

### Ejercicio 8.4
Clasifique $\displaystyle\sum_{n=1}^{\infty}(-1)^n\frac{n^3}{3^n}$.

**Solución.**
$$\left|\frac{a_{n+1}}{a_n}\right|=\frac{(n+1)^3}{3^{n+1}}\cdot\frac{3^n}{n^3}=\frac13\left(\frac{n+1}{n}\right)^3\to\frac13.$$
$L=\tfrac13<1$: **absolutamente convergente**.

---

### Ejercicio 8.5
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{n^n}{n!}$ converge.

**Solución.**
$$\frac{a_{n+1}}{a_n}=\frac{(n+1)^{n+1}}{(n+1)!}\cdot\frac{n!}{n^n}=\frac{(n+1)^{n+1}}{(n+1)\,n^n}=\frac{(n+1)^n}{n^n}=\left(1+\frac1n\right)^n\to e.$$
$L=e>1$: **diverge**.

---

### Ejercicio 8.6
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{(n!)^2}{(2n)!}$ converge.

**Solución.** Usamos $(2n+2)!=(2n+2)(2n+1)(2n)!$:
$$\frac{a_{n+1}}{a_n}=\frac{((n+1)!)^2}{(2n+2)!}\cdot\frac{(2n)!}{(n!)^2}=\frac{(n+1)^2}{(2n+2)(2n+1)}=\frac{n+1}{2(2n+1)}\to\frac14.$$
$L=\tfrac14<1$: **converge**.

---

### Ejercicio 8.7 (cuando el criterio no concluye)
Aplique el criterio de la razón a $\sum\frac1n$ y a $\sum\frac1{n^2}$. ¿Qué observa?

**Solución.**
- $\dfrac{1/(n+1)}{1/n}=\dfrac n{n+1}\to1$.
- $\dfrac{1/(n+1)^2}{1/n^2}=\left(\dfrac n{n+1}\right)^2\to1$.

En ambas $L=1$, pero la primera diverge y la segunda converge. **Con $L=1$ no se puede concluir:** hay que usar otro criterio.

---

## 9. Criterio de la raíz

**Enunciado (Stewart, 11.6).** Sea $\displaystyle L=\lim_{n\to\infty}\sqrt[n]{|a_n|}$.

- Si $L<1$: **absolutamente convergente**.
- Si $L>1$ (incluye $\infty$): **diverge**.
- Si $L=1$: **no concluye**.

**Cuándo usarlo:** cuando $a_n$ está **elevado a la $n$** (o a un múltiplo de $n$).

**Límites útiles:** $\displaystyle\lim_{n\to\infty}\sqrt[n]{n}=1$, $\displaystyle\lim_{n\to\infty}\left(1+\frac cn\right)^n=e^c$.

### Ejercicio 9.1
Determine si $\displaystyle\sum_{n=1}^{\infty}\left(\frac{2n+3}{3n+2}\right)^n$ converge.

**Solución.**
$$\sqrt[n]{|a_n|}=\frac{2n+3}{3n+2}\to\frac23<1.$$
**Converge** absolutamente.

---

### Ejercicio 9.2
Determine si $\displaystyle\sum_{n=1}^{\infty}\left(\frac{n}{n+1}\right)^{n^2}$ converge.

**Solución.**
$$\sqrt[n]{a_n}=\left(\frac n{n+1}\right)^{n}=\frac{1}{\left(1+\frac1n\right)^n}\to\frac1e<1.$$
**Converge**.

---

### Ejercicio 9.3
Determine si $\displaystyle\sum_{n=1}^{\infty}\left(1+\frac2n\right)^{n^2}$ converge.

**Solución.**
$$\sqrt[n]{a_n}=\left(1+\frac2n\right)^{n}\to e^2>1.$$
**Diverge**.

---

### Ejercicio 9.4
Determine si $\displaystyle\sum_{n=2}^{\infty}\frac{1}{(\ln n)^n}$ converge.

**Solución.**
$$\sqrt[n]{a_n}=\frac1{\ln n}\to0<1.$$
**Converge**.

---

### Ejercicio 9.5
Determine si $\displaystyle\sum_{n=1}^{\infty}(\arctan n)^n$ converge.

**Solución.** $\sqrt[n]{a_n}=\arctan n\to\dfrac\pi2\approx1.57>1$. **Diverge**.

---

### Ejercicio 9.6
Determine si $\displaystyle\sum_{n=1}^{\infty}\frac{2^n}{n^n}$ converge.

**Solución.** $\sqrt[n]{a_n}=\dfrac2n\to0<1$. **Converge**.

---

## 10. Ejercicios integradores: ¿qué criterio usar?

Para cada serie, decida el criterio más conveniente y concluya. (Respuesta y justificación abajo de cada una.)

### 10.1
$\displaystyle\sum_{n=1}^{\infty}\frac{n^2}{n^3+1}$

**Criterio:** comparación en el límite con $b_n=\frac1n$ (se ve como cociente de polinomios).
$$\lim\frac{n^2/(n^3+1)}{1/n}=\lim\frac{n^3}{n^3+1}=1.$$
$\sum\frac1n$ diverge, entonces **diverge**.

### 10.2
$\displaystyle\sum_{n=1}^{\infty}\frac{3^n}{n\,2^n}$

**Criterio:** divergencia o razón. Aquí $\dfrac{3^n}{n2^n}=\dfrac{(3/2)^n}{n}\to\infty$ (la exponencial gana), así que $a_n\not\to0$ y **diverge**.
(Con razón: $\left|\frac{a_{n+1}}{a_n}\right|=\frac32\cdot\frac n{n+1}\to\frac32>1$. Mismo resultado.)

### 10.3 
$\displaystyle\sum_{n=2}^{\infty}\frac{(-1)^n}{\ln n}$

**Criterio:** alternante + valor absoluto. Es **condicionalmente convergente** (ver ejercicio 7.5).

### 10.4 
$\displaystyle\sum_{n=1}^{\infty}\frac{2n+1}{n^3+n}$

**Criterio:** comparación en el límite con $b_n=\frac1{n^2}$ (dominante: $\frac{2n}{n^3}$).
$$\lim\frac{(2n+1)/(n^3+n)}{1/n^2}=\lim\frac{2n^3+n^2}{n^3+n}=2.$$
$\sum\frac1{n^2}$ converge, entonces **converge**.

### 10.5
$\displaystyle\sum_{n=1}^{\infty}\left(\frac{n}{2n+1}\right)^n$

**Criterio:** raíz. $\sqrt[n]{a_n}=\dfrac n{2n+1}\to\dfrac12<1$. **Converge**.

### 10.6 
$\displaystyle\sum_{n=1}^{\infty}\frac{n!}{n^n}$

**Criterio:** razón.
$$\frac{a_{n+1}}{a_n}=\frac{(n+1)!}{(n+1)^{n+1}}\cdot\frac{n^n}{n!}=\frac{n^n}{(n+1)^n}=\frac1{(1+1/n)^n}\to\frac1e<1.$$
**Converge**.

### 10.7
$\displaystyle\sum_{n=1}^{\infty}\frac{1}{n\sqrt n}\cos\!\left(\frac{n\pi}{4}\right)$

**Criterio:** convergencia absoluta + comparación. $\left|\dfrac{\cos(n\pi/4)}{n^{3/2}}\right|\le\dfrac1{n^{3/2}}$, y $\sum n^{-3/2}$ converge ($p=\tfrac32$). **Absolutamente convergente.**

---

## 11. Tabla resumen y errores frecuentes

### Tabla resumen

| Criterio | Se aplica a | Conclusión | Cuándo falla (no concluye) |
|---|---|---|---|
| Definición ($s_n$) | Telescópicas, geométricas | $\lim s_n$ finito: converge | Si no se halla fórmula cerrada para $s_n$ |
| Divergencia | Cualquiera | $\lim a_n\ne0$ o no existe: **diverge** | Si $\lim a_n=0$ |
| Geométrica | $\sum ar^{n-1}$ | Converge si $\lvert r\rvert<1$, suma $\frac a{1-r}$ | Nunca falla (si $\lvert r\rvert\ge1$ diverge) |
| Serie $p$ | $\sum\frac1{n^p}$ | Converge si $p>1$ | Nunca falla |
| Comparación | Términos $>0$ | $a_n\le b_n$ con $\sum b_n$ conv.: converge; $a_n\ge b_n$ con $\sum b_n$ div.: diverge | Si la desigualdad va al revés |
| Comparación en el límite | Términos $>0$ | $\lim\frac{a_n}{b_n}=c\in(0,\infty)$: mismo comportamiento | Si $c=0$ o $c=\infty$ |
| Integral | $a_n=f(n)$, $f$ continua, $>0$, decreciente | Igual comportamiento que $\int^\infty f$ | Si $f$ no es decreciente o la integral es muy difícil |
| Serie alternante | $\sum(-1)^{n-1}b_n$ | $b_n$ decrece y $\to0$: converge | Si $b_n\not\to0$ (diverge por divergencia) |
| Razón | Factoriales, $c^n$ | $L<1$ conv. abs.; $L>1$ diverge | $L=1$ |
| Raíz | $a_n$ elevado a la $n$ | $L<1$ conv. abs.; $L>1$ diverge | $L=1$ |

### Errores frecuentes

1. **"$a_n\to0$, entonces converge."** Falso. Contraejemplos: $\sum\frac1n$ y $\sum\ln\frac{n}{n+1}$.
2. **Comparar en el sentido equivocado.** Estar *por encima* de una serie convergente no dice nada; estar *por encima* de una divergente sí.
3. **Usar el criterio de la integral sin verificar hipótesis.** Debe ser continua, positiva y *decreciente*.
4. **Creer que el valor de la integral es la suma.** Solo da información sobre convergencia.
5. **Aplicar la serie alternante sin revisar que $b_n$ decrezca.** También hay que verificar $b_n\to0$.
6. **Usar razón o raíz en series racionales** ($\sum\frac{1}{n^p}$): siempre dan $L=1$.
7. **Olvidar el valor absoluto** en razón y raíz.
8. **Con $L=1$, concluir convergencia o divergencia.** No se puede: cambie de criterio.
9. **Confundir convergencia absoluta con condicional.** Condicional significa que converge pero $\sum|a_n|$ diverge.
10. **Sumar series geométricas con $|r|\ge1$** usando la fórmula $\frac a{1-r}$. Solo es válida si $|r|<1$.

---

*Fin del taller.*
