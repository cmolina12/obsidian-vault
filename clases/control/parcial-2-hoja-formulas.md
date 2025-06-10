**Conversion de unidades**
***
- **Unificación a las unidades de la media:** Si la media $\mu$ está en unidades *x*, todo debe expresarse en esa misma unidad → convertir $T$ y $\tau$ a la unidad de la media: si $\mu$ es mensual y $\tau = 5$ días, entonces $\tau = \frac{5}{30}$ meses → si $\mu$ es anual y $T = 15$ días, entonces $T = \frac{15}{360}$ años → luego: $\mu_{T} = \mu \cdot T$, $\mu_{\tau} = \mu \cdot \tau$, $\mu_{T+\tau} = \mu \cdot (T + \tau)$ → para la desviación: $\sigma_{T} = \sigma \cdot \sqrt{T}$, $\sigma_{\tau} = \sigma \cdot \sqrt{\tau}$, $\sigma_{T+\tau} = \sigma \cdot \sqrt{T + \tau}$ 
- **Conversión de tasas (i) simples:** $i_{\text{mes}} = \frac{i_{\text{año}}}{12}$, $i_{\text{día}} = \frac{i_{\text{año}}}{360}$ → para convertir al revés: $i_{\text{año}} = i_{\text{mes}} \cdot 12$ o $i_{\text{año}} = i_{\text{día}} \cdot 360$ → usar siempre la unidad de tiempo que corresponde con la media.
- **Si te dan la varianza en lugar de la desviación:** La varianza es $\sigma^2$, debes obtener la desviación estándar como $\sigma = \sqrt{\text{Varianza}}$ → luego puedes usarla como siempre: $\sigma_{T} = \sigma \cdot \sqrt{T}$, $\sigma_{T+\tau} = \sigma \cdot \sqrt{T + \tau}$ → si necesitas convertir primero el tiempo, asegúrate de que esté en la unidad de la media antes de aplicar la raíz.
- **Si la demanda depende de una variable aleatoria (X) como ( D = aX + b ):** calcular media como $\mu_D = a \cdot \mu_X + b$ y desviación como $\sigma_D = a \cdot \sigma_X$ → si te dan varianza: primero obtener $\sigma_X = \sqrt{\text{Var}(X)}$ → aplicar esto antes de cualquier cálculo de $F(Q)$, $Q$, $L(z)$, etc.


***Vendedor de diarios*** 
***
### <mark style="background: #D2B3FFA6;">Para todos los casos</mark> 
**Entradas:** $\mu\text{ (Media)}$: unidades/tiempo, $\sigma\text{ (Desviacion Estandar)}$: unidades/tiempo, $c\text{ (Costo unitario)}$, $v \text{ (Precio venta)}$, $r\text{ (Valor recompra)}$, $C_{o}\text{ (Costo sobrantes)}$, $C_{u}\text{ (Costo faltantes)}$, $F(Q)\text{ (Proporcion de la demanda): null}$  

