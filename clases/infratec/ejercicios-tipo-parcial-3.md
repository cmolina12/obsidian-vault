
## Ejercicio 1

1. **¿Cuántas palabras de 10 letras se pueden formar con un alfabeto de 26 letras, sabiendo que solo se puede usar cada letra una única vez?**


#### **Paso 1: Identificar el problema**
Estamos formando palabras de 10 letras sin repetir letras, lo que corresponde a un problema de **permutaciones**. Cada letra seleccionada ya no puede volver a usarse.

---

#### **Paso 2: Fórmula de las permutaciones**

La fórmula para calcular el número de permutaciones de rr elementos seleccionados de un conjunto de nn elementos es:

$$P(n, r) = \frac{n!}{(n-r)!}$$

En este caso:

- n = 26 (el alfabeto completo),
- r = 10 (el número de letras en la palabra).

Sustituyendo los valores:

$$P(26, 10) = \frac{26!}{(26-10)!} = \frac{26!}{16!}$$

---

#### **Paso 3: Expandir los factoriales**

El factorial de un número n!n! se define como el producto de todos los números enteros positivos desde 1 hasta nn. Por lo tanto:

$$26! = 26 \cdot 25 \cdot 24 \cdot 23 \cdot 22 \cdot 21 \cdot 20 \cdot 19 \cdot 18 \cdot 17 \cdot 16!$$

Dividiendo entre 16!, los términos 16! se cancelan:

$$\frac{26!}{16!} = 26 \cdot 25 \cdot 24 \cdot 23 \cdot 22 \cdot 21 \cdot 20 \cdot 19 \cdot 18 \cdot 17$$

---

#### **Paso 4: Calcular el resultado**

Ahora multiplicamos estos valores:

$$P(26, 10) = 26 \cdot 25 \cdot 24 \cdot 23 \cdot 22 \cdot 21 \cdot 20 \cdot 19 \cdot 18 \cdot 17 = 19,275,223,968,000$$

---

### **Respuesta final**

El número total de palabras de 10 letras que se pueden formar sin repetir letras es:

$$\boxed{19,275,223,968,000}$$

---

2. **¿Cuántas palabras de 10 letras se pueden formar con un alfabeto de 26 letras, sabiendo que se pueden reutilizar las letras varias veces?**

#### **Paso 1: Identificar el problema**

Aquí estamos formando palabras de 10 letras, pero **las letras se pueden reutilizar**. Esto corresponde a un problema de **variaciones con repetición**, ya que cada posición puede ser ocupada por cualquiera de las 26 letras.

---

#### **Paso 2: Fórmula de las variaciones con repetición**

La fórmula para este caso es:

$$n^r$$

Donde:

- n = 26 (el total de letras del alfabeto),
- r = 10 (el número de letras en la palabra).

Entonces:

$$26^{10}$$

---

#### **Paso 3: Realizar el cálculo**

Elevamos 26 a la décima potencia:

$$26^{10} = 26 \cdot 26 \cdot 26 \cdot 26 \cdot 26 \cdot 26 \cdot 26 \cdot 26 \cdot 26 \cdot 26$$

Calculando:

$$26^{10} = 141,167,095,653,376$$

---

### **Respuesta final**

El número total de palabras de 10 letras que se pueden formar reutilizando letras es:

$$\boxed{141,167,095,653,376}$$

---

3. **Hay un grupo de 12 estudiantes. Queremos dividirlos en 2 grupos: 6 van a India y 6 a Australia. ¿Cuántos grupos distintos se pueden formar?**
#### **Paso 1: Identificar el problema**

Queremos dividir un grupo de 12 estudiantes en dos grupos de 6, y **no importa el orden** de los grupos (es decir, un grupo a India y otro a Australia es lo mismo si los estudiantes se intercambian entre los grupos).

---

#### **Paso 2: Fórmula para combinaciones**

Cuando el orden no importa, usamos la fórmula de **combinaciones**:

