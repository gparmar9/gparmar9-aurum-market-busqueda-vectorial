# Aurum Market — Práctica de Bases de Datos Vectoriales

Este proyecto es el entregable de la práctica de la asignatura **Bases de Datos Vectoriales** del Máster en IA y Cloud Computing.

Consiste en un motor de búsqueda semántica de productos (encuentra productos por significado, no solo por palabras exactas) y un detector de altas duplicadas en un catálogo, usando embeddings y una base de datos vectorial (Chroma).

## Contenido

- **`aurum_market.ipynb`**: notebook con todo el desarrollo (carga de datos, embeddings, base de datos vectorial, búsqueda, evaluación y detección de duplicados). Ya viene ejecutado, con resultados.
- **`datos/`**: catálogo de productos y ficheros de consultas/pruebas proporcionados para la práctica.
- **`resultados/`**: ficheros generados por el notebook (resultados de búsqueda, duplicados detectados y métricas).
- **`cache/`**: embeddings ya calculados, para no tener que recalcularlos cada vez (se puede borrar sin problema).
- **`Enunciado BBDD Alberto.pdf`**: enunciado original de la práctica.

## Resultados

Medidos sobre las consultas de desarrollo (catálogo completo de 15.000 productos):

| Métrica | Valor |
|---|---|
| nDCG@10 | 0.53 |
| Recall@10 | 0.21 |
| MRR@10 | 0.71 |
| Fidelidad del índice ANN | 98.75 % |
| Latencia (p50 / p95) | 16 ms / 18 ms |
| Detección de duplicados (precisión / recall / F1) | 1.0 / 1.0 / 1.0 |

## Cómo ejecutarlo

1. Instalar las librerías necesarias: `pandas`, `numpy`, `scikit-learn`, `sentence-transformers`, `chromadb`.
2. Abrir `aurum_market.ipynb` y ejecutar las celdas en orden.

La primera vez que se calculan los embeddings del catálogo completo tarda unos 15 minutos; las siguientes veces es instantáneo gracias a la caché.
