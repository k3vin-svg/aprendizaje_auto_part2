# Práctica 2: Aprendizaje No Supervisado - Determinación de Tipos de Estrellas 

Este repositorio contiene la solución a la Práctica 2 de la asignatura **Aprendizaje Automático** de la Universidad Carlos III de Madrid (UC3M). 

El objetivo principal de este proyecto es aplicar técnicas de aprendizaje no supervisado para agrupar y clasificar distintos tipos de estrellas basándose en sus características físicas y espectrales, comparando los clústeres obtenidos con las clasificaciones astronómicas reales.

## Estructura del Repositorio

* `practica2.ipynb`: Notebook de Jupyter que contiene todo el código, el análisis exploratorio, el preprocesamiento, el modelado y la discusión de los resultados.
* `stars_data.csv`: Dataset original con la información de 240 estrellas (Temperatura, Luminosidad, Radio, Magnitud Absoluta, Color y Clase Espectral).
* `README.md`: Este archivo, con la descripción general del proyecto.

## Metodología y Algoritmos

En este proyecto se ha implementado el siguiente flujo de trabajo:
1.  **Preprocesamiento:** Codificación ordinal exhaustiva de las variables categóricas (`Color` y `Spectral_Class`) respetando su orden termodinámico y energético real.
2.  **Reducción de Dimensionalidad:** Escalado de datos mediante `StandardScaler` y aplicación de **PCA** (Análisis de Componentes Principales) para proyectar los datos en 2 dimensiones.
3.  **Clustering:** Evaluación y comparación de tres enfoques:
    * **K-Means:** Optimizado utilizando el método del codo y la métrica *Silhouette Score*.
    * **Clustering Jerárquico:** Configurado con el método de enlace *Ward* y analizado visualmente mediante dendrogramas.
    * **DBSCAN:** Búsqueda automatizada de hiperparámetros (`eps` y `min_samples`) optimizada mediante la métrica de validación *DBCV*.

## Requisitos e Instalación

Para ejecutar el notebook correctamente, es necesario tener instaladas las siguientes librerías de Python. La mayoría vienen incluidas en distribuciones como Anaconda o Google Colab:

* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`
* `scipy`
> [!IMPORTANT]
> Este proyecto utiliza la métrica **DBCV** para la evaluación del algoritmo DBSCAN. Esta librería no suele venir preinstalada. Para poder ejecutar esa sección del código, debes instalarla ejecutando:

```bash
pip install dbcv
