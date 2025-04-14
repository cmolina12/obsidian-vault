## Fórmulas

**1.**  
$z = \text{DISTR.NORM.ESTAND.INV}(F(Q))$

**2.**  
$Q^* = \mu + z \cdot \sigma$

**3.**  
$L(z) = \text{DISTR.NORM}(z;0;1;0) - z \cdot (1 - \text{DISTR.NORM.ESTAND}(z))$

**4.**  
$L(-z) = \text{DISTR.NORM}(-z;0;1;0) + z \cdot (1 - \text{DISTR.NORM.ESTAND}(-z))$

**5.**  
$E(Sobrantes) = \int_{0}^{Q}(Q - D)f(x)dx \approx \sigma L(-z)$

**6.**  
$E(Faltantes) = \int_{Q}^{\infty}(D - Q)f(x)dx \approx \sigma L(z)$

---

## Niveles de servicio

### Nivel de servicio tipo I

**Proporción de ciclos sin faltantes**

**Probabilidad de no faltantes**

¿Cuándo no hay faltantes?  
Cuando $D < Q$

$\alpha = P(D < Q) = F(Q)$

---

### Nivel de servicio tipo II

$\beta = 1 - \frac{E(\text{faltantes})}{E(\text{demanda})}$

$E(\text{faltantes}) = \displaystyle\int_{x=Q}^{x=\infty}(D - Q)f(x)dx$

$E(\text{demanda}) = \displaystyle\int_{x=0}^{x=\infty} D f(x)dx$

---

## Fórmula del Punto Óptimo

$\frac{c_u}{c_o} = \frac{v - c}{c - r}$

$F(Q^*) = \frac{c_u}{c_o + c_u} = \frac{v - c}{v - r}$

---

## Fórmula de la demanda esperada

$$E[Ventas] = \begin{cases} Q - E[Sobrantes] \\ E[Demanda] - E[Faltantes] \end{cases}$$

**¿Qué sucedería si lo que me sobra en inventario al final del día lo puedo utilizar para satisfacer la demanda del día siguiente?**

$E[Ventas] = E[Demanda]$

---

![[Vendedor de Diarios - estudiantes.xlsx]]