$$C(n, r) = \binom{n}{r} = \frac{n!}{r!(n-r)!}$$

Donde:

- n = 12 (el total de estudiantes),
- r = 6 (los estudiantes en uno de los grupos).

Sustituyendo:

$$C(12, 6) = \frac{12!}{6! \cdot (12 - 6)!} = \frac{12!}{6! \cdot 6!}$$

---

#### **Paso 3: Expandir y simplificar factoriales**

Expandiendo 12!, 6!, y simplificando:

$$12!=12⋅11⋅10⋅9⋅8⋅7⋅6!$$
$$C(12, 6) = \frac{12 \cdot 11 \cdot 10 \cdot 9 \cdot 8 \cdot 7 \cdot 6!}{6! \cdot 6!} = \frac{12 \cdot 11 \cdot 10 \cdot 9 \cdot 8 \cdot 7}{6 \cdot 5 \cdot 4 \cdot 3 \cdot 2 \cdot 1}$$

Dividimos:

$$C(12, 6) = \frac{665280}{720} = 924$$
Seleccionar **6 estudiantes de un grupo de 12** para enviar a India es equivalente a decir que los otros **6 van automáticamente a Australia**.

---

### **Respuesta final**

El número total de maneras de dividir a los 12 estudiantes en dos grupos de 6 es:

$$\boxed{924}$$
---
4. **Tenemos 12 bolas: 3 rojas, 4 azules, 5 amarillas. Asuma que se sacan 3 simultaneamente, cuantas combinaciones existen si queremos sacar una de cada color?**

#### **Paso 1: Entender el problema**

Queremos formar combinaciones específicas:

- Sacar **1 bola roja** de las 3 disponibles.
- Sacar **1 bola azul** de las 4 disponibles.
- Sacar **1 bola amarilla** de las 5 disponibles.

Como el orden de extracción no importa, usamos la fórmula de combinaciones para cada grupo.

---

#### **Paso 2: Fórmula de combinaciones**

La fórmula de combinaciones es:

$$C(n, r) = \binom{n}{r} = \frac{n!}{r!(n-r)!}$$

Donde:

- n es el total de elementos disponibles,
- r es el número de elementos que queremos seleccionar.

Aplicamos esto para cada color:

1. Para las bolas **rojas**: $$C(3, 1) = \frac{3!}{1!(3-1)!} = \frac{3}{1} = 3$$
2. Para las bolas **azules**: $$C(4, 1) = \frac{4!}{1!(4-1)!} = \frac{4}{1} = 4$$
3. Para las bolas **amarillas**: $$C(5, 1) = \frac{5!}{1!(5-1)!} = \frac{5}{1} = 5$$

---

#### **Paso 3: Multiplicar las combinaciones**

El número total de maneras de seleccionar una bola de cada color es el producto de las combinaciones calculadas:

$$C(3, 1) \cdot C(4, 1) \cdot C(5, 1) = 3 \cdot 4 \cdot 5 = 60$$

---

### **Respuesta final**

El número total de combinaciones para sacar una bola de cada color es:

$$\boxed{60}$$

---

## Ejercicio 2

Hay un juego de 8 cartas \{1, 2, 3, 4, 5, 6, 7, 8\}. Se gana si se tienen 2 cartas tal que la suma sea 9. ¿Con cuántas cartas se puede tener evidencia de que ya ganó?

Con 8 cartas y los pares posibles (1,8),(2,7),(3,6),(4,5), al seleccionar 4 cartas podemos evitar formar un par, eligiendo una carta de cada par (por ejemplo,1, 2, 3, 4). Sin embargo, al seleccionar una quinta carta, esta forzosamente completará uno de los pares restantes, ya que cada carta pertenece exclusivamente a un par. Por lo tanto, se necesitan **5 cartas** para garantizar que al menos un par cuya suma sea 9 siempre esté presente, sin importar cómo se seleccionen.

---

## Ejercicio 3

