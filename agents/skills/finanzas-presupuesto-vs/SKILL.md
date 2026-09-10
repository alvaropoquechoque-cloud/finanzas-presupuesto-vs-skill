---
name: finanzas-presupuesto-vs
description: Gestiona y audita el presupuesto financiero de Sommos y su comparación contra Real P&L, preservando la lógica del VS del Control antiguo y separando presupuesto, actual, forecast y variaciones.
---

# Finanzas Sommos — Presupuesto y VS

## Propósito

Gestionar la capa de presupuesto y análisis de variaciones del workflow financiero de Sommos.

Esta skill opera principalmente sobre:

- `Presupuesto`

y utiliza como fuente de resultados reales/devengados:

- `Real P&L`

Su objetivo es permitir responder:

**¿Cómo se está comportando Sommos frente al presupuesto aprobado?**

Debe mantener correctamente separados:

- Budget
- Actual
- Forecast
- Variación
- Variación %

---

# Archivo principal

Google Sheet:

`Finanzas Sommos — Workflow y Control`

Spreadsheet ID:

`1RXy19WZMPQePflFaFeIIHnh09BpJbwOnk6Wumw8bW4E`

URL:

`https://docs.google.com/spreadsheets/d/1RXy19WZMPQePflFaFeIIHnh09BpJbwOnk6Wumw8bW4E/edit`

---

# Modelo histórico de referencia

La lógica de esta skill fue reconstruida tomando como referencia:

`VS`

del Control financiero antiguo.

El objetivo no es únicamente copiar su apariencia.

Debe preservarse especialmente:

- categorías comparables;
- valores de Budget;
- fuente de Actual;
- porcentajes;
- subtotales;
- lógica de comparación;
- periodo real vs futuro.

---

# Principio fundamental

El presupuesto responde:

**¿qué esperábamos que ocurriera?**

El P&L responde:

**¿qué ocurrió o corresponde económicamente al periodo?**

Por lo tanto:

`Budget ≠ Cash`

y:

`Budget ≠ Transacciones`

La comparación correcta debe realizarse principalmente contra:

`Real P&L`

porque el `VS` histórico compara presupuesto contra resultado devengado.

---

# Error que debe evitarse

No utilizar pagos bancarios de `Transacciones` como Actual del presupuesto cuando la línea representa gasto o ingreso devengado.

Ejemplo:

Un servicio devengado en julio pero pagado en agosto:

Correcto:

`Budget julio`
vs
`P&L julio`

Incorrecto:

`Budget julio`
vs
`Pago bancario agosto`

---

# Arquitectura

La dirección principal es:

`Presupuesto`
→ Budget

`Operative incomes`
+
`Real S&A`
+
`Sueldos 2026`
→ `Real P&L`
→ Actual

Luego:

`Budget vs Actual`
→ Variación
→ Análisis

---

# Pestaña Presupuesto

`Presupuesto` contiene la comparación financiera por:

- categoría;
- periodo;
- Budget;
- P&L / Actual;
- porcentaje;
- resumen;
- subtotales.

La estructura exacta debe leerse siempre en vivo.

No asumir filas o columnas históricas.

---

# Fuente de Budget

Los importes presupuestados deben venir del presupuesto aprobado o de la fuente histórica validada.

No reemplazar Budget automáticamente con:

- forecast;
- actual;
- cash;
- promedio histórico.

Budget debe mantenerse estable salvo revisión presupuestaria explícita.

---

# Fuente de Actual

La fuente principal de Actual debe ser:

`Real P&L`

No `Transacciones`.

No `Bancos`.

No `Cash Flow`.

Esto es especialmente importante para:

- servicios;
- salarios;
- gastos recurrentes;
- ingresos devengados;
- impuestos;
- partidas de P&L.

---

# Budget vs Actual

Conceptualmente:

`Variación = Actual - Budget`

o la convención específica utilizada por la hoja viva.

Antes de modificar fórmulas:

verificar qué signo utiliza actualmente `VS` / `Presupuesto`.

No cambiar la convención únicamente por preferencia.

---

# Porcentaje de ejecución

Conceptualmente puede expresarse como:

`Actual / Budget`

Pero debe conservar la fórmula exacta usada por el modelo.

Revisar especialmente:

- Budget = 0;
- Actual = 0;
- gastos negativos/positivos;
- categorías de ingreso;
- subtotales.

No introducir `#DIV/0!`.

---

# Categorías

Las categorías de Presupuesto deben estar alineadas con las líneas relevantes de `Real P&L`.

No crear una categoría presupuestaria nueva sin revisar:

- `Config`;
- `Real S&A`;
- `Operative incomes`;
- `Sueldos 2026`;
- `Real P&L`.

---

# Mapeo hacia Real P&L

Cada línea presupuestaria debe poder explicar qué línea(s) de P&L utiliza.

Ejemplos conceptuales:

`Outsourced services`
→ Real P&L Outsourced services

`Innovatech`
→ Real P&L Innovatech

`Bank fees`
→ Real P&L Bank fees

