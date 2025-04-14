# Ejercicio 1

$$ \text{Utilice el Teorema del Residuo Chino para encontrar la solucion en } ℤ_{1001}a$$
$$
\begin{cases} x\equiv_{} 5 \text{ mod }7 \\ x\equiv{}8\text{ mod }11 \\x\equiv{}12\text{ mod }13 \end{cases}
$$

### Calculamos N (Producto de los modulos)

$$N=7\times 11\times_{}3=1001$$

### Dividimos N por cada modulo

$$N_{i}$$

$$N_{1}=\frac{N}{7}=\frac{1001}{7}=143$$
$$N_{2}=\frac{N}{11}=\frac{1001}{11}=91$$
$$N_{3}=\frac{N}{13}=\frac{1001}{13}=77$$

### Calculamos los inversos modulares para cada N_i

Necesitamos encontrar el inverso modular y_i tal que

$$N_{i}\text{ }\times\text{ }y_{i}\equiv{}1\text{ (mod }m_{i}\text{)}$$
### **Inverso modular de N_1 = 143 (mod 7)**
__________________

$$143*y_{1}\equiv{}1\text{ (mod 7)}$$

**Dividimos 143 por 7**

$$\frac{143}{7}=20\text{ y el residuo es 3, entonces:}$$
$$143 \equiv{}3\text{ (mod 7), y ahora buscamos }y_{1}\text{ tal que:}$$
$$3\times{}y_{1}\equiv{}1\text{ (mod 7)}$$
**Probamos valores**
$$3\times_{}1=3$$
$$3\times_{}2=6$$
$$3\times_{}3=9\text{ (mod 7)}\equiv_{}2 \text{ (mod 7)}$$
$$3\times_{}4=12\text{ (mod 7)}\equiv_{}5 \text{ (mod 7)}$$
$$3\times_{}5=15\text{ (mod 7)}\equiv_{}1 \text{ (mod 7)}$$

Por lo tanto, el inverso de **3** (y por tanto de **143**) módulo 7 es:
$$y_{1}=5$$
### **Inverso modular de N_2 = 91 (mod 11)**
____________

$$91 \times{}y_{2}\equiv{}1\text{ (mod 11)}$$
**Dividimos 91 por 11**
$$\frac{91}{11}=8\text{ y el residuo es 3}$$
$$91\equiv{}3\text{ (mod 11), y ahora buscamos }y_{1}\text{ tal que:}$$
$$3\times y_{2}\equiv{}1\text{ (mod 11)}$$
**Probamos valores**

$$3\times_{}1=3$$
$$3\times{}2=6$$
$$3\times{}3=9$$
$$3\times{}4=12\equiv1\text{ (mod 11)}$$
Por lo tanto, el inverso de **3** (y por lo tanto **91**) módulo 11 es:
$$y_{2}=4$$
### **Inverso modular de N_3 = 77 (mod 13)**
____________
$$77*y_{3}\equiv_{}1\text{ (mod 13)}$$

**Dividimos 77 por 13**

$$\frac{77}{13}=5\text{ y el residuo es 12}$$
$$77\equiv{}12\text{ (mod 13), y ahora buscamos }y_{1}\text{ tal que:}$$
$$12\times y_{3}\equiv_{}1\text{ (mod 13)}$$
**Probamos valores**
$$12×1=12$$
$$12×2=24≡11\text{ (mod 13)}$$
*...etc
$$12×12=144≡1\text{ (mod 13)}$$
Por lo tanto, el inverso de **12** (y por lo tanto **77**) módulo 13 es:
$$y_{3}=12$$

## Resumen de los inversos

$$y_{1}=5\text{ es el inverso de 143 (mod 7)}$$
$$y_{2}=4\text{ es el inverso de 91 (mod 11)}$$
$$y_{3}=12\text{ es el inverso de 77 (mod 13)}$$

### Calcular la solución con la formula general

**Formula general**:

$$x=(a_{1}\times N_{1}\times y_{1})+(a_{2}\times N_{2}\times y_{2})+(a_{3}*N_{3}*y_{3})\text{ (mod N)}$$

**Sustituyendo valores y resolviendo:**
$$x=(5\times 143\times 5)+(8\times 91\times 4)+(12\times77\times 12)\text{ (mod 1001)}$$
$$x=(3575+2912+11088) \text{ (mod 1001)}$$
$$x=17575 \text{ mod 1001}$$
$$x = 558$$

