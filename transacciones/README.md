# 💰 Sistema de Transacciones en Obsidian

Esta carpeta contiene ejemplos de cómo registro y gestiono manualmente mis **transacciones financieras** (gastos, ingresos, transferencias) dentro de Obsidian. El sistema está diseñado para ser:

- ✅ Simple y flexible (basado en archivos Markdown)
- 📊 Analizable (usando `Dataview` y `DataviewJS`)
- 🤖 Automatizable (mediante plantillas con `Templater`)

---

## 📦 ¿Cómo funciona?

Cada transacción es una **nota individual** con propiedades estructuradas (frontmatter plano, no YAML) que describen la operación realizada. Estas notas se crean usando una plantilla y se nombran con un ID único.

---

## 🧾 Estructura de una transacción

```markdown
date:: 2025-04-01
account:: RappiCard
amount:: -32000
type:: gasto
category:: mercado
id:: T2025-04-01-COMPRA-MERCADO
````

### 🧩 Campos explicados:

- `date` → Fecha de la transacción (`YYYY-MM-DD`)
- `account` → Cuenta o medio de pago (ej. `Nequi`, `RappiCard`, `Lulo`)
- `amount` → Valor numérico. Positivo para ingresos, negativo para gastos.
- `type` → `gasto`, `ingreso`, o `transferencia`
- `category` → Clasificación general (`comida`, `transporte`, `suscripciones`, etc.)
- `id` → Identificador único, usado también como nombre del archivo

---

## ⚙️ Automatización con plantillas

Uso **Templater** para generar automáticamente nuevas transacciones con el formato correcto.

Ejemplo de plantilla:

```markdown
<%*
const fecha = tp.date.now("YYYY-MM-DD");
const id = "T" + tp.date.now("YYYY-MM-DD") + "-" + tp.file.title.toUpperCase();
-%>

date:: <%= fecha %>
account:: 
amount:: 
type:: gasto
category:: 
id:: <%= id %>

> Descripción aquí.
```

---

## 🔍 Consultas con Dataview

Con `Dataview`, puedo hacer tablas como:

```"dataview"
table date, category, amount
from "transacciones"
where type = "gasto"
sort date desc
```

O sumar los gastos del mes actual:

```"dataview"
sum
from "transacciones"
where type = "gasto" and date >= date(2025-04-01) and date <= date(2025-04-30)
```

---

## 📊 Dashboards con DataviewJS

Con `DataviewJS`, genero dashboards como:

```js
let gastos = dv.pages('"transacciones"')
  .where(t => t.type === "gasto" && t.date.month === 4)
  .groupBy(t => t.category)
  .map(g => [g.key, g.rows.reduce((acc, row) => acc + row.amount, 0)]);

dv.table(["Categoría", "Total"], gastos);
```

Esto produce una tabla como:

| Categoría  | Total   |
| ---------- | ------- |
| comida     | -92,000 |
| transporte | -48,000 |
| servicios  | -85,000 |
## 📷 Ejemplos visuales del sistema

A continuación se muestran algunos ejemplos de cómo se visualizan las transacciones dentro del vault:

### 🧾 Visualización 1
![Visualización 1](1.png)

### 🧾 Visualización 2
![Visualización 2](2.png)

### 🧾 Visualización 3
![Visualización 3](3.png)


---

## 📁 Organización de esta carpeta

- `T2025-04-01-COMPRA-MERCADO.md`: Ejemplo de gasto
- `T2025-04-03-RECARGA-NEQUI.md`: Ejemplo de ingreso
- `README.md`: Este archivo

---

## 💡 Recomendaciones para expansión

- Añadir campo `etiqueta::` para multi-categorías
- Validar duplicados por ID
- Enlazar a `clases` cuando sea un gasto académico
- Integrar un campo `persona::` para gastos compartidos

---

## 🔒 Privacidad

Este repositorio muestra ejemplos anonimizados o ficticios. Mi vault personal completo no está publicado.

---

