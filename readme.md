# 📊 NovaRetail+ — Análisis de Comportamiento y Factores de Ingreso

> **Resumen Ejecutivo (BLUF):** Este proyecto, desarrollado en el marco de la ruta de especialización en Data Analysis de TripleTen, evalúa los inductores clave del ingreso en una plataforma de comercio electrónico de 15,000 registros. Mediante análisis exploratorio y estadístico avanzado, se aisló el motor transaccional primario ($r = 0.97$ en compras mensuales) y se identificaron cuellos de botella en la conversión publicitaria, proporcionando a la dirección una hoja de ruta accionable para optimizar la retención y el valor de vida del cliente (LTV).

## 📁 1. Estructura y Datos del Proyecto
* **Dataset analizado:** `novaretail_comportamiento_clientes_2024.csv`
* **Volumen:** 15,000 registros de clientes y 12 variables estructuradas.
* **Dimensiones evaluadas:** Demografía, frecuencia de interacción (`visitas_mes`, `compras_mes`), inversión publicitaria, nivel de satisfacción, estatus de membresía (`miembro_premium`), tasa de abandono (`abandono`) y la variable objetivo financiera (`ingreso_anual`).
* **Espacio de Conocimiento:** Centralizado en el notebook 📋 [Creación 'Readme' para proyectos DA](https://gemini.google.com/notebook/b33dc643-a979-4966-9690-bc2edf65bb2c).

---

## ⚙️ 2. Metodología y Enfoque Analítico (Cómo se hizo)
El pipeline analítico implementó un rigor metodológico estructurado en tres fases:
1. **Limpieza e Integridad de Datos:** Validación de valores nulos, tipificación estricta de variables (conversión de decimales a enteros en métricas discretas) y control de consistencia estructural.
2. **Estadísticos Descriptivos y Supuestos:** Evaluación de medidas de tendencia central y dispersión para fijar la línea base del comportamiento (ej. promedio de 10.03 visitas y 1.21 compras mensuales).
3. **Estadística Multivariante Avanzada:**
   * **Coeficiente de Pearson:** Para dependencias lineales continuas.
   * **Correlación Punto Biserial:** Para evaluar el peso estadístico de variables dicotómicas (`miembro_premium`) frente a métricas continuas.
   * **V de Cramér:** Para medir asociaciones e independencia entre variables categóricas nominales (`tipo_dispositivo`, `region`, `abandono`).

---

## 📊 3. Descubrimientos y Hallazgos Principales (Core)
El análisis cuantitativo permitió desmitificar suposiciones comerciales y aislar los inductores reales del negocio:

* **El motor transaccional (`compras_mes` vs. `ingreso_anual`):** Se identificó una correlación lineal cuasi-determinística de **$r = 0.97$**. Cada transacción adicional multiplica de forma directa el valor económico del cliente, orientando la estrategia a migrar usuarios del tramo de 0–1 compra a frecuencias recurrentes $\ge 2$.
* **Fricción en el embudo publicitario:** El gasto en pauta dirigida atrae tráfico eficazmente ($r = 0.58$ con `visitas_mes`), pero la conversión transaccional se debilita ($r = 0.35$ frente a compras), evidenciando un cuello de botella en la experiencia de usuario (UX) o pasarela de pagos que requiere optimización CRO.
* **Homogeneidad demográfica vs. Estatus Premium:** Las variables demográficas tradicionales (`edad`, `nivel_ingreso` estimado) muestran correlaciones planas frente al ingreso ($r \approx 0.017$). El consumo es transversal y democrático, siendo la condición de suscriptor premium el único factor conductual diferenciador real (asociación significativa con el abandono, $V = 0.1202$).
* **Concentración financiera regional:** Aunque el ingreso per cápita es uniforme en el territorio, la región Norte concentra el mayor bloque absoluto de clientes (4,395 usuarios) y un volumen de ingresos acumulado superior (161,345 unidades monetarias), dictando una priorización geográfica del presupuesto operativo.

---

## ⚠️ 4. Limitaciones Metodológicas
* **Correlación $\neq$ Causalidad:** Las métricas reflejan asociaciones y co-variación robusta, mas no prueban causalidad directa ni efectos de intervención aislados en experimentos controlados.
* **Naturaleza Estática (Cross-Sectional):** El estudio representa un corte analítico al cierre de periodo, limitando el seguimiento longitudinal del ciclo de vida del cliente (LTV).
* **Factores Externos Omitidos:** Ausencia de variables macroeconómicas, estacionales o de poder adquisitivo externo por localidad.

---

## 🚀 5. Próximos Pasos Estratégicos
1. **Implementación de Clivajes RFM:** Agrupar a los 15,000 usuarios en segmentos de Recencia, Frecuencia y Monetización para focalizar campañas de retención automatizada.
2. **Modelo Predictivo de Abandono (Churn Prediction):** Desarrollar un algoritmo de aprendizaje supervisado (como Regresión Logística o XGBoost) apalancado en la variable binaria `abandono` para la detección temprana de riesgo de fuga.
3. **Enriquecimiento del Ecosistema de Datos:** Integrar la antigüedad del cliente (fecha de registro) y taxonomías detalladas de productos en futuras iteraciones analíticas.

---
<div align="center">
*Desarrollado como parte del portafolio analítico senior en el programa de Data Analysis de TripleTen.*
</div>