# Ejercicio 2

1. **Utilice Square & Multiply (S&M) para encontrar**
$$19^{210}\text{ mod 35}$$
**Primero expresamos el exponente 210 en binario con divisiones sucesivas**

$$\frac{210}{2}=105\text{, residuo 0}$$
$$\frac{105}{2}=52\text{, residuo 1}$$
$$\frac{52}{2}=26\text{, residuo 0}$$
$$\frac{26}{2}=13\text{, residuo 0}$$
$$\frac{13}{2}=6\text{, residuo 1}$$
$$\frac{6}{2}=3\text{, residuo 0}$$
$$\frac{3}{2}=1\text{, residuo 1}$$
El cociente se ha vuelto menor que la base, por lo tanto paramos aqui. El numero binario es:
$$11010010_{2}$$
Esto significa que:
$$210=2^{7}+2^{6}+2^{4}+2^{1}$$

**Aplicamos el algoritmo Square and Multiply**

1. *Inicializar*$$x=19\text{ mod 35}$$
2. *Iterar según los bits binarios de 210*
Trabajamos de derecha a izquierda el binario 11010010.
   - Si el bit es 0, hacemos **square** (cuadrado).
   - Si el bit es 1, hacemos **square y multiply**.
3. *Square and Multiply*

$$x_{0}=19$$
$$0=19^{2}=361 ={}361\text{ mod 35}\equiv_{}11$$
$$1=((11^{2}\text{ mod 35})\times_{}11)\text{ mod 35}\equiv19$$
$$0=19^{2}=361 ={}361\text{ mod 35}\equiv_{}11$$
$$0=11^{2}=121 ={}121\text{ mod 35}\equiv_{}16$$
$$1=((16^{2}\text{ mod 35})\times_{}16)\text{ mod 35}\equiv1$$
$$0=1^{2}=1 ={}1\text{ mod 35}\equiv_{}1$$
$$1=((1^{2}\text{ mod 35})\times_{}1)\text{ mod 35}\equiv1$$
$$1=((1^{2}\text{ mod 35})\times_{}1)\text{ mod 35}\equiv1$$

**Por lo tanto**:
$$19^{210}\text{ mod 35}=1$$
2.**Encontrar ϕ(16873)**

**Buscamos los factores primos de 16873**

Probamos dividiendo:
$$\frac{16873}{n},\text{ donde n son los numeros primos más pequeños que podamos usar}$$
Hasta que obtengamos un entero, en este caso el primer entero m fue **47** y el resultado de esta división fue **359**, así que estos dos son factores primos. Si hacemos raíz de 359 nos da 18, entonces probamos con los números primos menores que 18 y ninguno nos daría un entero. Por lo tanto, 359 es primo y ahí acaba.

Los factores primos de 16873 son 47 y 359. 

Ya que tenemos dos factores primos, eso significa que 16873 se puede expresar como el producto de estos dos números primos.

$$16873=47\times{}47$$
La funcion ϕ(n) para un numero *n* que es el producto de dos primos *p* y *q* se calcula con la formula:

$$ϕ(n)=(p-1)\times{}(q-1)$$

En este caso, p = 47 y q = 359.

$$ϕ(16873)=(47-1)\times{}(359-1)$$
$$ϕ(16873)=46*358$$
$$ϕ(16873)=16448$$

Por lo tanto, el resultado es **16448**.

3. **Encontrar ϕ(111475)**

**Buscamos los factores primos de 111475**

Probamos buscando los factores primos y vemos que:
$$\frac{111475}{5}=22295$$
$$\frac{22295}{5}=4459$$
Entonces por ahora, tenemos 5 x 5 x 4459 y seguimos

$$\frac{4459}{13}=343$$
343 es lo mismo que 7 a la 3, entonces encontramos los factores primos finales.

Los factores primos de 111475 son:
$$5^{2}\times7^{3}\times_{}13^{1}$$
**Calculamos ϕ(111475)**

La funcion totiente de Euler se calcula con la formula:

$$ϕ(n)=n\left( 1-\frac{1}{p_{1}} \right)\left( 1-\frac{1}{p_{2}} \right)\left( 1-\frac{1}{p_{3}} \right)$$