==r:== **Caso 1: "Se revende al X% del precio de venta" →**  $r = \frac{X}{100} \cdot v$ **Caso 2: "Se revende al X% del costo" →**  $r = \frac{X}{100} \cdot c$ **Caso 3: "El X\% de las unidades se revende al Y\% del precio de venta" →**  $r = \frac{X}{100} \cdot \frac{Y}{100} \cdot v$ **Caso 4: "Se pierde X% del costo" →**  $r = \left(1 - \frac{X}{100} \right) \cdot c$ **Caso 5: "No se recupera nada / se desechan" →**  $r = 0$ **Caso 6: "Una tercera parte de las unidades no vendidas se vende con 40% de descuento sobre el precio de venta, el resto se dona" →** $r = \frac{1}{3} \cdot (1 - 0.40) \cdot v$ <mark style="background: #FF5582A6;">costos:</mark> $C_{u}=v-c$, $C_{o}=c-r$ <mark style="background: #FFB86CA6;">F(Q):</mark> $\frac{C_{u}}{C_{u}+C_{o}}=\text{Nivel de servicio tipo I en D continuos}$
<mark style="background: #ABF7F7A6;">Niveles de servicio:</mark> **Nivel de servicio tipo I ($\alpha$):** “probabilidad de no tener faltantes“, “probabilidad de satisfacer toda la demanda”, “probabilidad de no quedarse sin inventario” **Nivel de servicio tipo II ($\beta$):** “porcentaje/proporacion de la demanda cubierta o satisfecha” **Nota:** Si el enunciado da la “probabilidad de tener faltantes”, el nivel de servicio tipo I se calcula como $1 - \text{esa probabilidad}$ porque son eventos complementarios.
***
<mark style="background: #D2B3FFA6;">Continuo - Normal:</mark> 
**Paso 1:** Sacar **relación critica** con formula de $F(Q)$, **z** con `=DISTR.NORM.ESTAND.INV( F(Q) )`, **Q** con $\mu+(z*\sigma)$ **Paso 2:** Sacar **L(z)** con `=DISTR.NORM(z;0;1;0)-z(1-DISTR.NORM.ESTAND(z))`, **L(-z)** con la formula anterior pero todos los $z$ con negativos, **E(Sobrantes)** con $\sigma*L(-z)$ y **E(Faltantes)** con $\sigma*L(z)$, **costos sobrantes** y **costos faltantes** y **costo total** **Paso 3:** Sacar **E(Demanda)** que es igual a la media, **servicio tipo I** que es F(Q), y **servicio tipo II** que es $1-\frac{\text{E(Faltantes)}}{\text{E(Demanda)}}$ **Paso 4:** Si dicen que la empresa quiere tener **X** nivel de servicio tipo I, **se hace el mismo proceso** con ese nivel como el F(Q) **Paso 5:** Si me dan la **demanda exacta** y piden el costo de la politica, hago $\text{Faltantes = }\text{Demanda exacta}-Q_{anterior}$ y el costo de faltantes es el mismo costo de la politica, o sobrantes si es viceversa. 

<mark style="background: #FF5582A6;">Continuo - Uniforme:</mark> 
**Paso 1:** Mirar el **a** y **b** que me dan **Paso 2:** Sacar **F(Q)** con formula general y $Q=(F(Q)(b-a))+a$ **Paso 3:** Sacar **E(Sobrantes)** $=\frac{(Q-a)^2}{2(b-a)}$ y **E(Faltantes)** $=\frac{(b-Q)^2}{2(b-a)}$  **Paso 4:** Sacar **E(Demanda)** $=\frac{a+b}{2}$ y **Servicio Tipo II** con $1-\frac{E(\text{Faltante})}{\text{E(Demanda)}}$ **Paso 5:** Costo sobrantes y faltantes con formula general. **Nota:** La formula de E(Sobrantes) y E(Faltantes) **solo** aplica si Q esta entre a y b. Si no, se calcula asi:

$$
\text{Si } Q > b: 
\quad 
\begin{cases}
E(\text{Sobrantes}) = b \\
E(\text{Faltantes}) = 0
\end{cases}
\quad
\text{y si } a > Q:
\quad
\begin{cases}
E(\text{Sobrantes}) = 0 \\
E(\text{Faltantes}) = a
\end{cases}
$$

<mark style="background: #BBFABBA6;">Discreto - Frecuencia:</mark>
**Paso 1:** Armar la tabla. **Columna 1:** Demanda **Columna 2:** Frecuencia de cada demanda **Columna 3:** Probabilidad de cada demanda con $\frac{\text{Frecuencia(x)}}{\text{Suma de frecuencias}}$ **Columna 4:** Probabilidad acumulada, sumando las probabilidades. **Paso 2:** Sacar la relación critica con formula general, ahora buscar donde la probabilidad acumulada > F(Q), ese es la fila optima. **Paso 3:** **Columna 5 y 6:** Sobrantes y Faltantes con formulas de **Poisson**. Luego, **E(Sobrantes)** y **E(Faltantes)** con formulas de **Poisson** y **E(Demanda)** con `SUMAPRODUCTO(Todas las demandas, Todas las probabilidades)`. **Servicio tipo I** es probabilidad acumulada en fila optima, **Servicio tipo II** con $1-\frac{\text{E(Faltante)}}{\text{E(Demanda)}}$.

