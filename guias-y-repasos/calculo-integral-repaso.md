# Banco de Preguntas: Taller Intensivo de Cálculo Integral 


## MÓDULO 1: TEOREMA FUNDAMENTAL DEL CÁLCULO - PARTE 1 (2 Ejercicios)

  

### Pregunta 1

  

**Enunciado:** Utilice la Parte 1 del Teorema Fundamental del Cálculo para encontrar la derivada de $F(x) = \int_{x}^{0} \sqrt{1 + \sec(t)} \, dt$ (Numeral 11).

  

* **Opción A:** $F'(x) = \sqrt{1 + \sec(x)}$

  

* **Opción B:** $F'(x) = -\sqrt{1 + \sec(x)}$

  

* **Opción C:** $F'(x) = \frac{\sec(x)\tan(x)}{2\sqrt{1 + \sec(x)}}$

  

* **Opción D:** $F'(x) = -\frac{1}{\sqrt{1 + \sec(x)}}$

  

**Respuesta Correcta:** Opción B

  

**Explicación:** Por propiedades de las integrales definidas, se invierten los límites de integración agregando un signo negativo: $F(x) = -\int_{0}^{x} \sqrt{1 + \sec(t)} \, dt$. Aplicando directamente la Parte 1 del TFC ($\frac{d}{dx}\left[\int_{a}^{x} f(t) dt\right] = f(x)$), se obtiene $F'(x) = -\sqrt{1 + \sec(x)}$.

  

### Pregunta 2

  

**Enunciado:** Encuentre la derivada de la función $h(x) = \int_{1}^{e^x} \ln(t) \, dt$ usando el Teorema Fundamental del Cálculo y la regla de la cadena (Numeral 13).

  

* **Opción A:** $h'(x) = x e^x$

  

* **Opción B:** $h'(x) = x$

  

* **Opción C:** $h'(x) = \ln(e^x) = x$

  

* **Opción D:** $h'(x) = e^x \ln(x)$

  

**Respuesta Correcta:** Opción A

  

**Explicación:** Aplicando la Parte 1 del TFC junto con la regla de la cadena: $\frac{d}{dx}\left[\int_{a}^{g(x)} f(t) dt\right] = f(g(x)) \cdot g'(x)$. Aquí $g(x) = e^x$, $g'(x) = e^x$ y $f(t) = \ln(t)$. Así, $h'(x) = \ln(e^x) \cdot e^x = x \cdot e^x$.

  

---

  

## MÓDULO 2: INTEGRALES IMPROPIAS (3 Ejercicios)

  

### Pregunta 3

  

**Enunciado:** Determine si la integral impropia de **Tipo 1** $\int_{1}^{\infty} \frac{\ln(x)}{x^2} \, dx$ converge o diverge. Si converge, halle su valor.

  

* **Opción A:** Converge a $1$

  

* **Opción B:** Diverge

  

* **Opción C:** Converge a $0$

  

* **Opción D:** Converge a $e$

  

**Respuesta Correcta:** Opción A

  