`Exchange rate differences`
→ línea correspondiente del P&L cuando aplique

No utilizar descripciones bancarias como sustituto del mapeo contable.

---

# Salarios

Los gastos salariales comparados contra Budget deben tomar el resultado del P&L.

El P&L, a su vez, viene de:

`Sueldos 2026`

No comparar presupuesto salarial contra pagos bancarios.

---

# Ingresos

Los ingresos presupuestados deben compararse contra ingresos devengados del P&L.

No contra cobros de clientes.

El cliente puede pagar en otro periodo sin cambiar la ejecución económica del Budget del mes.

---

# Grants

Cuando el presupuesto incluya grants:

mantenerlos separados de revenue operativo cuando la estructura así lo establezca.

No mezclar grants cobrados con ventas.

---

# Histórico vs Forecast

Distinguir:

## Mes real/cerrado

Comparar:

`Budget vs Real P&L actual`

## Mes futuro

Puede utilizarse:

- Budget;
- forecast;
- comparación Budget vs Forecast;

si la estructura viva lo contempla.

No etiquetar forecast como actual.

---

# Forecast

El forecast vivo puede provenir de:

- `Operative incomes`
- `Real S&A`
- `Sueldos 2026`

Pero no debe sobrescribir el Budget.

La diferencia:

`Forecast - Budget`

es información útil.

---

# Presupuesto aprobado

Un Budget debe considerarse una línea base.

Cuando exista una revisión presupuestaria:

no sobrescribir silenciosamente el presupuesto original si se requiere trazabilidad.

Idealmente distinguir:

- Budget original;
- Budget revisado;

si el modelo evoluciona hacia esa estructura.

Mientras no exista esa estructura:

seguir el Budget vivo aprobado.

---

# Periodos disponibles

La pestaña nueva puede contener únicamente determinados meses del análisis.

No inventar columnas futuras solamente porque existan en el Control antiguo.

Si se necesita ampliar:

replicar la lógica y formato existente de manera controlada.

---

# Histórico validado

Los valores de presupuesto y comparación existentes fueron revisados contra `VS` del Control antiguo.

En la revisión anterior:

- Budget;
- P&L;
- porcentajes;
- resumen;
- totales;

fueron conciliados para los periodos disponibles.

No modificar ese histórico sin revisar la fuente.

---

# Precisión

Preservar precisión suficiente en:

- Budget;
- Actual;
- variaciones;
- porcentajes.

La visualización puede redondear.

No redondear la fuente solo para hacer que un porcentaje coincida visualmente.

---

# Diferencias de motor

Pueden existir diferencias extremadamente pequeñas entre:

- Excel;
- Google Sheets;

especialmente en porcentajes.

Si la diferencia es del orden de residuos técnicos y el valor económico coincide:

documentarla.

No crear ajustes contables.

---

# Variación favorable vs desfavorable

No asumir que signo positivo siempre significa favorable.

Para ingresos:

`Actual > Budget`
puede ser favorable.

Para gastos:

`Actual > Budget`
puede ser desfavorable.

Por ello, si se crea semáforo o clasificación:

debe considerar la naturaleza de la línea.

---

# Resumen

El resumen debe facilitar una lectura ejecutiva de:

- ingresos;
- costos;
- gastos;
- desviaciones relevantes.

No duplicar información sin valor analítico.

---

# Materialidad

No todas las diferencias requieren la misma atención.

Una desviación puede evaluarse por:

- USD absoluto;
- porcentaje;
- recurrencia;
- impacto en EBITDA;
- impacto en caja;
- causa.

No marcar como crítica una diferencia de pocos centavos por redondeo.

---

# Análisis de variaciones

Una buena explicación debe responder:

1. cuánto varió;
2. si es favorable o desfavorable;
3. por qué ocurrió;
4. si es temporal o estructural;
5. qué impacto tiene en forecast/runway;
6. si requiere acción.

No inventar causas.

Si no existe evidencia:

indicar que la causa requiere revisión.

---

# Ejemplos de causas

Una variación puede venir de:

- ingreso retrasado;
- nuevo cliente;
- churn;
- contratación;
- vacante;
- aumento salarial;
- proveedor no presupuestado;
- gasto adelantado;
- gasto diferido;
- FX;
- grant;
- proyecto;
- ahorro;
- sobreconsumo.

Estas son categorías conceptuales, no conclusiones automáticas.

---

# No usar Budget para corregir Actual

Nunca cambiar `Real P&L` únicamente porque no coincide con Budget.

Si existe desviación:

esa desviación puede ser precisamente la información que necesitamos analizar.

---

# No usar Actual para cambiar Budget

Tampoco modificar retroactivamente el Budget solo para que la ejecución aparezca mejor.

El presupuesto debe preservar su función como benchmark.

---

# Relación con P&L

Si una cifra Actual no parece correcta:

primero revisar:

`Real P&L`

y sus fuentes:

- Operative incomes;
- Real S&A;
- Sueldos 2026.

No corregir el número directamente dentro de Presupuesto si es una fórmula derivada.

---

# Relación con Devengo

Si el problema está en:

