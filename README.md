# Estadística para Análisis de Datos  

Este repositorio documenta el desarrollo práctico del módulo de Estadística para Análisis de Datos, enfocado en estadística descriptiva, distribuciones probabilísticas, inferencia estadística, pruebas de hipótesis, análisis de poder y validación empírica mediante simulación y análisis reproducible en Python.

El trabajo se desarrolla en **5 días**, siguiendo un enfoque incremental, reproducible y orientado a análisis de datos reales.

---

## Objetivos Generales

- Comprender y aplicar conceptos fundamentales de probabilidad y estadística.
- Modelar correctamente el comportamiento de clientes usando distribuciones adecuadas.
- Validar supuestos estadísticos mediante evidencia empírica.
- Aplicar el Teorema del Límite Central para justificar inferencia paramétrica.
- Desarrollar análisis reproducibles y documentados para portafolio profesional.
- Tomar decisiones basadas en datos mediante pruebas de hipótesis, tamaños del efecto y análisis de poder estadístico.

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

## Días Pendientes

Los siguientes días se desarrollarán progresivamente y se documentarán una vez completados.

- Día 3
- Día 4
- Día 5

---

## Conclusiones Finales *(a completar al finalizar los 5 días)*

En esta sección se integrarán los aprendizajes estadísticos, las decisiones metodológicas y las conclusiones generales obtenidas a lo largo del módulo, destacando el valor del enfoque probabilístico y la inferencia estadística aplicada al análisis de datos empresariales.

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
├── .gitignore

```