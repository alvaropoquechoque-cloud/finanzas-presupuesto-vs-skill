# Finanzas Sommos — Análisis de variaciones

## Propósito

Definir cómo analizar y comunicar las diferencias entre:

- Budget;
- Actual;
- Forecast.

Esta referencia pertenece a:

`finanzas-presupuesto-vs`

El objetivo es transformar una diferencia numérica en información útil para gestión.

---

# Preguntas mínimas

Para una variación material responder:

1. ¿Cuánto fue la diferencia?
2. ¿Es favorable o desfavorable?
3. ¿Cuál es la causa?
4. ¿Es timing o estructural?
5. ¿Se repetirá?
6. ¿Qué impacto tiene en resultado y caja?
7. ¿Requiere una acción?

---

# No inventar causas

Una fórmula puede mostrar:

`Actual > Budget`

pero no explica por qué.

No inferir automáticamente:

- retraso;
- ahorro;
- sobrecosto;
- churn;
- contratación;

sin evidencia.

Cuando no exista suficiente información:

indicar:

`Causa pendiente de validación`

---

# Materialidad absoluta

Una variación puede ser material por su importe en USD.

No existe necesariamente un único umbral universal.

Evaluar respecto a:

- tamaño de categoría;
- resultado mensual;
- burn;
- caja disponible.

---

# Materialidad porcentual

Una variación porcentual alta puede ser poco importante si el importe base es muy pequeño.

Ejemplo conceptual:

Budget USD 10
Actual USD 20

Variación:

100%

pero solo:

USD 10

No priorizar únicamente por porcentaje.

---

# Materialidad combinada

Una mejor práctica es revisar:

- USD absoluto;
- %;
- recurrencia.

Una desviación moderada durante seis meses puede ser más importante que una desviación grande de una sola vez.

---

# Favorable vs desfavorable

## Ingresos

Generalmente:

`Actual > Budget`
→ favorable

`Actual < Budget`
→ desfavorable

## Gastos

Generalmente:

`Actual < Budget`
→ favorable

`Actual > Budget`
→ desfavorable

Pero siempre revisar la naturaleza de la cuenta.

---

# Variación por timing

Ocurre cuando el evento sigue esperado pero cambia de periodo.

Ejemplos:

- factura llega un mes después;
- cliente se factura después;
- contratación se retrasa;
- viaje se mueve de mes.

No interpretar automáticamente como ahorro o pérdida permanente.

---

# Variación estructural

Cambia la economía futura.

Ejemplos:

- nuevo headcount;
- aumento salarial;
- nuevo proveedor;
- renegociación;
- nuevo cliente;
- churn;
- cambio permanente de infraestructura.

Debe incorporarse al forecast cuando corresponda.

---

# Variación one-off

Evento no recurrente.

Ejemplos:

- gasto legal puntual;
- viaje extraordinario;
- ingreso excepcional;
- ajuste fiscal;
- costo de cierre.

No extrapolar automáticamente al futuro.

---

# Variación de FX

Puede surgir por:

- moneda local;
- TC;
- diferencia cambiaria.

Separar:

- mayor gasto económico;
- simple efecto de traducción.

No modificar el presupuesto histórico para absorber FX realizado.

---

# Variación salarial

Puede explicarse por:

- vacante;
- contratación;
- salida;
- aumento;
- bono;
- cambio de mes de incorporación.

Consultar:

`Sueldos 2026`

antes de concluir.

---

# Variación de S&A

Puede surgir por:

- proveedor;
- cambio contractual;
- factura extraordinaria;
- cutoff;
- gasto adelantado/retrasado.

Consultar:

`Real S&A`

---

# Variación de ingresos

Puede surgir por:

- facturación;
- nuevo cliente;
- retraso de implementación;
- churn;
- menor volumen;
- mantenimiento;
- proyecto adicional.

Consultar:

`Operative incomes`

No utilizar cobros como explicación automática.

---

# Grants

Analizar grants separadamente.

Un grant:

- aprobado;
- devengado;
- cobrado;

puede tener tres momentos distintos.

No interpretar retraso de cash como caída de revenue operativo.

---

# Impacto en EBITDA

Para una variación material:

revisar si impacta:

`EBITDA`

Esto permite distinguir desviaciones operativas de partidas financieras o de caja.

---

# Impacto en Cash Flow

Una desviación de P&L no siempre impacta cash en el mismo mes.

Ejemplo:

gasto mayor devengado pero todavía no pagado.

Por eso el análisis puede mencionar separadamente:

- impacto P&L;
- impacto cash.

---

# Impacto en Runway

Cuando una desviación sea recurrente:

revisar si modifica:

- core burn;
- cash forecast;
- runway;
- necesidad de financiamiento.

No actualizar Runway desde esta skill directamente salvo que corresponda al flujo definido.

---

# Formato de explicación

Una buena explicación debe ser breve y accionable.

Ejemplo conceptual:

`Outsourced services: +USD 1.2k desfavorable vs Budget, explicado por servicios legales no presupuestados. One-off; no se espera repetición en octubre.`

Evitar explicaciones vagas como:

`Gastamos más de lo esperado.`

---

# Top variaciones

Para un resumen ejecutivo:

priorizar las variaciones que más explican el resultado.

No listar todas las líneas si muchas son inmateriales.

---

# Recomendación de ranking

Puede priorizarse por:

`ABS(Variación USD)`

y después revisar:

- %;
- naturaleza;
- recurrencia.

No automatizar una conclusión únicamente por ranking.

---

# Forecast posterior

Cuando se confirme que una variación es estructural:

puede ser necesario actualizar:

- Operative incomes;
- Real S&A;
- Sueldos 2026;

desde:

`finanzas-devengo-operativo`

No modificar esas fuentes desde análisis de presupuesto sin el flujo correcto.

---

# Budget no se reescribe

Una desviación real no justifica modificar el Budget original.

El análisis debe conservar la referencia contra la cual se evaluó desempeño.

---

# Dashboard

El Dashboard puede mostrar:

- variación Budget vs Actual;
- principales desviaciones;
- impacto en runway.

No debe convertirse en una réplica completa de Presupuesto.

---

# QA del análisis

Antes de comunicar una causa:

- validar valor de Budget;
- validar valor Actual;
- validar fórmula;
- revisar fuente;
- confirmar si es ingreso/gasto;
- revisar timing;
- confirmar evidencia de la causa.

---

# Guardrails

- No inventar explicaciones.
- No confundir favorable matemático con favorable financiero.
- No tratar timing como ahorro permanente.
- No extrapolar one-offs automáticamente.
- No modificar Budget para reducir la variación.
- No ignorar impacto en cash cuando sea relevante.
- No usar porcentajes sin mirar USD.

---

# Regla final

El objetivo del análisis de variaciones no es explicar todas las diferencias.

Es identificar:

**qué cambió, por qué importa y qué decisión debería provocar**.