<mark style="background: #ADCCFFA6;">Discreto - Poisson:</mark> 
**Paso 1:** Sacar **F(Q)** con formula general y **Q, E(Sobrantes), E(Faltantes), y Nivel de Servicio Tipo I y II** con el procedimiento a continuación **Paso 2:** Estructura de la tabla recomendada (columna por columna)
<div style="display: flex; gap: 1rem; align-items: flex-start;">
  <img src="Captura de pantalla 2025-04-24 a la(s) 9.12.24 a.m..png" style="max-width: 50%; height: auto; object-fit: contain;">
  <img src="Captura de pantalla 2025-04-24 a la(s) 9.12.46 a.m..png" style="max-width: 40%; height: auto; object-fit: contain;">
</div>

**x** va desde 0 hasta donde la F(x) acumulada sea casi 1. **El valor en verde indica el menor $Q$ tal que $F(x) \geq F(Q)$**, que es el punto óptimo de pedido en el modelo discreto con Poisson; se selecciona justo después de calcular $F(Q) = \frac{C_u}{C_u + C_o}$ y representa el valor donde se cumple por primera vez la condición de cobertura mínima esperada. **E(Sobrantes)** es entonces `SUMAPRODUCTO(Sobrantes,f(x) en el rango de sobrantes)` y **E(Faltantes)** es `SUMAPRODCUTO(Faltantes, f(x) en el rango de faltantes)` y la **E(Demanda)** es igual a la media. El **servicio tipo I** es el F(x) acumulado en la fila verde, el **servicio tipo 2** se calcula con $1-\frac{\text{E(Faltantes)}}{\text{E(Demanda)}}$.

***QR***
***
Se pide Q cantidad cada vez que la posición del inventario llegue o este por debajo del punto de reorden R. La orden tarda $\tau$ unidades de tiempo en estar disponible. **R siempre debe ser mayor a la demanda ($\mu_{\tau}$), así sabemos si esta correcto**.
- **Si te dan nivel de servicio tipo I o el tipo II ($\alpha = P(D \leq Q)$) → es modelo de ventas perdidas (lost sales)**  
- **Si no me dan nada o es explicito entonces backorders**

$P(\text{No faltantes})=P(x_{\tau}<R)=F(R)=\alpha$

<mark style="background: #FFB86CA6;">Ventas perdidas (Normal)</mark>
$\sigma_{\tau}=\sigma*\sqrt{ \tau }$, $\mu_{\tau}=\mu*\tau$, $R=\mu_{\tau}+\sigma_{\tau}*Z$, z=`INV.NORM.ESTAND(alpha)`, $Q(EOQ)=\sqrt{ \frac{2K\lambda}{h} }$, L(z) = `DISTR.NORM(z;0;1;0)-z(1-DISTR.NORM.ESTAND(z))`, $n(R)\text{ dependiente}=\sigma_{\tau}*L(z)$, $\beta=1-\frac{n(R)}{Q}$, $n(R)\text{ real}=Q*(1-\beta)$, $T=\frac{Q}{\mu}$, $SS=\sigma_{\tau}*Z$, $I=\frac{Q}{2}+SS$, z = `inv.norm.estand(alpha)`

- **Si me dan el tipo I solamente**
Con esa información puedo de una sacar Z, R y SS. **Si nos dicen que Q es EOQ:** Saco L(z) con el z de antes y n(R) con la formula dependiente y puedo sacar $\beta$ con su formula, y $T$ con su formula.
- **Si me dan tipo 1 pero no me dicen EOQ entonces se saca Q con la formula $T=\frac{Q}{\lambda}$** y con el tipo 1 puedo sacar **z, R, L(z), y n(R), y si me piden beta lo puedo sacar ahora con el Q tambien**
- **Si me dan el tipo II solamente, entonces hay que asumir z**
	- Si anteriormente pudimos sacar Q, entonces hago la tabla **n(R) real, L(z) real,** asumo z, **L(z) dependiente, n(R) dependiente** y diferencia **(L(z) dependiente - L(z) real)**. Con esto saco **z** y puedo sacar **tipo 1, SS, R y Iprom**
- **Si me dan ambos resuelvo normal y el Q lo saco con la formula $Q=\frac{n(R)}{1-\beta}$**

