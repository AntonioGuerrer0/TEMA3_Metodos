# TEMA3_Metodos
<h1 align="center">Problemario de Métodos Numéricos</h1>

<h3>Realizado por:</h3>

<ul>
    <li>Jose Antonio Guerrero Lazcano</li>
</ul>

<hr>

<h1 id="indice" align="center">ÍNDICE</h1>

<ul>

<li><a href="#competencia-asignatura">Competencia de la Asignatura</a></li>

<li>
<a href="#metodos-integracion">TEMA 3: Métodos de Integración</a>

<ul>
<li><a href="#trapecio">Método del Trapecio</a></li>
<li><a href="#simpson13">Método de Simpson 1/3</a></li>
<li><a href="#simpson38">Método de Simpson 3/8</a></li>
<li><a href="#cuadratura-gaussiana">Método de la Cuadratura Gaussiana</a></li>
</ul>

</li>
<hr>

<h2 id="competencia-asignatura" align="center">
Competencia de la Asignatura
</h2>

<p>
Aplica los métodos numéricos para resolver problemas científicos y de ingeniería utilizando la computadora.
</p>


<hr>


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>

<hr>
<h2 id="trapecio" align="center">
1. Método del Trapecio
</h2>

<h3>¿Qué es?</h3>

<p>
El Método del Trapecio es un método numérico utilizado para aproximar el valor de una integral definida. Este método consiste en dividir el área bajo una curva en pequeños trapecios y calcular el área de cada uno para obtener una aproximación del área total.
</p>

<p>
A diferencia de otros métodos más simples, como la suma de rectángulos, el Método del Trapecio ofrece una mejor aproximación debido a que considera la inclinación de la función entre dos puntos consecutivos.
</p>

<p>
Es uno de los métodos más utilizados en integración numérica por su facilidad de implementación y buena precisión en funciones continuas.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Fórmula del Método del Trapecio Simple</h4>

<pre>
∫ f(x) dx ≈ (b - a) / 2 * [f(a) + f(b)]
</pre>

<h4>Fórmula del Método del Trapecio Compuesto</h4>

<pre>
∫ f(x) dx ≈ h/2 * [f(x0) + 2f(x1) + 2f(x2) + ... + 2f(xn-1) + f(xn)]
</pre>

<h4>Donde:</h4>

<ul>
<li><b>a:</b> límite inferior.</li>
<li><b>b:</b> límite superior.</li>
<li><b>h:</b> tamaño del subintervalo.</li>
<li><b>f(x):</b> función a integrar.</li>
<li><b>n:</b> número de segmentos.</li>
</ul>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Es fácil de entender e implementar.</li>
<li>Proporciona una mejor aproximación que el método rectangular.</li>
<li>Puede utilizarse en funciones continuas y suaves.</li>
<li>Reduce el error utilizando más subdivisiones.</li>
<li>Es útil para cálculos científicos y de ingeniería.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Puede generar errores en funciones muy curvas.</li>
<li>Es menos preciso que métodos como Simpson.</li>
<li>Requiere más subdivisiones para mejorar la precisión.</li>
<li>La aproximación depende del tamaño del intervalo.</li>
<li>Puede acumular errores numéricos.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li>
<b>Ingeniería en Sistemas Computacionales:</b>
Desarrollo de software científico y simulaciones numéricas.
</li>

<li>
<b>Ingeniería Civil:</b>
Cálculo de áreas, volúmenes y análisis estructural.
</li>

<li>
<b>Ingeniería Mecánica:</b>
Cálculo de trabajo, energía y transferencia de calor.
</li>

<li>
<b>Ingeniería Electrónica:</b>
Análisis de señales y procesamiento digital.
</li>