Aplicando los factores primos:
$$p_{1}=5,p_{2}=7,p_{3}=17$$
Sustituimos:
$$ϕ(111475)=111475\left( 1-\frac{1}{5} \right)\left( 1-\frac{1}{{7}} \right)\left( 1-\frac{1}{{13}} \right)$$
$$ϕ(111475)=11475\times \frac{4}{5}\times \frac{6}{7}\times \frac{12}{13}$$
$$ϕ(111475)=70320$$

Por lo tanto, el resultado es **70320**.

**4. Usa el Teorema de Euler para calcular:**
$$539^{658}\text{ mod 24}$$
1. **Primero, verificamos que el numero y el modulo son coprimos**

Es decir, si gcd(539,24) = 1. Rapidamente aplicamos algoritmo extendido de Euclides.

$$539=1*24+11$$
$$24=2*11+2$$
$$11=5*2+1$$
$$2=2*1+0$$

Ya que el ultimo residuo cociente no es 0, el gcd(539,24) = 1, lo que significa que 539 y 24 son coprimos y si podemos aplicar el teorema de Euler.

2. **Calcular ϕ(24)**

Calculamos la funcion totiente de Euler:

- 24 se puede factorizar como:
$$24=2^{3}\times 3^{1}$$
- Aplicamos la formula:
$$ϕ(n)=n\left( 1-\frac{1}{p_{1}} \right)\left( 1-\frac{1}{p_{2}} \right)$$
Donde p1 y p2 son 2 y 3 respectivamente.

$$ϕ(24)=24\left( 1-\frac{1}{{2}} \right)\left( 1-\frac{1}{{3}} \right)$$
$$ϕ(24)=8$$

3. **Calcular 658 modϕ(24) para reducir la potencia**

*Ahora calculamos:*
$$658\text{ mod ϕ(24)}$$
*Que en este caso es:*
$$658\text{ mod 8}$$
*Y nos da como resultado:*
$$2 \text{ mod 8}$$

4. **Calcular la ecuación original**

$$539^{658}\text{ mod 24}$$ 
*Se reduce a:*
$$539^{2}\text{ mod 24}$$

*Primero podemos ignorar la potencia y hacer el modulo:*
$$539 \text{ mod 24}=11$$
*Entonces:*
$$11^{2}=121,\text{ 121 mod 24}=1$$
*Por lo tanto:*
$$539^{658}\text{ mod 24}=1$$
**El resultado final es que:**
$$539^{658}\equiv 1 \text{ mod 24}$$

# Ejercicio 3

**Encontrar los inversos usando el Algoritmo Extendido de Euclides y escribir la justificación**

**1.**$$149^{-1}\text{ mod }135$$
_____
**Definición inverso multiplicativo de en el modulo n:

$$a*x\equiv 1\text{ mod n}$$

*Entonces:*

$$149*x\equiv 1\text{ mod 135}$$
Esto es equivalente a encontrar *x* tal que:
$$149x-135k=1$$
- **Aplicamos el Algoritmo Extendido de Euclides. Primero sacamos las ecuaciones del Algoritmo de Euclides:**

$$149=1*135+14$$
$$135=9*14+9$$
$$14=1*9+5$$
$$9=1*5+4$$
$$5=1*4+1$$
$$4=4*1+0$$
gcd(149,135) =  4

**Ahora el Extendido y empezamos con la penúltima ecuación:**

$$5=1*4+1$$
**Dejamos el 1 solo**
$$1=5-1*4$$
**Aplicamos el algoritmo**
$$1=5-1*(9-1*5)$$
$$1=1*5-1*9+1*5$$
$$1=5(1+1)-1*9$$
$$1=5*2-1*9$$
$$1=(14-1*9)*2-1*9$$
$$1=2*14-2*9-1*9$$
$$1=2*14+(-2-1)*9$$
$$1=2*14-3*9$$
$$1=2*14-3*(135-9*14)$$
$$1=2*14-3*135+9*3*14$$
$$1=14(2+9*3)-3*135$$
$$1=14*29-3*135$$
$$1=(149-1*135)*29-3*135$$
$$1=29*149-29*1*135-3*135$$
$$1=29*149+(-3-29*1)135$$
$$1=29*149+135*-32$$
$$1=29*149-32*135$$

**Este resultado implica que:**
$$29*149\equiv 1\text{ mod }135$$
Ya que el x que acompaña a 149 es 29 precisamente.

**Entonces el inverso de 149 modulo 135 es:**
$$x \equiv 29\text{ mod }135$$

**2.**$$123^{-1}\text{ mod 43}$$
_________________________________