**Costos totales**
![[Captura de pantalla 2025-04-24 a la(s) 7.53.33 p.m..png|500]]
<mark style="background: #ADCCFFA6;">Backorders (Iterativo)</mark>
Un "backorder" (o pedido pendiente) es un pedido que se realiza para un producto que no está disponible en stock en el momento de la compra, pero se espera que esté disponible en un futuro cercano.
**Paso 0)** Sacar la media y la desviación **Paso 1)** Encontrar $\tau$, K, i, c, h, p, $\mu_{\tau}$ y $\sigma_{\tau}$ **Paso 3**: $F(R)=1-\frac{Q*h}{p*\lambda}=\text{Tipo 1}$, z=`INV.NORM.ESTAND(F(R))`, $R=\mu_{\tau}+\sigma_{\tau}*Z$, L(z) = Formula general, $n(R)=\sigma_{\tau}*L(z)$, **SIGUIENTE ITERACION**, 

$$Q=\sqrt{ \frac{2*\lambda*(K+p*n(R\text{ anterior}))}{h} }$$

![[Captura de pantalla 2025-04-24 a la(s) 7.45.15 p.m..png|300]]
**Paso 4:** Corremos las iteraciones hasta que converga, o ya no cambien los valores. La iteración donde esto empieza a verse es la optima. Ahora sacamos **Q de la iteracion**, **Tipo 1 = F(R) de la iteracion**, **Tipo 2 = $1-\frac{n(R)}{Q}$**, **n(R) de la iteracion**, **R de la iteracion**, $SS=\sigma_{\tau}*Z$, y **I = Formula inventarios**

**Costos totales:**
![[Captura de pantalla 2025-04-24 a la(s) 7.53.47 p.m..png|500]]

***ST***
***
Cada T periodos de tiempo se pide una cantidad tal que la posición del inventario se eleve al nivel S. También conocido como (S, R). Las órdenes se colocan exactamente cada T unidades de tiempo. 
El nivel objetivo S debe ser mayor o igual a la demanda en T + $\tau$ . ¿Por qué? Porque el objetivo S tiene un componente de la demanda en (𝝀𝝉) y otro de la demanda en T (𝝀𝑻).

$S=(\lambda \tau)+(\lambda T)+SS$ $\lambda(T+\tau)+SS$, $S=\lambda(T+\tau)+SS$, $S=\mu_{T+\tau}+Z\sigma_{T+\tau}$, $Z\sigma_{T+\tau}=SS$. **Nivel de servicio tipo 1 = F(s) = $\alpha$ = Probabilidad de no faltantes en T + $\tau$**. **Nivel de servicio tipo 2 (Proporción de la demanda satisfecha con las existencias)** = $\beta=1-\frac{\text{E(Faltantes)}}{\text{E(Demanda)}}$ = $\beta=1-\frac{n(S)}{\lambda T}$. **n(S)=$\sigma_{T+\tau}L(z)$** o $n(S)=(1-\beta)*\mu T$. **Sacar tipo 1 con $\alpha$=`DISTR.NORM.ESTAND.N(Z;VERDADERO)`**

**Costo total:** $\frac{K}{T}+c\lambda+h\left( \frac{Q}{2}+S -\lambda(T+\tau)\right)+p\left( \frac{n(S)}{T} \right)$ o igual pero el de inventarios con $h\left( \frac{\lambda T}{2} +SS\right)$. 1 - Ordenar, 2 - Adquirir, 3 - Inventarios, 4 - faltantes

<mark style="background: #D2B3FFA6;">Caso Exacto: Normal</mark>
<mark style="background: #FFB86CA6;">Caso 1: Nos dan nivel de servicio tipo 1</mark>
Sacar $\mu T$ y $\sigma T$, $\mu(\tau+T)$ y $\sigma(\tau+T)$. **Paso 1:** Nos dan $\alpha$ que sabemos es F(S), sacamos Z con `INV.NORM.ESTAND(F(S))` y sacamos S con la formula $\mu_{T+\tau}+Z*\sigma_{T+\tau}$. **Paso 2:** Sacar SS con su respectiva formula **Paso 3:** Sacar el valor esperado de faltantes o sobrantes, para esto hay que sacar L(z) para faltantes y L(-z) para sobrantes y sus respectivas formulas son $\sigma_{\tau+T}*L(z)$ y $\sigma_{\tau+T}*L(-z)$. **Paso 4:** Sacar valor esperado de faltantes (N(s)) con su formula, si nos preguntan valor esperado de faltantes entonces multiplicamos por su costo, nos lo deben dar. **Paso 5:** Sacamos **E(Demanda)** con $\mu*T$ y ahi completamos las variables para sacar el **servicio tipo 2**.