- ingreso del periodo;
- gasto;
- salario;

utilizar:

`finanzas-devengo-operativo`

No arreglar el devengo desde Presupuesto.

---

# Relación con Cash

Presupuesto no debe utilizarse como fuente directa del Cash Flow histórico.

Budget y Cash Flow responden preguntas diferentes.

Puede utilizarse para planeación futura, pero no para reemplazar movimientos reales.

---

# Relación con Runway

Las desviaciones Budget vs Forecast pueden ayudar a explicar:

- cambios de burn;
- cambios en runway;
- necesidades de financiamiento.

La skill de Runway puede consumir estos resultados para análisis.

---

# Relación con Dashboard

El Dashboard puede mostrar indicadores como:

- Budget vs Actual;
- variación;
- ejecución;
- desviaciones relevantes.

No duplicar toda la tabla presupuestaria dentro del Dashboard.

---

# Modificación de Budget

Antes de modificar un importe presupuestado:

1. identificar categoría;
2. identificar mes;
3. comprobar valor actual;
4. confirmar fuente/aprobación;
5. revisar si es Budget original o revisado;
6. cuantificar impacto;
7. comprobar totales.

No modificar Budget únicamente a partir de una conversación ambigua.

---

# Modificación de fórmula Actual

Antes de modificar la columna P&L/Actual:

1. identificar línea equivalente en `Real P&L`;
2. verificar mes;
3. comprobar que no tome `Transacciones`;
4. comprobar signo;
5. comprobar subtotal;
6. comparar contra `VS` histórico cuando corresponda.

---

# QA antes de modificar

- [ ] Leí estructura viva.
- [ ] Identifiqué periodo.
- [ ] Identifiqué categoría.
- [ ] Distinguí Budget de Actual.
- [ ] Identifiqué fuente del Actual.
- [ ] Revisé el mapeo contra Real P&L.
- [ ] Confirmé si es histórico o forecast.

---

# QA posterior

Después de cualquier cambio:

1. releer celdas modificadas;
2. comprobar Budget;
3. comprobar Actual;
4. comprobar variación;
5. comprobar porcentaje;
6. comprobar subtotales;
7. comparar contra P&L;
8. revisar Dashboard cuando corresponda.

Buscar:

- `#REF!`
- `#VALUE!`
- `#N/A`
- `#DIV/0!`
- `#ERROR!`

---

# Check contra VS

Cuando se utilice el antiguo `VS` como referencia:

comparar conceptualmente:

- nombres;
- categorías;
- meses;
- Budget;
- P&L;
- %;
- resumen;
- totales.

No limitar la comparación a totales.

Un total correcto puede esconder líneas mal mapeadas.

---

# Guardrails

- No utilizar Transacciones como Actual del Budget cuando corresponde P&L.
- No confundir cash con gasto/ingreso.
- No cambiar Budget para ocultar una desviación.
- No cambiar P&L para hacer coincidir Budget.
- No inventar causas de variación.
- No inventar forecast.
- No crear categorías nuevas sin revisar Config/P&L.
- No aceptar `#DIV/0!`.
- No modificar históricos reconciliados silenciosamente.
- No redondear prematuramente.
- No declarar igualdad con VS solo comparando totales.

---

# Regla de finalización

Una revisión de presupuesto solo está terminada cuando:

- Budget es correcto;
- Actual viene de Real P&L;
- mapeo por línea es correcto;
- porcentajes son correctos;
- subtotales cierran;
- diferencias están explicadas o identificadas;
- celdas fueron releídas.

---

# Coordinación con otras skills

## `finanzas-config-categorizacion`

Usar para:

- categorías;
- taxonomía;
- catálogos.

## `finanzas-devengo-operativo`

Usar cuando una diferencia provenga de:

- Operative incomes;
- Real S&A;
- Sueldos 2026.

## `finanzas-estados-financieros`

Usar para:

- revisar Real P&L;
- comprobar Actual;
- validar impacto financiero.

## `finanzas-cxc-cxp`

No utilizar CxC/CxP como fuente del Actual del presupuesto.

Consultar solamente si el análisis necesita explicar timing de cobros/pagos.

## `finanzas-bancos-conciliacion`

No utilizar Bancos como fuente del P&L actual.

Puede ayudar a explicar timing de cash, no devengo.

## `finanzas-runway-dashboard`

Usar para:

- mostrar variaciones relevantes;
- conectar variaciones con burn/runway;
- KPIs ejecutivos.

## `finanzas-cierre-mensual`

Cuando exista, usar para:

- comprobar Budget vs Actual después de cerrar el P&L.

---

# Referencias

Consultar cuando corresponda:

- `references/presupuesto.md`
- `references/budget-vs-actual.md`
- `references/analisis-variaciones.md`

---

# Alcance final

Esta skill debe poder responder:

**¿Qué presupuestamos?**

**¿Qué ocurrió económicamente?**

**¿Cuál es la diferencia?**

**¿Por qué importa?**

Sin confundir nunca esas respuestas con cuándo entró o salió el dinero del banco.
