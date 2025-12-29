# Estadística para Análisis de Datos  

Este repositorio documenta el desarrollo práctico del módulo de **Estadística para Análisis de Datos**, enfocado en estadística descriptiva, distribuciones probabilísticas, inferencia estadística, pruebas de hipótesis, análisis de varianza (ANOVA), **técnicas no paramétricas y bootstrap**, y **modelado predictivo mediante regresión lineal**, con validación empírica de supuestos y análisis reproducible en Python.

El trabajo se desarrolla en **5 días**, siguiendo un enfoque incremental, reproducible y orientado a análisis de datos reales.

---

## Objetivos Generales

- Comprender y aplicar conceptos fundamentales de probabilidad y estadística.
- Modelar correctamente el comportamiento de clientes usando distribuciones probabilísticas adecuadas.
- Validar supuestos estadísticos mediante evidencia empírica y diagnóstico visual.
- Aplicar el Teorema del Límite Central para justificar inferencia paramétrica.
- Formular y contrastar hipótesis estadísticas para la toma de decisiones basadas en datos.
- Comparar múltiples grupos mediante ANOVA y pruebas post-hoc, controlando el error tipo I en contextos reales.
- Construir, evaluar e interpretar **modelos de regresión lineal** con fines explicativos y predictivos.
- Desarrollar análisis reproducibles, documentados y exportables, orientados a portafolio profesional.

---

## Desarrollo por Día

---

## Día 1 – Estadística Descriptiva y Distribuciones de Probabilidad

### Actividades realizadas
- Simulación de comportamiento de clientes (compras y gasto).
- Modelado probabilístico:
  - Distribución **Poisson** para conteo de compras.
  - Distribución **Log-normal** para valores monetarios.
- Análisis descriptivo y probabilístico.
- Aplicación del **Teorema del Límite Central**.
- Comparación empírica entre:
  - Suposición ingenua de normalidad.
  - Distribuciones probabilísticas adecuadas.
- Generación de visualizaciones y exportación de resultados a Excel.

---

### Verificación

Los datos crudos de comportamiento de clientes no siguen una distribución normal. El número de compras anuales es un conteo discreto correctamente modelado por una distribución de Poisson, mientras que el valor de compra presenta asimetría positiva y es mejor representado por una distribución log-normal. Sin embargo, al analizar medias muestrales del gasto total, la distribución resultante converge a una normal, validando empíricamente el Teorema del Límite Central y justificando el uso de estadística paramétrica para inferencia.

---

### Evidencia generada
- Tests de normalidad (rechazo de normalidad en datos crudos).
- Histogramas y gráficos Q-Q.
- Comparación visual:
  - Normal vs Poisson (compras).
  - Normal vs Log-normal (valor de compra).
- Distribución normal de medias muestrales.

---

### Archivos generados
- `analisis_probabilistico_clientes_dia1.ipynb`
- `analisis_probabilistico_clientes_reproducible.xlsx`
- `distribuciones_probabilidad_clientes.png`
- `comparacion_modelos_normal_vs_reales.png`

---

## Día 2 – Pruebas de Hipótesis y Análisis de Campañas de Marketing

### Actividades realizadas
- Simulación de un experimento A/B de marketing (grupo control vs tratamiento).
- Análisis de tasa de conversión mediante prueba de proporciones (Z-test unilateral).
- Análisis de gasto promedio mediante prueba t para muestras independientes (unilateral).
- Cálculo de tamaños del efecto:
  - **Cohen’s h** para proporciones.
  - **Cohen’s d** para medias.
- Construcción de intervalos de confianza unilaterales.
- Análisis de poder estadístico y tamaño muestral requerido.
- Visualización integrada de resultados y resumen ejecutivo.

---

### Verificación

La prueba de proporciones no rechaza H₀ para la tasa de conversión (Z = 1.12, p = 0.132 > 0.05, h = 0.05), por lo que no se detecta una mejora estadísticamente significativa en conversión. En contraste, la prueba t unilateral rechaza H₀ para el gasto promedio (t = 2.21, p = 0.0136 < 0.05, d = 0.10), indicando un aumento significativo. La implementación de la campaña puede considerarse si el aumento en gasto promedio compensa la ausencia de mejora significativa en conversión considerando el retorno económico, el tamaño del efecto y un poder estadístico moderado (0.71).

---

### Evidencia generada
- Resultados numéricos de pruebas de hipótesis (Z-test y t-test).
- Tamaños del efecto (Cohen’s h y d).
- Intervalo de confianza unilateral para diferencia de gasto.
- Análisis de poder estadístico y tamaño de muestra requerido.
- Visualizaciones comparativas y resumen ejecutivo gráfico.