<mark style="background: #ABF7F7A6;">Caso 2: Nos dan nivel de servicio tipo 2</mark>
Repetir inicialización del pasado. **Paso 1:** Saco el N(s) real con la formula $(1-\beta)*\mu T$. Para calcular el nivel objetivo S hago la tabla **z, L(z), N(s) dependiente, Dif, S**. Asumo z, saco L(z) con su formula, saco el N(s) dependiente con la formula de más arriba, saco S con la formula $\mu_{T+\tau}+Z*\sigma_{T+\tau}$ **Paso 2:** Saco SS con $Z*\sigma_{T+\tau}$. **Paso 4:** Saco el costo total mensual de la política con la formula del costo total.

<mark style="background: #FFF3A3A6;">Caso Aproximado: Primero QR y luego ST</mark>

<mark style="background: #ADCCFFA6;">Caso Frecuencia</mark>





***Unidades y Teoria***

Generales
- **μ / λ:** demanda promedio → unidades por tiempo (ej. unidades/día) → se usa en todos los modelos  
- **σ:** desviación estándar de la demanda → mide variabilidad → unidades  
- **τ (tau):** lead time → tiempo entre pedir y recibir inventario → días, semanas, meses  
- **T:** intervalo entre revisiones (solo en modelo ST) → tiempo → días, semanas  
- **z:** número de desviaciones estándar que se protegen → refleja el nivel de servicio deseado → sin unidades  
- **SS (stock de seguridad):** unidades extra para cubrir variabilidad durante τ (QR) o T+τ (ST) → unidades  
- **L(z):** valor promedio de faltantes por desviación estándar → se usa para calcular faltantes → sin unidades  
- **L(-z):** valor promedio de sobrantes por desviación estándar → se usa para calcular sobrantes (Newsvendor) → sin unidades  

QR
- **R (punto de reorden):** nivel de inventario en el que se lanza un pedido → debe cubrir la demanda durante el lead time (τ) más un margen de seguridad → unidades
- **n(R):** Valor esperado de los faltantes durante τ cuando el inventario inicial es R → unidades
- **F(R):** probabilidad acumulada de que la demanda durante el lead time sea menor o igual a R → se usa en el QR iterativo como criterio de cumplimiento del servicio tipo I

- **p:** costo por unidad no atendida a tiempo (backorder) → se aplica cada vez que hay faltantes, se ve en QR y ST → unidades monetarias por unidad (ej. $/unidad)
- **h:** costo de mantenimiento por unidad almacenada durante un período de tiempo → unidades monetarias por unidad por tiempo (ej. $/unidad/mes)
- **k:** costo fijo por realizar un pedido → unidades monetarias por pedido (ej. $)
- **c:** costo unitario de adquisición del producto →  $/unidad
- **Costo por faltantes esperados:** representa el impacto económico de no satisfacer parte de la demanda

ST
- **T (intervalo de revisión):** tiempo fijo entre revisiones del inventario → en cada revisión se evalúa cuánto hay y se pide lo necesario para alcanzar el nivel S → tiempo (ej. días, semanas)
- **S (nivel objetivo):** cantidad de inventario que se desea tener justo después de hacer un pedido → debe cubrir la demanda esperada durante el período T + τ → unidades
- **SS (stock de seguridad):** inventario adicional dentro de S para cubrir la variabilidad de la demanda durante el período de cobertura (T + τ) → unidades
- **n(S):** faltantes esperados durante el período T + τ cuando el inventario es S → se usa para calcular servicio tipo II y costo por faltantes → unidades
- **F(S):** probabilidad acumulada de que la demanda durante T + τ sea menor o igual a S → otra forma de representar el nivel de servicio tipo I (idéntico a ( $\alpha$ ))