<li>
<b>Ingeniería Industrial:</b>
Modelado matemático y optimización de procesos.
</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir a = 0
    Definir b = 4
    Definir n = 4

    h = (b - a) / n

    suma = funcion(a) + funcion(b)

    Para i = 1 hasta n - 1

        x = a + i * h

        suma = suma + 2 * funcion(x)

    Fin Para

    resultado = (h / 2) * suma

    Mostrar "Resultado aproximado: "
    + resultado

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class MetodoTrapecio {

    public static double funcion(double x) {
        return Math.pow(x, 2);
    }

    public static void main(String[] args) {

        double a = 0;
        double b = 4;
        int n = 4;

        double h = (b - a) / n;

        double suma = funcion(a) + funcion(b);

        for(int i = 1; i < n; i++) {

            double x = a + i * h;

            suma += 2 * funcion(x);
        }

        double resultado = (h / 2) * suma;

        System.out.println("Resultado aproximado: " + resultado);
    }
}
```
<h3>Compilación de codigo</h3>
<img width="333" height="92" alt="Captura de pantalla 2026-05-27 193005" src="https://github.com/user-attachments/assets/4a4a1d32-4c5b-4902-ad5d-deb9c64265ec" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="simpson13" align="center">
2. Método de Simpson 1/3
</h2>

<h3>¿Qué es?</h3>

<p>
El Método de Simpson 1/3 es un método numérico utilizado para aproximar integrales definidas. Este método mejora la precisión del Método del Trapecio utilizando parábolas para aproximar la curva de la función en lugar de líneas rectas.
</p>

<p>
El método divide el intervalo en segmentos pares y utiliza polinomios de segundo grado para calcular una aproximación más precisa del área bajo la curva.
</p>

<p>
Es ampliamente utilizado en métodos numéricos debido a su buena precisión y facilidad de implementación.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Fórmula del Método de Simpson 1/3</h4>

<pre>
∫ f(x) dx ≈ h/3 * [f(x0) + 4f(x1) + 2f(x2) + 4f(x3) + ... + f(xn)]
</pre>

<h4>Donde:</h4>

<ul>
<li><b>h:</b> tamaño del intervalo.</li>
<li><b>a:</b> límite inferior.</li>
<li><b>b:</b> límite superior.</li>
<li><b>n:</b> número de segmentos (debe ser par).</li>
<li><b>f(x):</b> función a integrar.</li>
</ul>

<h4>Cálculo del tamaño de intervalo</h4>

<pre>
h = (b - a) / n
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Mayor precisión que el Método del Trapecio.</li>
<li>Reduce significativamente el error numérico.</li>
<li>Es eficiente para funciones suaves.</li>
<li>Fácil de implementar en programación.</li>
<li>Muy utilizado en cálculos científicos.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>El número de intervalos debe ser par.</li>
<li>Puede ser menos eficiente en funciones irregulares.</li>
<li>Requiere más operaciones matemáticas.</li>
<li>No es ideal para funciones discontinuas.</li>
<li>Puede acumular errores de redondeo.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li>
<b>Ingeniería en Sistemas Computacionales:</b>
Simulación matemática y software científico.
</li>

<li>
<b>Ingeniería Civil:</b>
Cálculo de áreas y análisis estructural.
</li>

<li>
<b>Ingeniería Mecánica:</b>
Análisis de energía y dinámica de sistemas.
</li>

<li>
<b>Ingeniería Electrónica:</b>
Procesamiento de señales y análisis numérico.
</li>

<li>
<b>Ingeniería Industrial:</b>
Optimización y modelado de procesos.
</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir a = 0
    Definir b = 4
    Definir n = 4

    h = (b - a) / n

    suma = funcion(a) + funcion(b)

    Para i = 1 hasta n - 1

        x = a + i * h

        Si i es par Entonces

            suma = suma + 2 * funcion(x)

        Si no

            suma = suma + 4 * funcion(x)

        Fin Si

    Fin Para

    resultado = (h / 3) * suma

    Mostrar "Resultado aproximado: "
    + resultado

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class SimpsonUnoTercio {

    public static double funcion(double x) {
        return Math.pow(x, 2);
    }

    public static void main(String[] args) {

        double a = 0;
        double b = 4;
        int n = 4;

        double h = (b - a) / n;

        double suma = funcion(a) + funcion(b);

        for(int i = 1; i < n; i++) {

            double x = a + i * h;

            if(i % 2 == 0) {
                suma += 2 * funcion(x);
            } else {
                suma += 4 * funcion(x);
            }
        }

        double resultado = (h / 3) * suma;

        System.out.println("Resultado aproximado: " + resultado);
    }
}
```
<h3>Compilación del codigo</h3>

