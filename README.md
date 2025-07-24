# Regresion_linea_tecnicas_avanzadas
El contenido de este repositorio consta del trabajo realizado durante el curso "Regresión Lineal: Técnicas Avanzadas de Modelado" de la plataforma Alura Latam. Estas actividad forma parte de la especialización de DataScience


# 📘 Proyecto: Análisis y Modelado de Precios Inmobiliarios con Regresión Lineal

Este repositorio documenta el desarrollo, visualización e interpretación de modelos predictivos aplicados a un conjunto de datos del mercado inmobiliario. A través de técnicas de regresión lineal, transformaciones logarítmicas y evaluación estadística, se construyó un proceso riguroso de estimación, validación y reflexión técnica y simbólica.

---

## 📂 Estructura del repositorio

- `Bitacora_de_estudio`: Documento narrativo-técnico que recopila cada etapa del análisis, desde la exploración de los datos hasta la evaluación de residuos. Integra reflexiones estadísticas y filosóficas sobre el modelado.
- `dataset.csv`: Conjunto de datos utilizado, que contiene información sobre inmuebles (área, distancia a servicios, precio, etc.).
- `Regresión_Lineal_II.ipynb`: Notebook en Jupyter que contiene los pasos de entrenamiento del modelo, visualizaciones, transformaciones de variables y evaluación de resultados.

---

## 🧪 Librerías utilizadas

El proyecto se desarrolló principalmente en **Python**, utilizando las siguientes librerías:

| Librería                       | Propósito principal                                         |
|-------------------------------|-------------------------------------------------------------|
| `pandas`                      | Manipulación de datos tabulares                             |
| `numpy`                       | Cálculos numéricos y transformaciones                       |
| `matplotlib.pyplot`           | Gráficos básicos                                            |
| `seaborn`                     | Visualización avanzada (histogramas, pairplot)              |
| `scikit-learn`                | Modelado predictivo, métricas y separación de datos         |
| `sklearn.model_selection`     | Separación de datos en entrenamiento y prueba (`train_test_split`) |
| `statsmodels.api`             | Estimación y resumen estadístico detallado                  |

---

## 📌 Temas abordados

- Limpieza y exploración de datos
- Distribuciones sesgadas y visualización con boxplot e histogramas
- Transformaciones logarítmicas para normalización
- Separación de datos usando `train_test_split` para evitar sobreajuste y evaluar generalización del modelo
- Construcción de modelos de regresión lineal (scikit-learn y statsmodels)
- Evaluación con R² y R² ajustada
- Interpretación de coeficientes, p-values, estadísticos F y t
- Análisis de residuos y validación de supuestos
- Depuración de variables no significativas
- Reflexión sobre el significado técnico y ético del error y la predicción

---

## 🖋️ Autor

**Guz** – Estudiante de Economía, en transición hacia ciencia de datos.  
Integra pensamiento técnico y reflexivo en sus proyectos, documentando el aprendizaje como bitácora vital.

---

## 🧠 Nota ética sobre el entrenamiento del modelo

Separar los datos en conjuntos de entrenamiento y prueba mediante `train_test_split` no solo es una práctica técnica: es una forma de honrar la incertidumbre. Dividir los datos significa aceptar que el modelo debe enfrentarse a lo desconocido, demostrar que puede generalizar sin memorizar. Esta decisión recuerda que, en ciencia —como en la vida—, la predicción nunca es certeza, y el error, lejos de ser una falla, es señal de apertura, aprendizaje y revisión constante.

---
