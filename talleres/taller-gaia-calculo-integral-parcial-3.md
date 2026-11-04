<table style="border: none; width: 100%; background-color: transparent;">
  <tr style="border: none; background-color: transparent;">
    <td style="border: none; width: 15%; text-align: center; vertical-align: middle;">
      <!-- Logo de la UPB desde internet -->
      <img src="https://thumb.wikimedia.org/wikipedia/commons/thumb/e/e4/Logos%C3%ADmbolo_UPB.svg/960px-Logos%C3%ADmbolo_UPB.svg.png?utm_source=es.wikipedia.org&utm_campaign=index&utm_content=thumbnail" alt="Logo UPB" width="200"/>
    </td>
    <td style="border: none; width: 85%; text-align: left; vertical-align: middle; padding-left: 20px;">
      <h1 style="margin: 0; font-size: 1.8em; border-bottom: none;">Universidad Pontificia Bolivariana</h1>
      <h2 style="margin: 5px 0; font-size: 1.4em; border-bottom: none; color: #888888;">Taller GAIA: Preparación Parcial #3 de Cálculo Integral</h2>
      <p style="margin: 5px 0 0 0; font-size: 1.1em;"><strong>Monitor:</strong> Thomas Sining Salazar</p>
    </td>
  </tr>
</table>

---

## MÓDULO 1: Teorema Fundamental del Cálculo (Parte 1)

### **Ejercicio 1**

Dada la función:

$$G(x) = \int_{\sqrt{x}}^{x^2} \frac{\cos(t)}{t} \, dt \quad \text{para } x > 0$$

Calcule $G'(x)$ detallando absolutamente todas las propiedades y pasos algebraicos.

#### **Solución Paso a Paso:**

1. **Comprensión teórica:** El Teorema Fundamental del Cálculo Parte 1 (TFC1) establece que si $F(x) = \int_{a}^{x} f(t) dt$, entonces $F'(x) = f(x)$. Cuando el límite superior es una función $u(x)$, aplicamos la Regla de la Cadena:
    
    $$\frac{d}{dx} \left[ \int_{a}^{u(x)} f(t) \, dt \right] = f(u(x)) \cdot u'(x)$$
2. **Descomposición del intervalo mediante un punto intermedio:** Para tener una sola variable por límite de integración, elegimos un punto arbitrario $a$ constante ($a > 0$) y dividimos la integral utilizando la propiedad de aditividad del intervalo:
    
    $$G(x) = \int_{\sqrt{x}}^{a} \frac{\cos(t)}{t} \, dt + \int_{a}^{x^2} \frac{\cos(t)}{t} \, dt$$
3. **Inversión de los límites de integración:** Por la propiedad $\int_{b}^{a} f(t) dt = -\int_{a}^{b} f(t) dt$, invertimos el primer término para que la variable quede arriba:
    
    $$G(x) = -\int_{a}^{\sqrt{x}} \frac{\cos(t)}{t} \, dt + \int_{a}^{x^2} \frac{\cos(t)}{t} \, dt$$
4. **Identificación formal de componentes:** Sea $f(t) = \frac{\cos(t)}{t}$.
    
    - **Primer término:** $-\int_{a}^{u_1(x)} f(t) \, dt$ con $u_1(x) = \sqrt{x} = x^{1/2}$.
        
        - Derivada de $u_1(x)$:
            
            $$u_1'(x) = \frac{1}{2} x^{\frac{1}{2} - 1} = \frac{1}{2} x^{-1/2} = \frac{1}{2\sqrt{x}}$$
        - Evaluación de $f(u_1(x))$:
            
            $$f(\sqrt{x}) = \frac{\cos(\sqrt{x})}{\sqrt{x}}$$
    - **Segundo término:** $\int_{a}^{u_2(x)} f(t) \, dt$ con $u_2(x) = x^2$.
        
        - Derivada de $u_2(x)$:
            
            $$u_2'(x) = 2x^{2-1} = 2x$$
        - Evaluación de $f(u_2(x))$:
            
            $$f(x^2) = \frac{\cos(x^2)}{x^2}$$