<img width="388" height="87" alt="Captura de pantalla 2026-05-27 193620" src="https://github.com/user-attachments/assets/ca436940-e4eb-4eeb-916a-481870d3e15b" />

<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="simpson38" align="center">
3. Método de Simpson 3/8
</h2>

<h3>¿Qué es?</h3>

<p>
El Método de Simpson 3/8 es un método numérico utilizado para aproximar integrales definidas. Este método es una extensión del Método de Simpson 1/3 y utiliza polinomios cúbicos para aproximar el comportamiento de una función.
</p>

<p>
El método divide el intervalo en múltiples segmentos y utiliza grupos de tres subintervalos para calcular una aproximación más precisa del área bajo la curva.
</p>

<p>
Es especialmente útil cuando el número de intervalos es múltiplo de tres y se requiere una mayor precisión en los cálculos numéricos.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Fórmula del Método de Simpson 3/8</h4>

<pre>
∫ f(x) dx ≈ 3h/8 * [f(x0) + 3f(x1) + 3f(x2) + 2f(x3)
+ 3f(x4) + 3f(x5) + 2f(x6) + ... + f(xn)]
</pre>

<h4>Donde:</h4>

<ul>
<li><b>h:</b> tamaño del intervalo.</li>
<li><b>a:</b> límite inferior.</li>
<li><b>b:</b> límite superior.</li>
<li><b>n:</b> número de intervalos (debe ser múltiplo de 3).</li>
<li><b>f(x):</b> función a integrar.</li>
</ul>

<h4>Cálculo del tamaño de intervalo</h4>

<pre>
h = (b - a) / n
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Ofrece una mayor precisión que el Método del Trapecio.</li>
<li>Permite aproximaciones eficientes en funciones suaves.</li>
<li>Utiliza polinomios cúbicos para mejorar resultados.</li>
<li>Reduce el error numérico.</li>
<li>Es útil en cálculos científicos y de ingeniería.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>El número de intervalos debe ser múltiplo de 3.</li>
<li>Requiere más operaciones matemáticas.</li>
<li>Puede ser complejo para funciones discontinuas.</li>
<li>Consume más tiempo de cálculo que métodos simples.</li>
<li>Puede acumular errores de redondeo.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li>
<b>Ingeniería en Sistemas Computacionales:</b>
Simulación matemática y desarrollo de software científico.
</li>

<li>
<b>Ingeniería Civil:</b>
Cálculo de áreas, volúmenes y análisis estructural.
</li>

<li>
<b>Ingeniería Mecánica:</b>
Análisis de energía y transferencia de calor.
</li>

<li>
<b>Ingeniería Electrónica:</b>
Procesamiento digital de señales y análisis numérico.
</li>