Al lanzar una moneda puede salir cara o sello. Asuma que se lanza una moneda 8 veces.

1. ¿Cuántas posibles combinaciones hay de resultados al lanzarla 8 veces?
2. ¿Cuántas de esas combinaciones tienen exactamente 3 caras?

#### **1. ¿Cuántas posibles combinaciones hay de resultados al lanzarla 8 veces?**

Cada lanzamiento tiene **2 posibles resultados**: cara (CC) o sello (SS). Por lo tanto, si lanzamos la moneda 8 veces, el total de combinaciones posibles es:

$$2^8$$

**Cálculo**:

$$2^8 = 256$$

---

### **Respuesta final para el punto 1**:

Hay un total de:

$$\boxed{256 \text{ combinaciones posibles.}}$$

---

#### **2. ¿Cuántas de esas combinaciones tienen exactamente 3 caras?**

Este problema corresponde a **combinaciones** donde el orden de las caras y sellos importa, pero se debe cumplir que haya exactamente 3 caras.

Usamos la fórmula de combinaciones:

$$C(n, r) = \binom{n}{r} = \frac{n!}{r!(n-r)!}$$

Donde:

- n = 8 (número total de lanzamientos),
- r = 3 (número de caras).

Sustituyendo:

$$C(8, 3) = \frac{8!}{3!(8-3)!} = \frac{8 \cdot 7 \cdot 6}{3 \cdot 2 \cdot 1}$$
 
**Cálculo**:

$$C(8, 3) = \frac{8 \cdot 7 \cdot 6}{6} = 56$$

---

### **Respuesta final para el punto 2**:

El número de combinaciones con exactamente 3 caras es:

$$\boxed{56 \text{ combinaciones.}}$$

---

## Ejercicio 4

1. ¿La relación de ortogonalidad entre dos rectas del plano es reflexiva, simétrica y transitiva?
2. La relación \(T\) definida por \(aTb\) si y solo si \(a - b\) es divisible por 2 o por 3, ¿es reflexiva, simétrica y transitiva?


### **Ejercicio 4.1: La relación de ortogonalidad entre dos rectas del plano es reflexiva, simétrica y transitiva**

#### **Reflexiva:**

- Una relación es reflexiva si, para toda recta r, se cumple r⊥r  (es decir, una recta es ortogonal consigo misma).
- Esto **no es cierto**, porque una recta no puede ser ortogonal a sí misma.

**Conclusión:** La relación de ortogonalidad **no es reflexiva**.

---

#### **Simétrica:**

- Una relación es simétrica si, para dos rectas r y s, r⊥*s*  ⟹  *s*⊥r
- Esto **es cierto** para la ortogonalidad, ya que si r es perpendicular a s, entonces s también es perpendicular a r.

**Conclusión:** La relación de ortogonalidad **es simétrica**.

---

#### **Transitiva:**

- Una relación es transitiva si, para tres rectas r,s,tr, s, t, r⊥s∧s⊥t  ⟹  r⊥t.
- Esto **no es cierto**, porque si r es perpendicular a s y s es perpendicular a t, entonces r y t serán paralelas (no perpendiculares).

**Conclusión:** La relación de ortogonalidad **no es transitiva**.

---

### **Respuesta final para 4.1:**

La relación de ortogonalidad:

- **No es reflexiva.**
- **Es simétrica.**
- **No es transitiva.**

---

### **Ejercicio 4.2: La relación T definida por aTb si y solo si a−b es divisible por 2 o por 3, es reflexiva, simétrica y transitiva**

#### **Reflexiva:**

- Una relación es reflexiva si, para todo a, se cumple aTa.
- En este caso, a−a=0, y 0 es divisible por 2 y por 3.
- Por lo tanto, T **es reflexiva**.

---

#### **Simétrica:**

- Una relación es simétrica si, para aTb, se cumple bTa.
- Aquí, si a−b es divisible por 2 o 3, entonces b−a=−(a−b) también es divisible por 2 o 3 (porque los números divisibles por 2 o 3 siguen siendo divisibles cuando cambian de signo).
- Por lo tanto, T **es simétrica**.