---

### Archivos generados
- `prueba_hipotesis_marketing_dia2.ipynb`
- `resultados_marketing_dia2.xlsx`
- `resultados_prueba_hipotesis_marketing_dia2.png`

---

## Día 3 – Análisis de Varianza (ANOVA) y Segmentación de Clientes por Canal

### Actividades realizadas
- Simulación de un dataset de **Valor de Vida del Cliente (CLV)** segmentado por canal de adquisición.
- Definición de cinco canales con tamaños de muestra desbalanceados.
- Verificación de supuestos del ANOVA:
  - Normalidad por grupo (Shapiro-Wilk).
  - Homocedasticidad de varianzas (prueba de Levene).
- Selección del método estadístico adecuado según los supuestos:
  - Uso de **Welch ANOVA** ante varianzas desiguales.
- Contraste global de igualdad de medias entre canales.
- Identificación de diferencias específicas mediante pruebas post-hoc:
  - T-test de Welch por pares.
  - Corrección de Bonferroni para control del error tipo I.
- Generación de visualizaciones estadísticas y resumen ejecutivo.
- Exportación del dataset original y de todas las tablas de resultados a Excel.

---

### Pregunta Estadística

¿El Valor de Vida del Cliente (CLV) promedio es igual entre los distintos canales de adquisición?

---

### Hipótesis

- **H₀**: μ₁ = μ₂ = μ₃ = μ₄ = μ₅  
  (El CLV promedio es igual en todos los canales)

- **H₁**: Al menos una media es diferente

---

### Verificación

La prueba de Levene rechaza la igualdad de varianzas (p ≪ 0.05), por lo que no se cumple el supuesto de homocedasticidad. En consecuencia, se utiliza **Welch ANOVA**, robusto a varianzas desiguales y tamaños muestrales distintos.

El test de Welch arroja un estadístico F elevado (F ≈ 30.45) con un valor p extremadamente pequeño (p ≈ 5.8e-17), lo que lleva a **rechazar H₀**. Existen diferencias estadísticamente significativas en el CLV promedio entre los canales de adquisición.

Las pruebas post-hoc con corrección de Bonferroni permiten identificar qué pares de canales presentan diferencias significativas, evidenciando que no todos los canales generan el mismo valor económico.

---

### Evidencia generada
- Tests de normalidad y homocedasticidad.
- Resultado del Welch ANOVA.
- Tabla de comparaciones pareadas con p-values ajustados.
- Visualizaciones:
  - Boxplot de CLV por canal.
  - Medias con error estándar.
  - Matriz de diferencias significativas.
  - Resumen ejecutivo gráfico.
- Dataset original y resultados exportados a Excel.

---

### Archivos generados
- `anova_segmentacion_clientes_dia3.ipynb`
- `resultados_anova_segmentacion_clientes_dia3.xlsx`
- `resultados_anova_segmentacion_clientes_dia3.png`

---

## Día 4 – Modelado Predictivo usando Regresión Lineal (CLV)

### Actividades realizadas
- Simulación y análisis de un dataset de **Customer Lifetime Value (CLV)** con 200 clientes.
- Análisis exploratorio inicial:
  - Estadísticas descriptivas del CLV.
  - Análisis de correlaciones entre CLV y variables explicativas.
- Construcción de modelos de regresión lineal:
  - **Modelo simple**: CLV ~ ingresos.
  - **Modelo múltiple**: CLV ~ ingresos + frecuencia de compras + antigüedad + satisfacción.
- Estimación de parámetros mediante **Mínimos Cuadrados Ordinarios (OLS)**.
- Evaluación de desempeño del modelo:
  - R² y R² ajustado.
  - RMSE (Error Cuadrático Medio).
  - AIC para comparación de modelos.
- Interpretación económica y estadística de los coeficientes.
- Validación exhaustiva de supuestos:
  - Normalidad de residuos (Shapiro-Wilk).
  - Homocedasticidad (Breusch-Pagan).
  - Independencia (Durbin-Watson).
  - Multicolinealidad (VIF).
- Identificación visual de posibles **outliers** mediante gráficos de diagnóstico.
- Generación de predicción de CLV para un cliente nuevo.
- Exportación del dataset original y **todas las tablas de resultados** a un único archivo Excel.
- Generación y guardado de visualizaciones de diagnóstico del modelo.

---

### Pregunta Estadística

¿Es posible explicar y predecir el Valor de Vida del Cliente (CLV) utilizando variables observables del cliente mediante un modelo de regresión lineal?

