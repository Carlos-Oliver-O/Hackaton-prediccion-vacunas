![Impacto de las Variables](images/portada.png)
# Memoria Datathon

Este repositorio contiene los detalles del proyecto desarrollado durante el **Datathon**, centrado en la predicción de antígenos en vacunas mediante modelos de Machine Learning supervisados.

## Índice

- [Memoria Datathon](#memoria-datathon)
  - [Índice](#índice)
  - [Trabajo Desarrollado](#trabajo-desarrollado)
  - [Análisis Exploratorio](#análisis-exploratorio)
    - [Impacto de Temperaturas y Humedades en la Fabricación de Vacunas](#impacto-de-temperaturas-y-humedades-en-la-fabricación-de-vacunas)
  - [Manipulación de Variables y Argumentación](#manipulación-de-variables-y-argumentación)
  - [Justificación de la Selección del Modelo](#justificación-de-la-selección-del-modelo)
    - [Comparativa de Modelos](#comparativa-de-modelos)
  - [Tecnologías y Herramientas Utilizadas](#tecnologías-y-herramientas-utilizadas)
  - [Contacto](#contacto)

---

## Trabajo Desarrollado

Se desarrolló un modelo de Machine Learning supervisado utilizando técnicas de regresión. Los enfoques principales utilizados fueron:

- **Random Forest**
- **XGBRegressor**

Dada la limitada cantidad de muestras disponibles para entrenamiento y el elevado número de características, se eligió la métrica **RMSE** como criterio principal para evaluar el rendimiento del modelo.

Antes de proceder con el modelado, fue necesario investigar el proceso de fabricación de vacunas para entender mejor los datos y su contexto.

---

## Análisis Exploratorio

Durante esta etapa, se identificaron **outliers** en los datos que afectaban significativamente el rendimiento del modelo debido a la naturaleza cuadrática del error RMSE. Se observaron variables críticas, como las **temperaturas** y **humedades**, que impactaban considerablemente la capacidad predictiva.

### Impacto de Temperaturas y Humedades en la Fabricación de Vacunas

![Impacto de Temperaturas y Humedades](impacto_temperaturas_humedades.png)

1. **Estabilidad de los Componentes Activos**:  
   Temperaturas y humedades inadecuadas pueden desnaturalizar los componentes de las vacunas, afectando su eficacia.

2. **Almacenamiento y Transporte**:  
   Es crucial mantener las vacunas entre 2°C y 8°C para preservar su integridad. Niveles inapropiados de humedad pueden comprometer el envase.

3. **Procesos de Fabricación**:  
   Las condiciones ambientales controladas son esenciales para procesos como la liofilización, asegurando la calidad del producto final.

4. **Control de la Contaminación**:  
   Alta humedad puede favorecer el crecimiento de microorganismos no deseados, comprometiendo la calidad del producto.

---

## Manipulación de Variables y Argumentación

Para la manipulación de datos, se utilizó la librería **Pandas**, experimentando con varias estrategias, como:

- Uso de **medianas** (seleccionada por su efectividad para reducir outliers).
- Medias y proporciones (descartadas por mantener valores atípicos).

Estas transformaciones mejoraron la calidad de los datos para el modelado.

![Comparativa de Estrategias](comparativa_estrategias.png)

---

## Justificación de la Selección del Modelo

Tras evaluar distintos modelos, se seleccionó **XGBoost** debido a su rendimiento superior, alcanzando un RMSE de **205**. Este modelo mostró mejor capacidad de generalización frente a los outliers en comparación con Random Forest.

### Comparativa de Modelos

![Comparativa de Modelos](comparativa_modelos.png)

| Modelo         | RMSE  | Observaciones                                   |
|----------------|-------|------------------------------------------------|
| Random Forest  | >205  | Menor penalización de datos atípicos.          |
| XGBoost        | 205   | Mejor rendimiento y generalización del modelo. |

---

## Tecnologías y Herramientas Utilizadas

- **Lenguaje**: Python
- **Librerías**: Pandas, XGBoost, Scikit-learn
- **Métrica de evaluación**: RMSE

---

## Contacto

Si tienes dudas o sugerencias, no dudes en abrir un issue o contactarnos a través de este repositorio.