**Explicación:** Se plantea como el límite $\lim_{t \to \infty} \int_{1}^{t} \frac{\ln(x)}{x^2} \, dx$. Aplicando integración por partes con $u = \ln(x)$ y $dv = x^{-2} \, dx$, la antiderivada es $-\frac{\ln(x)}{x} - \frac{1}{x}$. Evaluando de $1$ a $t$ y tomando el límite cuando $t \to \infty$, el primer término tiende a $0$ (por regla de L'Hôpital) y queda $0 - (-1) = 1$.

  

### Pregunta 4

  

**Enunciado:** Analice la integral impropia de **Tipo 2** $\int_{-2}^{3} \frac{1}{x^4} \, dx$. ¿Cuál es su comportamiento?

  

* **Opción A:** Converge a $\frac{35}{24}$

  

* **Opción B:** Converge a $0$

  

* **Opción C:** Diverge

  

* **Opción D:** Converge a $-\frac{1}{24}$

  

**Respuesta Correcta:** Opción C

  

**Explicación:** La función $f(x) = \frac{1}{x^4}$ no está definida en $x = 0$, que pertenece al interior del intervalo $[-2, 3]$. Por ello, se divide en dos integrales: $\int_{-2}^{0} \frac{1}{x^4} \, dx + \int_{0}^{3} \frac{1}{x^4} \, dx$. Evaluando el límite de la primera parte: $\lim_{t \to 0^-} \left[ -\frac{1}{3x^3} \right]_{-2}^{t} = +\infty$. Como una de sus partes diverge, la integral completa diverge.

  

### Pregunta 5

  

**Enunciado:** Evalúe la integral impropia de **Tipo Mixto** $\int_{0}^{1} \frac{e^{1/x}}{x^3} \, dx$.

  

* **Opción A:** Diverge

  

* **Opción B:** Converge a $e$

  

* **Opción C:** Converge a $1$

  

* **Opción D:** Converge a $0$

  

**Respuesta Correcta:** Opción A

  

**Explicación:** La función tiene una asíntota vertical en $x = 0^+$. Al hacer la sustitución $u = \frac{1}{x}$ ($du = -\frac{1}{x^2} dx$), los límites cambian: cuando $x \to 0^+$, $u \to \infty$; cuando $x = 1$, $u = 1$. La integral se transforma en una integral de Tipo 1: $\int_{1}^{\infty} u e^u \, du$. Integrando por partes da $[(u-1)e^u]_{1}^{\infty}$, cuyo límite tiende a $+\infty$, por lo que diverge.

  

---

  

## MÓDULO 3: ÁREAS ENTRE CURVAS (2 Ejercicios)

  

### Pregunta 6

  

**Enunciado:** Calcule el área de la región acotada por las parábolas $y = x^2$ y $y = 4x - x^2$.

  

* **Opción A:** $\frac{8}{3}$

  

* **Opción B:** $\frac{16}{3}$

  

* **Opción C:** $4$

  

* **Opción D:** $\frac{32}{3}$

  

**Respuesta Correcta:** Opción A

  

**Explicación:** Igualando las curvas $x^2 = 4x - x^2 \Rightarrow 2x^2 - 4x = 0$, los puntos de intersección son $x = 0$ y $x = 2$. En este intervalo, $4x - x^2 \ge x^2$. El área se calcula como $\int_{0}^{2} [(4x - x^2) - x^2] \, dx = \int_{0}^{2} (4x - 2x^2) \, dx = \left[ 2x^2 - \frac{2}{3}x^3 \right]_{0}^{2} = 8 - \frac{16}{3} = \frac{8}{3}$.

  

### Pregunta 7

  

**Enunciado:** Encuentre el área de la región acotada por la parábola $x = y^2 - 4y$ y la curva $x = 2y - y^2$, integrando respecto a $y$.

  

* **Opción A:** $9$

  

* **Opción B:** $18$

  

* **Opción C:** $\frac{27}{2}$

  

* **Opción D:** $\frac{81}{2}$

  

**Respuesta Correcta:** Opción A

  

**Explicación:** Igualando respecto a $y$: $y^2 - 4y = 2y - y^2 \Rightarrow 2y^2 - 6y = 0$, por lo que los límites son $y = 0$ y $y = 3$. La curva situada a la derecha es $x = 2y - y^2$. El área es $\int_{0}^{3} [(2y - y^2) - (y^2 - 4y)] \, dy = \int_{0}^{3} (6y - 2y^2) \, dy = \left[ 3y^2 - \frac{2}{3}y^3 \right]_{0}^{3} = 27 - 18 = 9$.

  

---

  

## MÓDULO 4: VOLÚMENES DE REVOLUCIÓN (2 Ejercicios)

  

### Pregunta 8

  

**Enunciado:** Determine el volumen del sólido al girar alrededor de la recta $y = -1$ la región entre $y = \sin(x)$ y $y = \cos(x)$ para $0 \le x \le \pi/4$.

  

* **Opción A:** $\sqrt{2}\pi$

  

* **Opción B:** $2\sqrt{2}\pi$

  

* **Opción C:** $\pi(\sqrt{2} + 1)$

  

* **Opción D:** $\frac{\sqrt{2}\pi}{2}$

  

**Respuesta Correcta:** Opción A

  

**Explicación:** Con el eje de giro $y = -1$, se aplica el método de arandelas. El radio mayor es $R(x) = \cos(x) + 1$ y el radio menor es $r(x) = \sin(x) + 1$. El volumen es $V = \pi \int_{0}^{\pi/4} [(\cos x + 1)^2 - (\sin x + 1)^2] \, dx = \pi \int_{0}^{\pi/4} [\cos(2x) + 2\cos x - 2\sin x] \, dx$. Evaluando da $\pi \left[ \frac{1}{2}\sin(2x) + 2\sin x + 2\cos x \right]_{0}^{\pi/4} = \sqrt{2}\pi$.

  

### Pregunta 9

  

**Enunciado:** Calcule el volumen del sólido generado al rotar la región entre $y = x^3$, $y = 0$, y $x = 1$ alrededor del eje $x = 2$.

  

* **Opción A:** $\frac{3\pi}{5}$

  

* **Opción B:** $\frac{7\pi}{5}$

  

* **Opción C:** $\frac{3\pi}{10}$

  

* **Opción D:** $\frac{4\pi}{5}$

  

**Respuesta Correcta:** Opción A

  

**Explicación:** Se aplica el método de cascarones cilíndricos. Como el eje es $x = 2$ y la región está entre $x = 0$ y $x = 1$, el radio del cascarón es $r(x) = 2 - x$ y la altura es $h(x) = x^3$. El volumen es $V = 2\pi \int_{0}^{1} (2 - x)x^3 \, dx = 2\pi \int_{0}^{1} (2x^3 - x^4) \, dx = 2\pi \left[ \frac{x^4}{2} - \frac{x^5}{5} \right]_{0}^{1} = 2\pi \left( \frac{1}{2} - \frac{1}{5} \right) = \frac{3\pi}{5}$.

  

---

  

## MÓDULO 5: LONGITUD DE ARCO Y SUPERFICIES (2 Ejercicios)

  

### Pregunta 10

  

**Enunciado:** Encuentre la longitud de arco exacta de la curva $y = \frac{x^3}{3} + \frac{1}{4x}$ en el intervalo $1 \le x \le 2$.

  

* **Opción A:** $\frac{33}{16}$

  

* **Opción B:** $\frac{59}{24}$

  

* **Opción C:** $\frac{31}{12}$

  

* **Opción D:** $\frac{17}{8}$

  

**Respuesta Correcta:** Opción B

  

**Explicación:** La derivada es $y' = x^2 - \frac{1}{4x^2}$. Dentro del radical se forma $1 + (y')^2 = \left(x^2 + \frac{1}{4x^2}\right)^2$. Simplificando la raíz: $L = \int_{1}^{2} \left(x^2 + \frac{1}{4x^2}\right) dx = \left[ \frac{x^3}{3} - \frac{1}{4x} \right]_{1}^{2} = \frac{59}{24}$.

  

### Pregunta 11

  

**Enunciado:** Determine el área de la superficie obtenida al girar la curva $y = \sqrt{5 - x}$ ($3 \le x \le 5$) alrededor del eje $x$.

  

* **Opción A:** $\frac{\pi}{6}(9\sqrt{3} - 1)$

  

* **Opción B:** $\frac{4\pi}{3}$

  

* **Opción C:** $\frac{\pi}{6}(9\sqrt{3})$

  

* **Opción D:** $\frac{5\pi}{3}$

  

**Respuesta Correcta:** Opción A

  

**Explicación:** La fórmula es $S = 2\pi \int y \sqrt{1 + (y')^2} \, dx$. Con $y' = \frac{-1}{2\sqrt{5-x}}$, tenemos $\sqrt{1 + (y')^2} = \sqrt{\frac{21-4x}{4(5-x)}}$. Simplificando con $y = \sqrt{5-x}$, la integral queda $S = \pi \int_{3}^{5} \sqrt{21-4x} \, dx$, cuyo resultado es $\frac{\pi}{6}(9\sqrt{3} - 1)$.