Esto es equivalente a encontrar *x* tal que:
$$123x \equiv 1 \text{ mod }43$$
**O resolver la ecuacion:**
$$123x-43k=1$$
**Aplicamos el Algoritmo Extendido de Euclides. Primero sacamos las ecuaciones del Algoritmo de Euclides:**

$$123 = 2 * 43 +37$$
$$43 = 1 * 37 +6$$
$$37 = 6 * 6 +1$$
$$6 = 6 * 1 +0$$

gcd(123,43) = 1

**Algoritmo Extendido**

$$1=37-6*6$$
$$1=37-6*(43-1*37)$$
$$1=1*37-6*43+6*1*37$$
$$1=(1+6)37-6*43$$
$$1=7*37-6*43$$
$$1=7*(123-2*43)-6*43$$
$$1=7*123-7*2*43-6*43$$
$$1=7*123+(-7*2-6)43$$
$$1=7*123-20*43$$

**Entonces x es 123 e implica que:**
$$7*123\equiv 1 \text{ mod 43}$$


**Entonces el inverso de 123 modulo 43 es:
$$x\equiv 7 \text{ mod }43$$

**3.**$$101^{-1}\text{ mod }149$$
______________

Esto es equivalente a encontrar *x* tal que:
$$101x \equiv 1 \text{ mod }149$$
*O resolver la ecuación:*
$$101x-149k=1$$
**Aplicamos el Algoritmo Extendido de Euclides. Primero sacamos las ecuaciones del Algoritmo de Euclides:**

$$149=1*101+48$$
$$101=2*48+5$$
$$48=9*5+3$$
$$5=1*3+2$$
$$3=1*2+1$$
$$2=2*1+0$$

gcd(101,149) = 1

**Algoritmo Extendido**
$$1=3-1*2$$
$$1=3-1*(5-1*3)$$
$$1=1*3-1*5+1*3$$
$$1=(1+1)3-1*5$$
$$1=2*3-1*5$$
$$1=2*(48-9*5)-1*5$$
$$1=2*48-2*9*5-1*5$$
$$1=2*48+(-2*9-1)5$$
$$1=2*48-19*5$$
$$1=2*48-19*(101-2*48)$$
$$1=2*48-19*101+19*2*48$$
$$1=(2+19*2)48-19*101$$
$$1=40*48-19*101$$
$$1=40*(149-1*101)-19*101$$
$$1=40*149-40*101-19*101$$
$$1=40*149+(-40-19)101$$
$$1=40*149+-59*101$$
**Entonces x es 101 e implica que:**

$$-59*101\equiv 1 \text{ mod 149}$$
**Entonces el inverso de 123 modulo 43 es:**

$$-59*101\equiv 1 \text{ mod 149}$$

*Sin embargo, como -59 es un numero negativo, podemos expresarlo como un numero positivo sumando 149. Entonces, el inverso seria:*

$$x\equiv 90 \text{ mod 149}$$

# Ejercicio 4

**Sea p = 83, q = 97 y e = 5**

**4.1.** Encuentre *c* el cifrado de *m* = 100 usando el RSA (usando S&M)

### Paso 1: Calcular n

*n* es el producto de los dos primos *p* y *q*:
$$n = p*q=83*97=8051$$

### Paso 2: Calcular ϕ(n)

$$ϕ(n)=(p-1)(q-1)=(83-1)(97-1)=82*96=7872$$

### Paso 3: Cifrado del mensaje

El cifrado *c* se calcula con la formula:
$$c\equiv m^{e}\text{ mod }n$$
Sustituyendo valores:
$$c\equiv 100^{5}\text{ mod }8051$$

### Paso 4: Calculamos el cifrado con Square & Multiply

1. **Pasamos a binario el exponente**

$$\frac{5}{2}=2\text{, residuo }1$$
$$\frac{2}{2}=1\text{, residuo }0$$

**Valor en binario:**
$$101_{2}$$
*Significa que:*
$$5=2^{2}+2^{0}$$
2. **Aplicamos S&M**
Iniciamos con *x = 100*

$$1=1^{2}*100 \text{ mod 8051}=100$$
$$0=100^{2}\text{ mod 8051}=1949$$
$$1=(1949^{2}\text{ mod 8051})*100\text{ mod 8051}=5869$$

El cifrado *c* del mensaje *m* = 100 es:
$$c = 5869$$

