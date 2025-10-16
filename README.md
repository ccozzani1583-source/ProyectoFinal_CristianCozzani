# Proyecto Final - Clasificación de Pagos Atrasados

Este proyecto forma parte del curso de Desarrollo de Machine Learning y presenta un análisis de clasificación de pagos atrasados utilizando el dataset provisto en `recibos al 13-10-2025.xlsm`.

## Contenidos
- `data/` contiene el archivo de datos original.
- `notebooks/` contiene el archivo `ProyectoParteIII+Cozzani.ipynb` con el código del proyecto.

## Descripción del dataset
El dataset está constituido por dos hojas dentro de un excel: `INFORME DE FACTURAS` e `INFORME TRABAJADO`. Para este proyecto utilizamos la hoja `INFORME TRABAJADO`, que contiene 154 registros y las siguientes variables principales: `FECHA PAGO`, `T.DOC`, `RECIBO`, `FACTURA`, `MONEDA`, `TOTAL FACT.`, `N°CLIENTE`, `RAZON SOCIAL`, `EMITIDO`, `VENCIMIENTO`, `ATRASO`, `FORMA PAG`, `LOCALIDAD`, `DEPARTAMENTO`.

## Objetivo
Predecir si un pago tendrá un alto atraso en relación a su mediana mediante un modelo de clasificación. La variable binaria `late` se definió como 1 si `ATRASO` es mayor que la mediana y 0 en caso contrario.

## Metodología
1. **Carga y exploración del dataset**: exploración de la estructura, tipos de datos, valores nulos y distribución de las categorías.
2. **Definición de la variable objetivo**: creación de la marca binaria `late` a partir de la mediana de `ATRASO`.
3. **Preprocesamiento y selección de características**: imputación de valores faltantes, normalización de variables numéricas, codificación one-hot de variables categóricas y selección de las k mejores características con `SelectKBest`.
4. **Entrenamiento y evaluación del modelo**: uso de un `RandomForestClassifier` en un pipeline que incluye el preprocesador y el selector. Mediciones de performance: accuracy, precision, recall, f1-score y matriz de confusión.
5. **Visualizaciones**: gráficos de la distribución de clases, importancias de variables y matriz de confusión.

## Uso
Clonar el repositorio y ejecutar el notebook en un ambiente de Jupyter: 
```bash
git clone <url-del-repositorio>
cd ProyectoFinal/notebooks
jupyter notebook ProyectoParteIII+Cozzani.ipynb
```
Asegúrate de instalar las dependencias: pandas, numpy, matplotlib, seaborn, scikit-learn, nbformat, openpyxl. Puedes instalarlas con: 
```bash
pip install pandas numpy matplotlib seaborn scikit-learn nbformat openpyxl
```

## Conclusiones
Se observó un rendimiento moderado del clasificador básico. Se recomienda investigar técnicas de balanceo de clases y otros algoritmos de clasificación, así como mayor enriquecimiento del dataset y limpieza de datos para mejorar la capacidad predictiva.