---

#### **Transitiva:**

- Una relación es transitiva si, para aTb y bTc, se cumple aTc.
- Si a−b es divisible por 2 o 3, y b−c divisible por 2 o 3, entonces: a−c=(a−b)+(b−c) La suma de dos números divisibles por 2 o 3 también será divisible por 2 o 3.
- Por lo tanto, T **es transitiva**.

---

### **Respuesta final para 4.2:**

La relación T:

- **Es reflexiva.**
- **Es simétrica.**
- **Es transitiva.**


---

## Ejercicio 5

Definimos la relación \(R\) en los reales de la siguiente manera: \(xRy\) es equivalente a \(x^2 - y^2 = x - y\).

1. Muestre que \(R\) es una relación de equivalencia.
2. Calcule las clases de equivalencia de un elemento \(x\) de \(\mathbb{R}\).

### **Ejercicio 5.1: Mostrar que R es una relación de equivalencia**

La relación RR está definida en los números reales como:

$$xRy \iff x^2 - y^2 = x - y$$

Para demostrar que RR es una relación de equivalencia, necesitamos probar que cumple con las tres propiedades: **reflexiva**, **simétrica** y **transitiva**.

#### **1. Reflexividad**

- Una relación es reflexiva si, para todo $$x \in \mathbb{R}, \text{se cumple xRx}.$$
- Sustituyendo x=y en la ecuación: $$x^2 - x^2 = x - x \implies 0 = 0$$ Esto es cierto para cualquier x, por lo que R es **reflexiva**.

---

#### **2. Simetría**

- Una relación es simétrica si, para xRy, también se cumple yRx.
- Si xRy, entonces: $$x^2 - y^2 = x - y$$ Al reordenar: $$y^2 - x^2 = y - x$$ Esto es equivalente a yRx, ya que simplemente cambiamos los roles de x y y.
- Por lo tanto, R es **simétrica**.

---

#### **3. Transitividad**

- Una relación es transitiva si, para xRy y yRz, se cumple xRz.
- Si xRy, entonces: $$x^2 - y^2 = x - y$$ Si yRz, entonces: $$y^2 - z^2 = y - z$$ Sumando estas dos ecuaciones: $$(x^2 - y^2) + (y^2 - z^2) = (x - y) + (y - z)$$ Simplificando: $$x^2 - z^2 = x - z$$ Esto demuestra que xRz.
- Por lo tanto, R es **transitiva**.

---

#### **Conclusión para 5.1:**

La relación R es:

- **Reflexiva**
- **Simétrica**
- **Transitiva**

Por lo tanto, R es una relación de equivalencia.

---

### **Ejercicio 5.2: Calcular las clases de equivalencia de un elemento x∈Rx \in \mathbb{R}**

Para determinar las clases de equivalencia, resolvemos la ecuación que define R:

$$x^2 - y^2 = x - y$$

#### **Paso 1: Factorizar la ecuación**

La ecuación se puede reescribir como:

$$(x - y)(x + y) = x - y$$

Si x−y≠0, podemos dividir ambos lados entre x - y:

x + y = 1

Si x - y = 0, esto implica que x = y (Por la reflexividad en si).

---

#### **Paso 2: Clases de equivalencia**

De la ecuación x + y = 1, podemos reescribir y como:

y = 1 - x

Por lo tanto, las clases de equivalencia están dadas por las rectas de la forma:

y=1−xy = 1 - x

Cada valor de xx define una clase de equivalencia, que incluye a todos los números yy tales que x+y=1x + y = 1.

---

### **Conclusión para 5.2:**

Las clases de equivalencia están formadas por pares (x,y)(x, y) tales que:

x + y = 1

Esto significa que cualquier elemento xx pertenece a la clase definida por la ecuación y = 1 - x.


---