---

### Hipótesis

- **H₀**: Los coeficientes de las variables explicativas son iguales a cero  
  (las variables no explican el CLV).

- **H₁**: Al menos uno de los coeficientes es distinto de cero  
  (existen variables que explican significativamente el CLV).

---

### Verificación

El coeficiente de **ingresos** (β ≈ 0.020) indica que, manteniendo constantes las demás variables, **un aumento de $1 en ingresos incrementa el CLV esperado en aproximadamente $0.02**, es decir, **$20 adicionales en CLV por cada $1.000 de ingresos**. El efecto es estadísticamente significativo (p < 0.001) y su intervalo de confianza no incluye cero, por lo que se rechaza H₀.

Los supuestos del modelo se cumplen adecuadamente: los residuos presentan **normalidad** (Shapiro p > 0.05), **homocedasticidad** (Breusch-Pagan p > 0.05), **independencia** (Durbin-Watson ≈ 2) y **ausencia de multicolinealidad** (VIF ≈ 1). La presencia de posibles valores atípicos observados gráficamente no invalida el modelo, pero podría afectar la estabilidad de las predicciones extremas, por lo que en aplicaciones reales se recomienda un análisis robusto adicional.

---

### Evidencia generada
- Estadísticas descriptivas del CLV.
- Matriz de correlaciones con CLV.
- Tabla completa de coeficientes del modelo múltiple.
- Métricas comparativas entre modelo simple y múltiple.
- Resultados de validación de supuestos.
- Tabla de VIF para detección de multicolinealidad.
- Predicción de CLV para un cliente nuevo.
- Visualizaciones de diagnóstico:
  - Residuos vs valores ajustados.
  - Q-Q plot de residuos.
  - Histograma de residuos.
  - Residuos vs orden de observación.

---

### Archivos generados
- `modelado_predictivo_usando_regresion_lineal_dia4.ipynb`
- `modelado_predictivo_usando_regresion_lineal_dia4.xlsx`
- `resultados_modelado_clv_regresion_lineal_dia4.png`

---

## Día 5 – Análisis Robusto de Segmentación de Clientes con Técnicas No Paramétricas

### Actividades realizadas
- Generación de un conjunto de datos con **distribuciones no normales**:
  - Gasto total: distribución **exponencial** (asimétrica y con outliers).
  - Frecuencia de visitas: **Poisson** (variable discreta).
  - Satisfacción: **Beta** acotada entre 0 y 10.
- Estimación de intervalos de confianza mediante **bootstrap no paramétrico**.
- Verificación formal de no normalidad mediante **Shapiro-Wilk**.
- Cálculo de **estadísticas descriptivas robustas**:
  - Mediana.
  - Rango intercuartil (IQR).
- Comparación global de segmentos de clientes (**Bronce, Plata y Oro**) usando:
  - **Kruskal-Wallis** como alternativa no paramétrica al ANOVA.
- Identificación de diferencias específicas entre segmentos mediante:
  - Pruebas **Mann-Whitney U** pareadas.
  - Corrección de **Bonferroni** para control del error tipo I.
- Generación y guardado de visualizaciones del análisis.
- Exportación del dataset original y de todas las tablas de resultados a un único archivo Excel.

---

### Pregunta Estadística

¿Existen diferencias estadísticamente significativas en el gasto total entre los distintos segmentos de clientes cuando no se cumplen los supuestos de normalidad?

---

### Hipótesis

- **H₀**: Las distribuciones de gasto total son iguales entre los segmentos.
- **H₁**: Al menos un segmento presenta una distribución (mediana) de gasto distinta.

---

### Verificación

Las pruebas de normalidad rechazan la hipótesis de normalidad para las variables clave (p ≪ 0.05), confirmando la presencia de asimetrías y outliers. Por este motivo, el uso de pruebas paramétricas como ANOVA no es apropiado.

La prueba de **Kruskal-Wallis** arroja un estadístico H significativo (p < 0.001), lo que indica diferencias globales entre los segmentos. Las comparaciones post-hoc con **Mann-Whitney U** y corrección de Bonferroni muestran diferencias significativas entre los segmentos Bronce–Plata y Bronce–Oro, mientras que no se detectan diferencias significativas entre Plata y Oro.

El uso de estadísticas robustas y pruebas basadas en rangos garantiza conclusiones confiables aun cuando los supuestos clásicos del modelo paramétrico están violados. Los intervalos de confianza obtenidos mediante **bootstrap** refuerzan la interpretación al no depender de supuestos de normalidad y proporcionar estimaciones más estables de la incertidumbre.

