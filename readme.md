# 📊 Proyecto 7: Explorando factores de comportamiento en NovaRetail+

<div align="center">

*Análisis correlacional y exploratorio del comportamiento del cliente para la toma de decisiones estratégicas en comercio electrónico.*

</div>

---

## 📋 1. Resumen Ejecutivo
Este repositorio contiene el desarrollo y las conclusiones técnicas del **Proyecto 7 de Análisis de Comportamiento en NovaRetail+**. El objetivo central del estudio, realizado para el equipo de Crecimiento y Retención, consistió en responder a la interrogante directiva para el cierre de ejercicio: 

> **¿Qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual generado?**

El proyecto emplea técnicas de análisis exploratorio de datos (EDA), matrices de correlación paramétricas/no paramétricas y segmentación multivariante sobre un conjunto de 15,000 registros, traduciendo la estadística avanzada en palancas de crecimiento accionables para la dirección general y los equipos de producto.

---

## 🗂️ 2. Estructura y Datos del Proyecto
* **Dataset analizado:** `novaretail_comportamiento_clientes_2024.csv`
* **Volumen:** 15,000 registros de clientes y 12 variables estructuradas.
* **Dimensiones evaluadas:** Demografía, frecuencia de interacción (`visitas_mes`, `compras_mes`), inversión publicitaria dirigida, nivel de satisfacción, estatus de membresía (`miembro_premium`), tasa de abandono (`abandono`) y la variable objetivo financiera (`ingreso_anual`).

---

## 🔬 3. Metodología y Enfoque Analítico (`Cómo se hizo`)
El pipeline analítico se estructuró bajo un rigor metodológico estricto:
1. **Limpieza e Integridad de Datos:** Validación de valores nulos, tipificación de variables (conversión de decimales a enteros en métricas discretas) y control de consistencia estructural.
2. **Estadísticos Descriptivos y Supuestos:** Evaluación de medidas de tendencia central y dispersión para establecer la línea base del comportamiento de los usuarios (ej. promedio de 10.03 visitas y 1.21 compras mensuales).
3. **Estadística Multivariante Avanzada:**
   * **Coeficiente de Pearson:** Para dependencias lineales continuas.
   * **Correlación Punto Biserial:** Para evaluar el peso estadístico de variables dicotómicas (`miembro_premium`) frente a métricas continuas.
   * **V de Cramér:** Para medir asociaciones e independencia entre variables categóricas nominales (`tipo_dispositivo`, `region`, `abandono`).

---

## 💡 4. Descubrimientos y Hallazgos Principales
El análisis riguroso permitió desmitificar suposiciones comerciales y aislar los inductores reales del negocio:

* **El motor transaccional (`compras_mes` vs. `ingreso_anual`):** Se identificó una correlación lineal cuasi-determinística de **$r = 0.97$**. Cada transacción adicional es el multiplicador directo del valor económico del cliente. La estrategia comercial debe priorizar la migración de usuarios del tramo de 0–1 compra a frecuencias recurrentes $\ge 2$.
* **Fricción en el embudo publicitario:** El gasto en pauta dirigida cumple su objetivo primario de atracción de tráfico ($r = 0.58$ con `visitas_mes`), pero la conversión transaccional se debilita ($r = 0.35$ frente a compras), evidenciando un cuello de botella en la experiencia de usuario (UX) o pasarela de pagos que requiere optimización CRO.
* **Homogeneidad demográfica vs. Estatus Premium:** Las variables demográficas tradicionales (`edad`, `nivel_ingreso` estimado) muestran correlaciones planas frente al ingreso ($r \approx 0.017$). El único factor conductual diferenciador real es la condición de suscriptor premium (asociación significativa con el abandono, $V = 0.1202$). El consumo es transversal y democrático.
* **Concentración financiera regional:** Aunque el ingreso per cápita es uniforme en el territorio, la región Norte concentra el mayor bloque absoluto de clientes (4,395 usuarios) y un volumen de ingresos acumulado superior (161,345 unidades monetarias), dictando una priorización geográfica del presupuesto operativo.

---

## ⚠️ 5. Limitaciones Metodológicas
* **Correlación $\neq$ Causalidad:** Las métricas reflejan asociaciones y co-variación robusta, mas no prueban causalidad directa ni efectos de intervención aislados en experimentos controlados.
* **Naturaleza Estática (Cross-Sectional):** El estudio representa un corte analítico al cierre de periodo, limitando el seguimiento longitudinal del ciclo de vida del cliente (LTV).
* **Factores Externos Omitidos:** Ausencia de variables macroeconómicas, estacionales o de poder adquisitivo externo por localidad.

---

## 🚀 6. Próximos Pasos Estratégicos
1. **Implementación de Clivajes RFM:** Agrupar a los 15,000 usuarios en segmentos de Recencia, Frecuencia y Monetización para focalizar campañas de retención automatizada.
2. **Modelo Predictivo de Abandono (Churn Prediction):** Desarrollar un algoritmo de aprendizaje supervisado (como Regresión Logística o XGBoost) apalancado en la variable binaria `abandono` para la detección temprana de riesgo de fuga.
3. **Enriquecimiento del Ecosistema de Datos:** Integrar la antigüedad del cliente (fecha de registro) y taxonomías detalladas de productos en futuras iteraciones analíticas.

---
<div align="center">
*Desarrollado como parte del portafolio analítico senior de NovaRetail+.*
</div>