**4.2. Decifre el c obtenido. Utilizar el algoritmo extendido de Euclides para calcular**
$$d=e^{-1}\text{modϕ}(n)$$
**Aviso**: Este punto se realizo en Python y se encuentra completo en el repositorio. A continuación se muestra el código y sus respectivos resultados.

```python
def algoritmo_extendido_euclides(a, b): # Algoritmo extendido de Euclides
    if a == 0: # Caso base
        return b, 0, 1 # Devolver mcd(b, 0) = b y los coeficientes de Bezout s = 0, t = 1
    mcd, s1, t1 = algoritmo_extendido_euclides(b % a, a) # Llamada recursiva
    s = t1 - (b // a) * s1 # Calcular los coeficientes de Bezout s y t
    t = s1 
    return mcd, s, t # Devolver mcd(a, b) = mcd(b % a, a) y los coeficientes de Bezout s y t

def mod_multiplicativo_inverso(e, phi): # Calcular el inverso multiplicativo de e módulo phi
    _, s, _ = algoritmo_extendido_euclides(e, phi) # Calcular el inverso multiplicativo de e módulo phi 
    return s % phi # Devolver el inverso multiplicativo de e módulo phi

def descifrar_rsa_sm(c, d, n): # Descifrar un mensaje cifrado c usando la clave privada d y el módulo n
    return pow(c, d, n) # Devolver el mensaje descifrado

# Parámetros dados
p = 83
q = 97
e = 5
c = 5869  # Valor cifrado obtenido previamente en 4.1

# Calcular n y φ(n)
n = p * q 
phi = (p - 1) * (q - 1)

# Calcular d usando el algoritmo extendido de Euclides
d = mod_multiplicativo_inverso(e, phi) 
print(f"d = {d}") # Imprimir el valor de d

# Descifrar el mensaje cifrado c
m_descifrado = descifrar_rsa_sm(c, d, n) 
print(f"Mensaje descifrado = {m_descifrado}") # Imprimir el mensaje descifrado
```

### Resultados de la consola

**d** = 3149
**Mensaje descifrado** = 100 (*Esto confirma que esta correcto*)

# Ejercicio 5

**Cifre la frase “Si la gente no cree que las matemáticas son simples, es solo porque no se dan cuenta de lo complicado que es la vida” de John Louis von Neumann utilizando el cifrado afín con la clave (a=11, b=15).**

**Aviso:** Este punto se realizo en Python y se encuentra completo en el repositorio. A continuación se muestra el código y sus respectivos resultados.

~~~python
# Cifrado afín que preserva espacios y caracteres especiales
alfabeto_ingles = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

def texto_a_numeros(texto):
    texto = texto.upper()
    numeros = []
    estructura = []  # Lista de tuplas (es_letra, caracter)
    
    for letra in texto:
        if letra in alfabeto_ingles:
            numeros.append(alfabeto_ingles.index(letra))
            estructura.append(('letra', None))
        else:
            estructura.append(('especial', letra))
    
    return numeros, estructura

def numeros_a_texto(numeros, estructura):
    texto = ""
    texto_sin_espacios = ""
    i = 0  # índice para los números
    
    for tipo, caracter in estructura:
        if tipo == 'letra':  # Si es una letra
            letra_cifrada = alfabeto_ingles[numeros[i]]
            texto += letra_cifrada
            texto_sin_espacios += letra_cifrada
            i += 1
        else:  # Si es un carácter especial
            texto += caracter
    
    return texto, texto_sin_espacios

def cifrado_afin(texto, a, b):
    numeros, estructura = texto_a_numeros(texto)
    numeros_cifrados = []
    
    for numero in numeros:
        numeros_cifrados.append((a * numero + b) % 26)
    
    return numeros_a_texto(numeros_cifrados, estructura)

def descifrado_afin(texto_cifrado, a, b):
    # Primero obtenemos los números y estructura del texto cifrado
    numeros, estructura = texto_a_numeros(texto_cifrado)
    numeros_descifrados = []
    
    for numero in numeros:
        numeros_descifrados.append((numero - b) * pow(a, -1, 26) % 26)
    
    return numeros_a_texto(numeros_descifrados, estructura)[0]

# Probamos el código con la frase
frase = "Si la gente no cree que las matemáticas son simples, es solo porque no se dan cuenta de lo complicado que es la vida"
a = 11
b = 15