5. **Derivación término a término:**
    
    $$G'(x) = -\left[ f(u_1(x)) \cdot u_1'(x) \right] + \left[ f(u_2(x)) \cdot u_2'(x) \right]$$$$G'(x) = -\left[ \frac{\cos(\sqrt{x})}{\sqrt{x}} \cdot \frac{1}{2\sqrt{x}} \right] + \left[ \frac{\cos(x^2)}{x^2} \cdot 2x \right]$$
6. **Pasos detallados de simplificación algebraica:**
    
    - Multiplicación del primer bloque:
        
        $$\frac{\cos(\sqrt{x})}{\sqrt{x}} \cdot \frac{1}{2\sqrt{x}} = \frac{\cos(\sqrt{x}) \cdot 1}{\sqrt{x} \cdot 2\sqrt{x}} = \frac{\cos(\sqrt{x})}{2 (\sqrt{x})^2} = \frac{\cos(\sqrt{x})}{2x}$$
    - Multiplicación del segundo bloque:
        
        $$\frac{\cos(x^2)}{x^2} \cdot 2x = \frac{2x \cos(x^2)}{x^2} = \frac{2 \cos(x^2)}{x}$$
    - Uniendo ambos resultados:
        
        $$G'(x) = -\frac{\cos(\sqrt{x})}{2x} + \frac{2\cos(x^2)}{x}$$
    - Llevando a un común denominador ($2x$):
        
        $$\frac{2\cos(x^2)}{x} = \frac{2\cos(x^2) \cdot 2}{x \cdot 2} = \frac{4\cos(x^2)}{2x}$$$$G'(x) = \frac{- \cos(\sqrt{x}) + 4\cos(x^2)}{2x} = \frac{4\cos(x^2) - \cos(\sqrt{x})}{2x}$$

## MÓDULO 2: Integrales Impropias

### **Ejercicio 2: Tipo 1 (Límites Infinitos)**

Determine la convergencia o divergencia de la siguiente integral:

$$\int_{-\infty}^{0} z e^{2z} \, dz$$

#### **Solución Paso a Paso:**

1. **Planteamiento con límite:** Dado que el límite inferior es $-\infty$, es una integral impropia de Tipo 1. Reemplazamos $-\infty$ por $t$:
    
    $$\int_{-\infty}^{0} z e^{2z} \, dz = \lim_{t \to -\infty} \int_{t}^{0} z e^{2z} \, dz$$
2. **Cálculo de la integral indefinida por partes:** Fórmula: $\int u \, dv = u v - \int v \, du$  
    
    - Elegimos $u = z \implies \frac{du}{dz} = 1 \implies du = dz$  
        
    - Elegimos $dv = e^{2z} dz \implies v = \int e^{2z} dz = \frac{1}{2}e^{2z}$  
        
    
    Sustituyendo en la fórmula:
    
    $$\int z e^{2z} \, dz = (z) \left( \frac{1}{2}e^{2z} \right) - \int \left( \frac{1}{2}e^{2z} \right) dz$$$$= \frac{1}{2}z e^{2z} - \frac{1}{2} \int e^{2z} \, dz$$$$= \frac{1}{2}z e^{2z} - \frac{1}{2} \left( \frac{1}{2} e^{2z} \right) = \frac{1}{2}z e^{2z} - \frac{1}{4}e^{2z}$$
3. **Evaluación de la integral definida entre** $t$ **y** $0$**:**
    
    $$\left[ \frac{1}{2}z e^{2z} - \frac{1}{4}e^{2z} \right]_{t}^{0} = \text{Evaluación en } 0 - \text{Evaluación en } t$$
    
    - En $z = 0$:
        
        $$\frac{1}{2}(0)e^{2(0)} - \frac{1}{4}e^{2(0)} = 0 - \frac{1}{4}(1) = -\frac{1}{4}$$
    - En $z = t$:
        
        $$\frac{1}{2}t e^{2t} - \frac{1}{4}e^{2t}$$
    
    Resta:
    
    $$\int_{t}^{0} z e^{2z} \, dz = -\frac{1}{4} - \left( \frac{1}{2}t e^{2t} - \frac{1}{4}e^{2t} \right) = -\frac{1}{4} - \frac{1}{2}t e^{2t} + \frac{1}{4}e^{2t}$$
4. **Paso a paso del límite cuando** $t \to -\infty$**:**
    
    $$\lim_{t \to -\infty} \left( -\frac{1}{4} - \frac{1}{2}t e^{2t} + \frac{1}{4}e^{2t} \right)$$
    - **Término constante:** $\lim_{t \to -\infty} \left(-\frac{1}{4}\right) = -\frac{1}{4}$  
        
    - **Término exponencial:** $\lim_{t \to -\infty} \frac{1}{4}e^{2t} = \frac{1}{4} e^{-\infty} = 0$  
        
    - **Término indeterminado:** $\lim_{t \to -\infty} t e^{2t}$ da una indeterminación $(-\infty) \cdot 0$. Reescribimos como fracción:
        
        $$\lim_{t \to -\infty} \frac{t}{e^{-2t}} \quad \left[\text{Forma } \frac{-\infty}{\infty}\right]$$
        
        Aplicamos Regla de L'Hôpital (derivando numerador y denominador respecto a $t$):
        
        $$\frac{d}{dt}(t) = 1$$$$\frac{d}{dt}(e^{-2t}) = -2e^{-2t}$$$$\lim_{t \to -\infty} \frac{1}{-2e^{-2t}} = \frac{1}{-2 e^{+\infty}} = \frac{1}{-\infty} = 0$$
5. **Conclusión final:**
    
    $$\text{Resultado} = -\frac{1}{4} - \frac{1}{2}(0) + 0 = -\frac{1}{4}$$
    
    **La integral impropia converge a** $-\frac{1}{4}$**.**
    

### **Ejercicio 3: Tipo 2 (Discontinuidad Infinita)**

Evalúe la siguiente integral impropia:

$$\int_{0}^{1} \frac{dx}{\sqrt{1 - x^2}}$$

1. **Análisis de la impropiedad:** Evaluando el integrando $f(x) = \frac{1}{\sqrt{1 - x^2}}$ en el límite superior $x = 1$:
    
    $$f(1) = \frac{1}{\sqrt{1 - 1^2}} = \frac{1}{\sqrt{0}} = \frac{1}{0} \quad (\text{Indefinido / Asíntota Vertical})$$
2. **Formulación con límite:** Como la discontinuidad está en $x = 1$, aproximamos desde la izquierda ($t \to 1^-$):
    
    $$\int_{0}^{1} \frac{dx}{\sqrt{1 - x^2}} = \lim_{t \to 1^-} \int_{0}^{t} \frac{dx}{\sqrt{1 - x^2}}$$
3. **Integración indefinida:** Recordemos la fórmula directa de la derivada de las funciones trigonométricas inversas:
    
    $$\frac{d}{dx}[\arcsin(x)] = \frac{1}{\sqrt{1 - x^2}} \implies \int \frac{dx}{\sqrt{1 - x^2}} = \arcsin(x)$$
4. **Evaluación de la integral definida:**
    
    $$\int_{0}^{t} \frac{dx}{\sqrt{1 - x^2}} = [\arcsin(x)]_{0}^{t} = \arcsin(t) - \arcsin(0)$$
    
    - $\arcsin(0) = 0$ (ya que $\sin(0) = 0$).
        
    
    Por lo tanto, queda $\arcsin(t)$.
    
5. **Cálculo del límite:**
    
    $$\lim_{t \to 1^-} \arcsin(t) = \arcsin(1)$$
    
    Buscamos el ángulo $\theta \in [-\pi/2, \pi/2]$ tal que $\sin(\theta) = 1$. Dicho ángulo es $\frac{\pi}{2}$.
    
6. **Conclusión:** **La integral impropia converge a** $\frac{\pi}{2}$**.**
    

### **Ejercicio 4: Tipo Mixto (Tipo 1 y Tipo 2 a la vez)**

Determine la convergencia o divergencia de:

$$\int_{0}^{\infty} \frac{dx}{x \sqrt{x}}$$

#### **Solución Paso a Paso:**

1. **Reescritura algebraica del integrando:**
    
    $$x \sqrt{x} = x^1 \cdot x^{1/2} = x^{1 + 1/2} = x^{3/2}$$$$\frac{1}{x \sqrt{x}} = \frac{1}{x^{3/2}} = x^{-3/2}$$
2. **Identificación de las dos impropiedades:**
    
    - **Impropiedad de Tipo 2 (en** $x = 0$**):** $\lim_{x \to 0^+} x^{-3/2} = \frac{1}{0} = \infty$.
        
    - **Impropiedad de Tipo 1 (en** $x = \infty$**):** Límite superior infiinito.
        
3. **Partición de la integral:** Separamos el problema en dos integrales independientes en $x = 1$:
    
    $$\int_{0}^{\infty} x^{-3/2} \, dx = \int_{0}^{1} x^{-3/2} \, dx + \int_{1}^{\infty} x^{-3/2} \, dx = I_1 + I_2$$
4. **Análisis detallado de** $I_1$ **(alrededor de 0):**
    
    $$I_1 = \lim_{t \to 0^+} \int_{t}^{1} x^{-3/2} \, dx$$
    - Antiderivada por regla de la potencia:
        
        $$\int x^{-3/2} \, dx = \frac{x^{-3/2 + 1}}{-\frac{3}{2} + 1} = \frac{x^{-1/2}}{-\frac{1}{2}} = -2 x^{-1/2} = -\frac{2}{\sqrt{x}}$$
    - Aplicación de límites de integración:
        
        $$\left[ -\frac{2}{\sqrt{x}} \right]_{t}^{1} = \left( -\frac{2}{\sqrt{1}} \right) - \left( -\frac{2}{\sqrt{t}} \right) = -2 + \frac{2}{\sqrt{t}}$$
    - Aplicando el límite cuando $t \to 0^+$:
        
        $$\lim_{t \to 0^+} \left( -2 + \frac{2}{\sqrt{t}} \right) = -2 + \frac{2}{0^+} = -2 + \infty = +\infty$$
5. **Conclusión:** Dado que $I_1$ da como resultado $+\infty$ (diverge), la suma $I_1 + I_2$ automáticamente diverge sin necesidad de evaluar $I_2$. **La integral impropia completa DIVERGE.**
    

## MÓDULO 3: Áreas entre Curvas

### **Ejercicio 5**

Calcule el área de la región encerrada entre las curvas $x = y^2 - 1$ y $x = 1 - y^2$.

#### **Gráfica de las Regiones:**
![[Pasted image 20260927131956.png|732]]

#### **Solución Paso a Paso:**

1. **Cálculo de los puntos de intersección (Límites en** $y$**):** Igualamos $x_1(y) = x_2(y)$:
    
    $$y^2 - 1 = 1 - y^2$$
    
    Sumamos $y^2$ a ambos lados:
    
    $$y^2 + y^2 - 1 = 1 \implies 2y^2 - 1 = 1$$
    
    Sumamos 1 a ambos lados:
    
    $$2y^2 = 2$$
    
    Dividimos entre 2:
    
    $$y^2 = 1 \implies y = \pm \sqrt{1} \implies y_1 = -1, \quad y_2 = 1$$
2. **Identificación de la función Derecha e Izquierda:** Probamos con un punto en el interior del intervalo $[-1, 1]$, por ejemplo $y = 0$:
    
    - $x_1(0) = 0^2 - 1 = -1$ (Ubicado más a la izquierda).
        
    - $x_2(0) = 1 - 0^2 = 1$ (Ubicado más a la derecha).
        
    
    Por lo tanto:
    
    - $x_{\text{derecha}}(y) = 1 - y^2$  
        
    - $x_{\text{izquierda}}(y) = y^2 - 1$  
        
3. **Planteamiento de la integral de área:**
    
    $$A = \int_{y_1}^{y_2} \left[ x_{\text{derecha}}(y) - x_{\text{izquierda}}(y) \right] \, dy$$$$A = \int_{-1}^{1} \left[ (1 - y^2) - (y^2 - 1) \right] \, dy$$
4. **Destrucción de paréntesis y simplificación:**
    
    $$(1 - y^2) - (y^2 - 1) = 1 - y^2 - y^2 + 1 = 2 - 2y^2$$$$A = \int_{-1}^{1} (2 - 2y^2) \, dy$$
5. **Aprovechamiento de la simetría (Paridad):** La función $f(y) = 2 - 2y^2$ es par pues $f(-y) = 2 - 2(-y)^2 = 2 - 2y^2 = f(y)$.
    
    $$A = 2 \int_{0}^{1} (2 - 2y^2) \, dy$$
6. **Integración término a término:**
    
    $$\int (2 - 2y^2) \, dy = 2y - 2 \left( \frac{y^3}{3} \right) = 2y - \frac{2}{3}y^3$$
7. **Evaluación completa:**
    
    $$A = 2 \left[ 2y - \frac{2}{3}y^3 \right]_{0}^{1} = 2 \left[ \left( 2(1) - \frac{2}{3}(1)^3 \right) - \left( 2(0) - \frac{2}{3}(0)^3 \right) \right]$$$$A = 2 \left[ 2 - \frac{2}{3} \right] = 2 \left[ \frac{6}{3} - \frac{2}{3} \right] = 2 \left[ \frac{4}{3} \right] = \frac{8}{3} \, \text{unidades}^2$$

## MÓDULO 4: Volúmenes de Revolución con Ejes Desplazados

### **Ejercicio 6: Método de Arandelas (Eje Horizontal** $y = 2$**)**

Halle el volumen del sólido generado al rotar la región acotada por $y = x^2$ y $y = x$ alrededor de la recta $y = 2$.

#### **Gráfica de la Región y el Eje de Giro:**
![[Pasted image 20260927131610.png|781]]

.

#### **Solución Paso a Paso:**

1. **Puntos de corte:**
    
    $$x^2 = x \implies x^2 - x = 0 \implies x(x - 1) = 0 \implies x = 0 \quad \text{y} \quad x = 1$$
2. **Construcción de los radios respecto al eje** $y = 2$**:** Como el eje está por encima de la región ($y = 2$):
    
    - **Radio Exterior** $R(x)$**:** Distancia del eje a la curva más distante ($y = x^2$).
        
        $$R(x) = 2 - x^2$$
    - **Radio Interior** $r(x)$**:** Distancia del eje a la curva más cercana ($y = x$).
        
        $$r(x) = 2 - x$$
3. **Planteamiento de la Integral de Arandelas:**
    
    $$V = \pi \int_{a}^{b} \left( [R(x)]^2 - [r(x)]^2 \right) dx = \pi \int_{0}^{1} \left( (2 - x^2)^2 - (2 - x)^2 \right) dx$$
4. **Desarrollo algebraico minucioso de los cuadrados:**
    
    - Cuadrado del Radio Exterior:
        
        $$(2 - x^2)^2 = 2^2 - 2(2)(x^2) + (x^2)^2 = 4 - 4x^2 + x^4$$
    - Cuadrado del Radio Interior:
        
        $$(2 - x)^2 = 2^2 - 2(2)(x) + x^2 = 4 - 4x + x^2$$
    - Resta de cuadrados:
        
        $$[R(x)]^2 - [r(x)]^2 = (4 - 4x^2 + x^4) - (4 - 4x + x^2)$$$$= 4 - 4x^2 + x^4 - 4 + 4x - x^2$$$$= x^4 + (-4x^2 - x^2) + 4x + (4 - 4) = x^4 - 5x^2 + 4x$$
5. **Integración paso a paso:**
    
    $$V = \pi \int_{0}^{1} (x^4 - 5x^2 + 4x) \, dx$$$$\int x^4 \, dx = \frac{x^5}{5}$$$$\int -5x^2 \, dx = -\frac{5x^3}{3}$$$$\int 4x \, dx = \frac{4x^2}{2} = 2x^2$$$$V = \pi \left[ \frac{x^5}{5} - \frac{5x^3}{3} + 2x^2 \right]_{0}^{1}$$
6. **Evaluación numérica final:**
    
    - En $x = 1$:
        
        $$\frac{1^5}{5} - \frac{5(1)^3}{3} + 2(1)^2 = \frac{1}{5} - \frac{5}{3} + 2$$
    - En $x = 0$:
        
        $$0 - 0 + 0 = 0$$
    - Homogeneización de fracciones (mínimo común múltiplo = 15):
        
        $$\frac{1}{5} = \frac{3}{15}, \quad \frac{5}{3} = \frac{25}{15}, \quad 2 = \frac{30}{15}$$$$\frac{3}{15} - \frac{25}{15} + \frac{30}{15} = \frac{3 - 25 + 30}{15} = \frac{8}{15}$$$$V = \frac{8\pi}{15} \, \text{unidades}^3$$

### **Ejercicio 7: Método de Cascarones Cilíndricos (Eje Vertical** $x = -1$**)**

Calcule el volumen del sólido al girar la región acotada por $y = x^2$ y $y = \sqrt{x}$ alrededor de $x = -1$.

#### **Gráfica de la Región:**


![[Pasted image 20260927132239.png|667]]

#### **Solución Paso a Paso:**

1. **Límites de integración:**
    
    $$x^2 = \sqrt{x} \implies x^4 = x \implies x^4 - x = 0 \implies x(x^3 - 1) = 0 \implies x = 0 \quad \text{y} \quad x = 1$$
2. **Identificación de Radio y Altura del Cascarón:**
    
    - **Radio** $R_g(x)$**:** Distancia horizontal desde el eje de giro $x = -1$ hasta un punto arbitrario $x$:
        
        $$r(x) = x - (-1) = x + 1$$
    - **Altura** $h(x)$**:** Distancia vertical entre las funciones superior e inferior:
        
        $$h(x) = y_{\text{superior}} - y_{\text{inferior}} = \sqrt{x} - x^2 = x^{1/2} - x^2$$
3. **Planteamiento de la Integral por Cascarones Cilíndricos:**
    
    $$V = 2\pi \int_{a}^{b} R_g dA \,  = 2\pi \int_{0}^{1} (x + 1)(x^{1/2} - x^2) \, dx$$
1. **Multiplicación distributiva (Paso a paso):**
    
    $$(x + 1)(x^{1/2} - x^2) = x \cdot x^{1/2} - x \cdot x^2 + 1 \cdot x^{1/2} - 1 \cdot x^2$$$$= x^{1 + 1/2} - x^{1+2} + x^{1/2} - x^2 = x^{3/2} - x^3 + x^{1/2} - x^2$$
2. **Integración por regla de potencias:**
    
    $$\int x^{3/2} \, dx = \frac{x^{3/2 + 1}}{\frac{3}{2} + 1} = \frac{x^{5/2}}{\frac{5}{2}} = \frac{2}{5}x^{5/2}$$$$\int -x^3 \, dx = -\frac{x^4}{4}$$$$\int x^{1/2} \, dx = \frac{x^{1/2 + 1}}{\frac{1}{2} + 1} = \frac{x^{3/2}}{\frac{3}{2}} = \frac{2}{3}x^{3/2}$$$$\int -x^2 \, dx = -\frac{x^3}{3}$$$$V = 2\pi \left[ \frac{2}{5}x^{5/2} - \frac{x^4}{4} + \frac{2}{3}x^{3/2} - \frac{x^3}{3} \right]_{0}^{1}$$
3. **Evaluación de las fracciones:**
    
    - En $x = 1$:
        
        $$\frac{2}{5}(1) - \frac{1}{4}(1) + \frac{2}{3}(1) - \frac{1}{3}(1) = \frac{2}{5} - \frac{1}{4} + \left(\frac{2}{3} - \frac{1}{3}\right) = \frac{2}{5} - \frac{1}{4} + \frac{1}{3}$$
    - MCM de denominators $5, 4, 3$: $5 \times 4 \times 3 = 60$.
        
        - $\frac{2}{5} = \frac{2 \times 12}{60} = \frac{24}{60}$  
            
        - $\frac{1}{4} = \frac{1 \times 15}{60} = \frac{15}{60}$  
            
        - $\frac{1}{3} = \frac{1 \times 20}{60} = \frac{20}{60}$  
            
    - Suma:
        
        $$\frac{24 - 15 + 20}{60} = \frac{29}{60}$$
4. **Multiplicación por el factor** $2\pi$**:**
    
    $$V = 2\pi \left( \frac{29}{60} \right) = \frac{58\pi}{60} = \frac{29\pi}{30} \, \text{unidades}^3$$

## MÓDULO 5: Longitud de Arco

### **Ejercicio 8**

Halle la longitud exacta de la curva $y = \frac{1}{6}x^3 + \frac{1}{2x}$ en el intervalo $1 \le x \le 3$.

#### **Solución Paso a Paso:**

1. **Escribir la función con exponentes explícitos:**
    
    $$y = \frac{1}{6}x^3 + \frac{1}{2}x^{-1}$$
2. **Diferenciación:**
    
    $$y' = \frac{d}{dx}\left(\frac{1}{6}x^3\right) + \frac{d}{dx}\left(\frac{1}{2}x^{-1}\right)$$$$y' = \frac{3}{6}x^2 + \frac{1}{2}(-1)x^{-2} = \frac{1}{2}x^2 - \frac{1}{2x^2}$$
3. **Elevar al cuadrado la derivada:** Aplicando el binomio al cuadrado $(a - b)^2 = a^2 - 2ab + b^2$:
    
    - $a = \frac{1}{2}x^2 \implies a^2 = \frac{1}{4}x^4$  
        
    - $b = \frac{1}{2x^2} \implies b^2 = \frac{1}{4x^4}$  
        
    - Término medio: $2ab = 2 \left(\frac{1}{2}x^2\right)\left(\frac{1}{2x^2}\right) = 2 \cdot \frac{1}{4} = \frac{1}{2}$  
        $$(y')^2 = \frac{1}{4}x^4 - \frac{1}{2} + \frac{1}{4x^4}$$
4. **Construcción del término interno de la raíz** $1 + (y')^2$**:**
    
    $$1 + (y')^2 = 1 + \frac{1}{4}x^4 - \frac{1}{2} + \frac{1}{4x^4}$$
    
    Sumamos los términos independientes $1 - \frac{1}{2} = +\frac{1}{2}$:
    
    $$1 + (y')^2 = \frac{1}{4}x^4 + \frac{1}{2} + \frac{1}{4x^4}$$
5. **Re-factorización como Trinomio Cuadrado Perfecto:** Nótese que la expresión es exactamente igual a $(y')^2$ pero con signo positivo en el término del medio:
    
    $$1 + (y')^2 = \left( \frac{1}{2}x^2 + \frac{1}{2x^2} \right)^2$$
6. **Sustitución en la fórmula de longitud de arco:**
    
    $$L = \int_{1}^{3} \sqrt{1 + (y')^2} \, dx = \int_{1}^{3} \sqrt{\left( \frac{1}{2}x^2 + \frac{1}{2x^2} \right)^2} \, dx$$
    
    Como $\frac{1}{2}x^2 + \frac{1}{2x^2} > 0$ en $[1, 3]$, la raíz cancela perfectamente el cuadrado:
    
    $$L = \int_{1}^{3} \left( \frac{1}{2}x^2 + \frac{1}{2}x^{-2} \right) dx$$
7. **Integración paso a paso:**
    
    $$\int \frac{1}{2}x^2 \, dx = \frac{x^3}{6}$$$$\int \frac{1}{2}x^{-2} \, dx = \frac{1}{2} \left(\frac{x^{-1}}{-1}\right) = -\frac{1}{2x}$$$$L = \left[ \frac{x^3}{6} - \frac{1}{2x} \right]_{1}^{3}$$
8. **Evaluación de los límites:**
    
    - En $x = 3$:
        
        $$\frac{3^3}{6} - \frac{1}{2(3)} = \frac{27}{6} - \frac{1}{6} = \frac{26}{6}$$
    - En $x = 1$:
        
        $$\frac{1^3}{6} - \frac{1}{2(1)} = \frac{1}{6} - \frac{1}{2} = \frac{1}{6} - \frac{3}{6} = -\frac{2}{6}$$
    - Resta:
        
        $$L = \left( \frac{26}{6} \right) - \left( -\frac{2}{6} \right) = \frac{26}{6} + \frac{2}{6} = \frac{28}{6} = \frac{14}{3} \, \text{unidades}$$

## MÓDULO 6: Superficies de Revolución

### **Ejercicio 9**

Determine el área de la superficie generada al girar la curva $y = 2\sqrt{x}$ en el intervalo $1 \le x \le 2$ alrededor del eje $x$.

#### **Solución Paso a Paso:**

1. **Fórmula del área de la superficie de revolución (Eje** $x$**):**
    
    $$S = 2\pi \int_{a}^{b} y \cdot \sqrt{1 + (y')^2} \, dx$$
2. **Cálculo de la derivada:**
    
    $$y = 2x^{1/2} \implies y' = 2 \cdot \frac{1}{2}x^{-1/2} = x^{-1/2} = \frac{1}{\sqrt{x}}$$
3. **Cálculo del término dentro de la raíz:**
    
    $$(y')^2 = \left( \frac{1}{\sqrt{x}} \right)^2 = \frac{1}{x}$$$$1 + (y')^2 = 1 + \frac{1}{x} = \frac{x}{x} + \frac{1}{x} = \frac{x + 1}{x}$$
    
    Aplicando raíz cuadrada:
    
    $$\sqrt{1 + (y')^2} = \sqrt{\frac{x + 1}{x}} = \frac{\sqrt{x + 1}}{\sqrt{x}}$$
4. **Sustitución en el integrando:**
    
    $$S = 2\pi \int_{1}^{2} (2\sqrt{x}) \cdot \left( \frac{\sqrt{x + 1}}{\sqrt{x}} \right) dx$$
5. **Cancelación algebraica de términos:** Extraemos la constante 2 e identificamos que $\sqrt{x}$ en el numerador cancela a $\sqrt{x}$ en el denominador:
    
    $$S = 2\pi \cdot 2 \int_{1}^{2} \frac{\sqrt{x} \cdot \sqrt{x + 1}}{\sqrt{x}} \, dx = 4\pi \int_{1}^{2} \sqrt{x + 1} \, dx$$
6. **Integración mediante sustitución simple:**
    
    - Sea $u = x + 1 \implies du = dx$  
        
    - Cambio de límites de integración:
        
        - Si $x = 1 \implies u = 1 + 1 = 2$  
            
        - Si $x = 2 \implies u = 2 + 1 = 3$  
            
    
    Reescribiendo la integral:
    
    $$S = 4\pi \int_{2}^{3} u^{1/2} \, du$$$$\int u^{1/2} \, du = \frac{u^{3/2}}{\frac{3}{2}} = \frac{2}{3} u^{3/2}$$$$S = 4\pi \left[ \frac{2}{3} u^{3/2} \right]_{2}^{3} = 4\pi \cdot \frac{2}{3} \left( 3^{3/2} - 2^{3/2} \right)$$$$S = \frac{8\pi}{3} \left( 3^{3/2} - 2^{3/2} \right)$$
7. **Simplificación del resultado numérico:** Recordando que $a^{3/2} = a^{1 + 1/2} = a \sqrt{a}$:
    
    - $3^{3/2} = 3\sqrt{3}$  
        
    - $2^{3/2} = 2\sqrt{2}$  
        $$S = \frac{8\pi}{3} \left( 3\sqrt{3} - 2\sqrt{2} \right) \, \text{unidades}^2$$