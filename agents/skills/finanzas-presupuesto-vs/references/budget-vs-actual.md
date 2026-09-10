# Finanzas Sommos — Budget vs Actual

## Propósito

Documentar cómo debe compararse:

`Budget`

contra:

`Actual / Real P&L`

Esta referencia pertenece a:

`finanzas-presupuesto-vs`

La lógica histórica de referencia proviene de:

`VS`

del Control antiguo.

---

# Regla principal

La comparación correcta es:

`Presupuesto vs Real P&L`

No:

`Presupuesto vs Transacciones`

No:

`Presupuesto vs Bancos`

No:

`Presupuesto vs Cash Flow`

---

# Por qué

El presupuesto y el P&L operan principalmente bajo una lógica económica/devengada.

Transacciones y Bancos representan principalmente cash.

Por lo tanto:

un pago o cobro puede ocurrir en un periodo diferente al gasto o ingreso relacionado.

---

# Fuente de Actual

Para cada categoría:

buscar la línea correspondiente en:

`Real P&L`

El valor del periodo debe alimentar el campo:

`P&L`

o:

`Actual`

de Presupuesto.

No repetir manualmente un valor si puede referenciarse correctamente.

---

# Mapeo

Cada línea de Budget debe tener una correspondencia clara con P&L.

Ejemplo:

`Outsourced services`
→ `Real P&L / Outsourced services`

`Innovatech`
→ `Real P&L / Innovatech`

`Bank fees`
→ `Real P&L / Bank fees`

`Marketing services`
→ `Real P&L / Marketing services`

Las denominaciones exactas deben leerse del Sheet vivo.

---

# Mapeos agregados

Una línea presupuestaria puede eventualmente corresponder a varias líneas del P&L.

Si esto ocurre:

documentar explícitamente el agregado.

No elegir una única línea arbitraria si el Budget representa un subtotal.

---

# Variación absoluta

La fórmula puede seguir conceptualmente:

`Variación = Actual - Budget`

o la convención vigente del Sheet.

Antes de cambiarla:

comprobar qué signo utiliza el modelo actual.

No cambiar de convención a mitad del archivo.

---

# Ejecución porcentual

Una fórmula típica es:

`Actual / Budget`

pero debe respetarse la metodología del `VS` validado.

Tratar especialmente:

`Budget = 0`

para evitar:

`#DIV/0!`

---

# Cuando Budget = 0

Si:

`Budget = 0`

y:

`Actual = 0`

el porcentaje debe manejarse según la convención del modelo, por ejemplo:

- vacío;
- 0%;
- N/A lógico.

Si:

`Budget = 0`

y:

`Actual ≠ 0`

la desviación debe destacarse como gasto/ingreso no presupuestado.

No ocultarla con un porcentaje artificial.

---

# Ingresos

Para ingresos:

`Actual > Budget`

suele representar una variación favorable.

Pero no aplicar una regla visual sin revisar la naturaleza de la línea.

---

# Gastos

Para gastos:

`Actual > Budget`

suele representar una variación desfavorable.

Por eso:

el signo matemático y la evaluación financiera no son lo mismo.

---

# Semáforo

Si se utiliza semáforo:

debe considerar el tipo de cuenta.

Ejemplo conceptual:

Ingreso por encima del Budget
→ favorable

Gasto por encima del Budget
→ desfavorable

No usar una única regla:

`positivo = verde`

para todas las líneas.

---

# Actual vs Forecast

En meses cerrados:

`Actual = Real P&L realizado/devengado`

En meses futuros:

puede compararse:

`Budget vs Forecast`

si la estructura lo permite.

No llamar Actual a un forecast.

---

# Histórico vs futuro

La frontera debe ser clara.

Por ejemplo:

mes cerrado
→ Actual

mes futuro
→ Forecast

No mezclar ambas bases dentro de un mismo campo sin indicarlo.

---

# Diferencias por timing

Una desviación puede ser temporal.

Ejemplo:

un gasto presupuestado en septiembre ocurre en octubre.

Esto puede generar:

- favorable septiembre;
- desfavorable octubre;

sin que el total anual necesariamente cambie.

Identificar timing antes de concluir que existe ahorro real.

---

# Diferencias estructurales

Una desviación estructural puede provenir de:

- cambio de proveedor;
- contratación;
- baja;
- nuevo cliente;
- churn;
- aumento permanente de costo.

Estas diferencias afectan el forecast futuro y deben tratarse de forma distinta a timing.

---

# Revisión contra VS

Cuando se compare con el antiguo `VS`:

validar:

- categorías;
- orden;
- Budget;
- P&L;
- %;
- subtotales;
- totales.

No comparar únicamente el total mensual.

---

# Precisión

Diferencias extremadamente pequeñas pueden deberse al motor de cálculo.

Ejemplo:

variaciones del orden de:

`0.0000000001`

en porcentajes.

Si los valores fuente son iguales:

no introducir ajustes contables.

---

# QA

Para cada periodo comprobar:

- Budget correcto;
- Actual correcto;
- fórmula correcta;
- categoría correcta;
- signo correcto;
- porcentaje válido;
- subtotal correcto;
- total correcto.

---

# Guardrails

- No comparar Budget con cash.
- No hardcodear Actual.
- No invertir signos sin revisar convención.
- No ocultar gastos no presupuestados.
- No llamar Actual a Forecast.
- No introducir ajustes para reproducir únicamente un porcentaje visual.

---

# Regla final

Budget vs Actual debe medir:

**desempeño económico frente al plan**

no:

**timing de pagos y cobros bancarios**.