Este análisis cierra el módulo abordando escenarios realistas donde los supuestos paramétricos no se cumplen, consolidando un enfoque estadístico robusto y aplicable a datos empresariales complejos.

---

### Evidencia generada

- Resultados del test de normalidad Shapiro-Wilk.
- Tabla de estadísticas robustas (mediana e IQR) por segmento.
- Resultado global de Kruskal-Wallis.
- Tabla de comparaciones post-hoc con p-values ajustados.
- Visualizaciones comparativas del gasto por segmento.
- Dataset original y tablas de resultados exportadas a Excel.

---

### Archivos generados

- `analisis_robusto_con_tecnicas_no_parametricas_dia5.ipynb`
- `resultados_no_parametricos_dia5.xlsx`
- `resultados_no_parametricos_dia5.png`

---

## Conclusiones Finales

Este proyecto demuestra una aplicación progresiva y rigurosa de la estadística al análisis de datos, avanzando desde la descripción básica hasta técnicas robustas y modelado predictivo, siempre con validación empírica de supuestos y enfoque reproducible.

A lo largo de los cinco días se consolidan los siguientes aprendizajes clave:

- Los datos reales rara vez cumplen supuestos ideales de normalidad, lo que exige seleccionar modelos y pruebas estadísticas adecuadas al proceso generador de datos.
- El **Teorema del Límite Central** justifica el uso de inferencia paramétrica sobre medias muestrales, pero no sobre datos crudos altamente asimétricos.
- Las **pruebas de hipótesis** permiten cuantificar evidencia estadística, pero deben complementarse con tamaños del efecto, poder estadístico y contexto de negocio.
- El **ANOVA** y sus variantes robustas (Welch) son fundamentales para comparar múltiples grupos cuando existen diferencias estructurales en varianzas y tamaños muestrales.
- La **regresión lineal** es una herramienta poderosa tanto explicativa como predictiva, siempre que se validen exhaustivamente sus supuestos y se interpreten los coeficientes desde una perspectiva económica.
- Las **técnicas no paramétricas y bootstrap** proporcionan inferencias confiables cuando los supuestos clásicos se violan, reforzando la robustez de las conclusiones.

En conjunto, el repositorio refleja buenas prácticas de análisis de datos aplicadas a contextos empresariales reales, integrando teoría estadística, simulación, validación empírica y comunicación clara de resultados, con un enfoque orientado a toma de decisiones basada en evidencia.

Este trabajo demuestra la capacidad de seleccionar, justificar y aplicar métodos estadísticos adecuados según la naturaleza de los datos, una competencia clave en análisis de datos aplicado.

---

## Tecnologías Utilizadas

- Python 3
- NumPy
- Pandas
- SciPy
- Matplotlib
- Jupyter Notebook
- Git & GitHub

---

## Notas

Este repositorio prioriza:
- Reproducibilidad
- Evidencia empírica
- Buenas prácticas de análisis de datos
- Documentación clara y profesional

---

## Estructura del Repositorio

El proyecto se organiza por días de trabajo.  
Cada carpeta diaria contiene el análisis realizado, los datos generados,
las visualizaciones y una verificación conceptual del contenido abordado.

Actualmente, el repositorio contiene el siguiente material:

```text
estadistica-analisis-datos/
├── README.md
├── dia_1/
│   ├── analisis_probabilistico_clientes_dia1.ipynb
│   ├── analisis_probabilistico_clientes_reproducible.xlsx
│   ├── distribuciones_probabilidad_clientes.png
│   ├── comparacion_modelos_normal_vs_reales.png
├── dia_2/
│   ├── prueba_hipotesis_marketing_dia2.ipynb
│   ├── resultados_marketing_dia2.xlsx
│   ├── resultados_prueba_hipotesis_marketing_dia2.png
├── dia_3/
│   ├── anova_segmentacion_clientes_dia3.ipynb
│   ├── resultados_anova_segmentacion_clientes_dia3.xlsx
│   ├── resultados_anova_segmentacion_clientes_dia3.png
├── dia_4/
│   ├── modelado_predictivo_usando_regresion_lineal_dia4.ipynb
│   ├── modelado_predictivo_usando_regresion_lineal_dia4.xlsx
│   ├── resultados_modelado_clv_regresion_lineal_dia4.png
├── dia_5/
│   ├── analisis_robusto_con_tecnicas_no_parametricas_dia5.ipynb
│   ├── resultados_no_parametricos_dia5.xlsx
│   ├── resultados_no_parametricos_dia5.png
├── .gitignore

```