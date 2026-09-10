# Finanzas Sommos — Presupuesto

## Propósito

Documentar la lógica de la pestaña:

`Presupuesto`

Esta referencia pertenece a:

`finanzas-presupuesto-vs`

El modelo histórico de referencia es:

`VS`

del Control antiguo.

---

# Pregunta que responde

El Presupuesto debe responder:

**¿Qué esperaba Sommos que ocurriera económicamente en cada periodo?**

No responde:

**¿Cuánto dinero entró o salió del banco?**

Por lo tanto:

`Budget ≠ Cash`

---

# Fuente principal

Los valores de Budget deben provenir de:

- presupuesto aprobado;
- planificación financiera autorizada;
- histórico validado del Control antiguo;
- revisión presupuestaria explícita.

No construir Budget desde:

- Transacciones;
- Bancos;
- Real P&L actual;
- Cash Flow.

---

# Presupuesto como baseline

El presupuesto funciona como línea base.

No debe cambiar automáticamente porque cambie:

- Actual;
- forecast;
- cash;
- una factura;
- un pago;
- un cobro.

Una desviación respecto al Budget es precisamente información útil.

---

# Estructura

La pestaña puede contener por periodo:

- Categoría
- Budget
- P&L / Actual
- %
- Variación
- Resumen

La estructura viva del Google Sheet prevalece.

No asumir posiciones históricas de filas o columnas.

---

# Categorías

Las categorías de Presupuesto deben poder mapearse a las líneas correspondientes del:

`Real P&L`

No crear una nueva línea presupuestaria sin revisar primero:

- `Config`
- `Operative incomes`
- `Real S&A`
- `Sueldos 2026`
- `Real P&L`

---

# Ingresos presupuestados

Los ingresos presupuestados representan expectativas económicas del periodo.

Deben compararse contra:

`Real P&L`

No contra:

- cobros;
- CxC;
- depósitos bancarios.

Ejemplo:

Ingreso devengado julio y cobrado agosto:

`Budget julio`
vs
`Real P&L julio`

El cobro de agosto no cambia esta comparación.

---

# Gastos presupuestados

Los gastos deben compararse contra el gasto devengado del P&L.

No contra el pago bancario.

Ejemplo:

Factura de julio pagada en agosto:

Correcto:

`Budget julio vs P&L julio`

Incorrecto:

`Budget julio vs cash agosto`

---

# Salarios

El Budget salarial debe compararse contra las líneas salariales de:

`Real P&L`

que provienen de:

`Sueldos 2026`

No comparar contra el total efectivamente pagado por banco.

---

# Grants

Cuando el presupuesto incluya grants:

mantenerlos separados de ingresos operativos cuando el modelo así lo define.

No convertir automáticamente un grant en revenue comercial.

---

# Budget original vs Budget revisado

Si en el futuro se implementan ambas versiones:

preservar:

- Budget original;
- Budget revisado;

por separado.

Mientras el modelo no tenga esa estructura:

no sobrescribir el Budget aprobado silenciosamente.

---

# Histórico reconciliado

Los valores existentes fueron comparados contra:

`VS`

del Control antiguo.

En los periodos validados deben conservarse:

- Budget;
- Actual/P&L;
- porcentajes;
- subtotales;
- resumen.

No modificar históricos sin revisar la fuente.

---

# Ampliación a nuevos meses

Si se necesita extender Presupuesto a nuevos periodos:

1. copiar la estructura lógica;
2. mantener categorías;
3. conectar Actual a Real P&L;
4. mantener fórmulas de porcentaje/variación;
5. validar totales;
6. preservar formato.

No inventar importes presupuestarios para completar meses futuros.

---

# Actualización del Budget

Antes de modificar un importe presupuestado:

confirmar:

- categoría;
- mes;
- importe actual;
- nuevo importe;
- fuente/aprobación;
- si el cambio es prospectivo o retroactivo.

No modificar periodos anteriores sin una instrucción explícita.

---

# Precisión

Mantener precisión suficiente en los valores fuente.

La presentación puede redondearse.

No redondear el Budget almacenado solo para hacer coincidir visualmente un porcentaje.

---

# Relación con Real P&L

`Real P&L`

es la fuente principal de Actual.

Si Actual parece incorrecto:

no escribir primero en Presupuesto.

Revisar:

- P&L;
- Operative incomes;
- Real S&A;
- Sueldos 2026.

---

# Relación con Forecast

Forecast y Budget son conceptos distintos.

`Budget`
→ plan aprobado

`Forecast`
→ expectativa actualizada

Ambos pueden diferir legítimamente.

No reemplazar uno con el otro.

---

# Relación con Cash Flow

Presupuesto no debe utilizarse como fuente de cash histórico.

Puede servir para planificación futura, pero Cash Flow debe utilizar la lógica financiera correspondiente.

---

# QA

Después de modificar Presupuesto:

- releer las celdas;
- comprobar categoría;
- comprobar mes;
- comprobar Budget;
- comprobar Actual;
- comprobar %;
- comprobar subtotal;
- comprobar total;
- comprobar Dashboard si corresponde.

Buscar:

- `#REF!`
- `#VALUE!`
- `#N/A`
- `#DIV/0!`
- `#ERROR!`

---

# Guardrails

- No convertir cash en Actual.
- No cambiar Budget para ocultar desviaciones.
- No inventar Budget.
- No modificar históricos reconciliados silenciosamente.
- No crear categorías sin revisar P&L.
- No hardcodear Actual si puede venir del P&L.
- No aceptar porcentajes con errores.

---

# Regla final

El Presupuesto debe mantener una línea base estable que permita comparar:

**lo que esperábamos**

contra:

**lo que realmente ocurrió económicamente**.