# Obtenemos las dos versiones del cifrado
frase_cifrada, frase_cifrada_sin_espacios = cifrado_afin(frase, a, b)

print("\nFrase original:", frase)
print("\nFrase cifrada (sin espacios):", frase_cifrada_sin_espacios)
print("\nFrase cifrada (con espacios):", frase_cifrada)
print("\nFrase descifrada:", descifrado_afin(frase_cifrada, a, b))
~~~

### Resultados de la consola

**Frase original:** Si la gente no cree que las matemáticas son simples, es solo porque no se dan cuenta de lo complicado que es la vida

**Frase cifrada (sin espacios):** FZGPDHCQHCNLUHHJBHGPFRPQHRQZLPFFNCFZRYGHFHFFNGNYNUJBHCNFHWPCLBHCQPWHGNLNRYGZLPWNJBHHFGPMZWP

**Frase cifrada (con espacios):** FZ GP DHCQH CN LUHH JBH GPF RPQHRÁQZLPF FNC FZRYGHF, HF FNGN YNUJBH CN FH WPC LBHCQP WH GN LNRYGZLPWN JBH HF GP MZWP

**Frase descifrada:** SI LA GENTE NO CREE QUE LAS MATEMÁTICAS SON SIMPLES, ES SOLO PORQUE NO SE DAN CUENTA DE LO COMPLICADO QUE ES LA VIDA

*Se decidió imprimir varias versiones del cifrado y su respectivo descifrado para confirmar la respuesta*

# Ejercicio 6

**1. Muestre usando inducción que**$$3^{n}<n!\text{ para todo }n\geq_{}7$$
### Paso 1: Base

Para n = 7, tenemos que verificar si la desigualdad es cierta:
$$3^{7}=2187\text{ y }7! = 5040$$
Claramente:$$3^{7}=2187<7! = 5040$$, por lo tanto, la base de inducción es correcta.

### Paso 2: Hipótesis

Supongamos que la desigualdad es verdadera para un valor n = k, es decir:
$$3^{k}<k!$$
Queremos demostrar que la desigualdad tambien es verdadera para n = k + 1, es decir, demostrar que:
$$3^{k+1}<(k+1)!$$
### Paso 3: Paso inductivo

Sabemos que
$$3^{k+1}=3^{k}*3

$$
y queremos probar que:
$$3^{k+1}=3^{k}*3<(k+1)!$$
Dividimos ambos lados por k! (que es positivo para k >=7):
$$3<k+1$$
Este paso es ierto siempre que k + 1 >= 4, lo cual es verdadero para k >= 3. Pero hay que recordar que estamos trabajando con k >= 7, por lo que la desigualdad 3 < k + 1 **se cumple**.

**Conclusion:**
Hemos demostrado que si la desigualdad 3^k < k! es cierta para un k >= 7, entonces también es cierta para k+1. Como hemos verificado que la base de la inducción es cierta para n = 7, concluimos que la desigualdad 3^n < n! es cierta para todo n >= 7.

**2. Muestre usando inducción que 21 divide:**
$$4^{n+1}+5^{2n-1} \text{ para todo }n\geq 1$$

### Paso 1: Base de la inducción
Para n = 1, tenemos que verificar si 21 divide
$$4^{1+1}+5^{2(1)-1}, \text{ es decir, verifiacr si: }4^{2}+5^{1}=16+5=21$$
Es claro que 21 divide 21, por lo tanto, la base de inducción es verdadera.

### Paso 2: Hipótesis de inducción
Supongamos que la afirmación es cierta para un valor n = k, es decir, que 21 divide$$4^{k+1}+5^{2k-1}$$
Esto significa que:
$$4^{k+1}+5^{2k-1}=21m\text{ para algun entero }m$$

### Paso 3: Paso inductivo
Queremos demostrar que 21 divide
$$4^{(k+1)+1}+5^{2(k+1)-1}$$
es decir, demostrar que 21 divide
$$4^{k+2}+5^{2k+1}$$
Podemos reescribir el termino que queremos verificar como:
$$4^{k+2}+5^{2k+1}=4*4^{k+1}+25*5^{2k-1}$$

Ahora usamos la hipotesis de induccion, que nos dice que 21 divide
$$4^{k+1}+5^{2k-1}$$
Entonces, podemos escribir:
$$4^{k+1}+5^{2k-1}=21m \text{ para algun }m$$
Multiplicamos la primera parte por 4 y la segunda parte por 25:
$$$$

