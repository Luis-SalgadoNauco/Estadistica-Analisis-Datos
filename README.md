# Estadística para Análisis de Datos  

Este repositorio documenta el desarrollo práctico del módulo de **Estadística para Análisis de Datos**, enfocado en el uso de distribuciones probabilísticas, inferencia estadística y validación empírica mediante simulación y análisis reproducible en Python.

El trabajo se desarrolla en **5 días**, siguiendo un enfoque incremental, reproducible y orientado a análisis de datos reales.

---

## Objetivos Generales

- Comprender y aplicar conceptos fundamentales de probabilidad y estadística.
- Modelar correctamente el comportamiento de clientes usando distribuciones adecuadas.
- Validar supuestos estadísticos mediante evidencia empírica.
- Aplicar el Teorema del Límite Central para justificar inferencia paramétrica.
- Desarrollar análisis reproducibles y documentados para portafolio profesional.

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

## Días Pendientes

Los siguientes días se desarrollarán progresivamente y se documentarán una vez completados.

- Día 2
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
├── .gitignore

```