<li>
<b>Ingeniería Industrial:</b>
Optimización y modelado de procesos industriales.
</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir a = 0
    Definir b = 3
    Definir n = 3

    h = (b - a) / n

    suma = funcion(a) + funcion(b)

    Para i = 1 hasta n - 1

        x = a + i * h

        Si i es múltiplo de 3 Entonces

            suma = suma + 2 * funcion(x)

        Si no

            suma = suma + 3 * funcion(x)

        Fin Si

    Fin Para

    resultado = (3 * h / 8) * suma

    Mostrar "Resultado aproximado: "
    + resultado

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class SimpsonTresOctavos {

    public static double funcion(double x) {
        return Math.pow(x, 2);
    }

    public static void main(String[] args) {

        double a = 0;
        double b = 3;
        int n = 3;

        double h = (b - a) / n;

        double suma = funcion(a) + funcion(b);

        for(int i = 1; i < n; i++) {

            double x = a + i * h;

            if(i % 3 == 0) {
                suma += 2 * funcion(x);
            } else {
                suma += 3 * funcion(x);
            }
        }

        double resultado = (3 * h / 8) * suma;

        System.out.println("Resultado aproximado: " + resultado);
    }
}
```
<h3>Compilacón de codigo</h3>

<img width="335" height="106" alt="Captura de pantalla 2026-05-27 194030" src="https://github.com/user-attachments/assets/f46b2468-3153-4503-8df9-5a79f81d9cd1" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="cuadratura-gaussiana" align="center">
4. Método de la Cuadratura Gaussiana
</h2>

<h3>¿Qué es?</h3>

<p>
El Método de la Cuadratura Gaussiana es un método numérico utilizado para aproximar integrales definidas con una alta precisión. A diferencia de otros métodos de integración, este utiliza puntos específicos llamados nodos y valores llamados pesos para obtener resultados más exactos utilizando menos evaluaciones de la función.
</p>

<p>
La Cuadratura Gaussiana se basa en polinomios ortogonales y permite integrar exactamente ciertos polinomios de grado elevado.
</p>

<p>
Es uno de los métodos más precisos y eficientes en integración numérica y es ampliamente utilizado en aplicaciones científicas e ingenieriles.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Fórmula general de Cuadratura Gaussiana</h4>

<pre>
∫ f(x) dx ≈ Σ [wi * f(xi)]
</pre>

<h4>Donde:</h4>

<ul>
<li><b>wi:</b> pesos de integración.</li>
<li><b>xi:</b> nodos o puntos de evaluación.</li>
<li><b>f(x):</b> función a integrar.</li>
</ul>

<h4>Transformación de intervalo</h4>

<pre>
x = ((b - a) / 2) * t + ((b + a) / 2)
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Ofrece una gran precisión con pocos puntos.</li>
<li>Reduce el error numérico.</li>
<li>Es más eficiente que otros métodos de integración.</li>
<li>Funciona muy bien en funciones suaves.</li>
<li>Muy utilizada en cálculos científicos avanzados.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Es más compleja de implementar.</li>
<li>Requiere el uso de nodos y pesos especiales.</li>
<li>Puede ser difícil de entender para principiantes.</li>
<li>No siempre es adecuada para funciones discontinuas.</li>
<li>Consume más procesamiento en ciertos casos.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li>
<b>Ingeniería en Sistemas Computacionales:</b>
Desarrollo de simulaciones científicas y análisis numérico.
</li>

<li>
<b>Ingeniería Civil:</b>
Análisis estructural y cálculo de áreas complejas.
</li>

<li>
<b>Ingeniería Mecánica:</b>
Transferencia de calor y análisis dinámico.
</li>

<li>
<b>Ingeniería Electrónica:</b>
Procesamiento de señales y sistemas digitales.
</li>

<li>
<b>Ingeniería Industrial:</b>
Optimización matemática y modelado de sistemas.
</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir nodos =
    {-0.5773502692, 0.5773502692}

    Definir pesos =
    {1.0, 1.0}

    Definir a = 0
    Definir b = 3

    suma = 0

    Para i = 0 hasta longitud de nodos - 1

        x = ((b - a) / 2) * nodos[i]
            + ((b + a) / 2)

        suma =
        suma + pesos[i] * funcion(x)

    Fin Para

    resultado = ((b - a) / 2) * suma

    Mostrar "Resultado aproximado: "
    + resultado

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class CuadraturaGaussiana {

    public static double funcion(double x) {
        return Math.pow(x, 2);
    }

    public static void main(String[] args) {

        double[] nodos = {-0.5773502692, 0.5773502692};
        double[] pesos = {1.0, 1.0};

        double a = 0;
        double b = 3;

        double suma = 0;

        for(int i = 0; i < nodos.length; i++) {

            double x = ((b - a) / 2) * nodos[i] + ((b + a) / 2);

            suma += pesos[i] * funcion(x);
        }

        double resultado = ((b - a) / 2) * suma;

        System.out.println("Resultado aproximado: " + resultado);
    }
}
```
<h3>Compilación del codigo</h3>
<img width="348" height="98" alt="Captura de pantalla 2026-05-27 194707" src="https://github.com/user-attachments/assets/57cddb1f-ea82-439f-9f9a-3383599f38b3" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>
