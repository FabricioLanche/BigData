# Proyecto Grupal Big Data – Análisis de Transacciones de E-commerce

Repositorio con el código fuente, los datos y el informe del proyecto grupal de Big Data: procesamiento distribuido de un dataset de e-commerce con múltiples motores (pandas, Polars, Dask, Modin y Apache Spark) y una sección de Hadoop MapReduce en Google Cloud Dataproc.

## Contenido del repositorio

| Ruta | Descripción |
|---|---|
| `src/*.ipynb` | Notebooks Jupyter con todo el procesamiento de datos |
| `dataset/` | Dataset CSV local (descargado automáticamente desde Kaggle) |
| `figs/` | Imágenes citadas en el informe |

## Notebooks (`src/`)

| Notebook | Procesamiento | Entorno/jerarquía |
|---|---|---|
| `fuente_de_datos.ipynb` | Exploración inicial y diccionario de datos | pandas |
| `pandas.ipynb` | Análisis exploratorio (EDA) en memoria | pandas |
| `polars.ipynb` | 10 consultas de análisis | Polars |
| `dask.ipynb` | 10 consultas, evaluación perezosa y grafos de tareas | Dask |
| `modin.ipynb` | 10 consultas con API de pandas distribuida | Modin |
| `spark.ipynb` | 10 consultas con Spark SQL | PySpark |

Todos los notebooks ejecutan el mismo núcleo de análisis (limpieza, deduplicación, transformaciones, filtrado, agrupaciones y métricas) sobre el dataset de transacciones, de modo que cada motor puede compararse sobre la misma carga de trabajo.

## Instalación y ejecución

Cada notebook instala sus propias dependencias en la primera celda (`dask[dataframe]`, `polars`, `modin[pandas]`, `pyspark`, etc.) mediante `pip install`. Abrir con Jupyter Notebook / JupyterLab:

```bash
jupyter notebook src/
```

### Dataset

Si `dataset/sales_transaction.csv` no existe, se descarga automáticamente desde Kaggle con `kagglehub` (requiere sesión/configuración de Kaggle) hacia `dataset/`. Los notebooks lo leen desde esa ruta local.
