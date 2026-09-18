# Actividad 03 - Algoritmos de Enjambre en Aprendizaje Automático

## Descripción

Este repositorio contiene el desarrollo de la Actividad 03 sobre la aplicación de algoritmos de inteligencia de enjambre en problemas de aprendizaje automático.

Se desarrollaron ejemplos de:

1. Feature Selection mediante Artificial Bee Colony (ABC).
2. Hyperparameter Tuning mediante Particle Swarm Optimization (PSO).
3. Entrenamiento de una red neuronal sin backpropagation mediante PSO.
4. Clustering mediante PSO como ejercicio alternativo.

---

## Objetivo

Comprender la aplicación de algoritmos de enjambre en problemas de optimización relacionados con aprendizaje automático, analizando la representación de las soluciones, inicialización del enjambre, función de aptitud, comportamiento de los agentes, evolución y condición de finalización.

---

## Ejemplo 1: Feature Selection con ABC

**Archivo:**

`01_ABC_Feature_Selection.ipynb`

Se utiliza Artificial Bee Colony (ABC) para seleccionar un subconjunto de características del dataset Wine.

Cada fuente de alimento se representa mediante un vector binario de 13 posiciones:

- `1`: la característica es seleccionada.
- `0`: la característica es descartada.

La aptitud se calcula utilizando el accuracy de una Regresión Logística con validación cruzada y una pequeña penalización por utilizar muchas características.

El algoritmo implementa tres comportamientos:

- Abejas empleadas.
- Abejas observadoras.
- Abejas exploradoras.

### Resultado

Se seleccionaron 7 de las 13 características del dataset.

- Fitness aproximado: `0.9872`
- Accuracy en test: `1.0000`

---

## Ejemplo 2: Hyperparameter Tuning con PSO

**Archivo:**

`02_PSO_Hyperparameter_Tuning.ipynb`

Se utiliza Particle Swarm Optimization (PSO) para optimizar los hiperparámetros de un modelo SVC con kernel RBF.

Cada partícula representa los valores:

- `C`
- `gamma`

Cada partícula actualiza su posición considerando:

- su velocidad actual;
- su mejor posición personal (`pbest`);
- la mejor posición encontrada por el enjambre (`gbest`).

### Resultado

Valores encontrados aproximadamente:

- `C = 4.112947`
- `gamma = 0.06572440`
- Accuracy de validación: `0.9912`
- Accuracy de test: `0.9737`

---

## Ejemplo 3: Red neuronal sin backpropagation

**Archivo:**

`03_PSO_NN_Sin_Backpropagation.ipynb`

Se construyó manualmente una red neuronal con arquitectura:

`4 → 6 → 5 → 3`

Cada partícula de PSO representa todos los pesos y bias de la red neuronal.

En total se optimizan:

`83 parámetros`

La función de aptitud utiliza la pérdida de entropía cruzada.

La red neuronal realiza únicamente propagación hacia adelante.

No se utiliza:

- Backpropagation.
- Descenso de gradiente.
- SGD.
- Adam.

PSO modifica directamente los pesos y bias de la red.

### Resultado

- Pérdida aproximada: `0.0567`
- Accuracy entrenamiento: `0.9750`
- Accuracy test: `1.0000`

---

## Ejemplo 4: Clustering con PSO

**Archivo:**

`04_PSO_Clustering_Alternativo.ipynb`

Se utiliza PSO para encontrar tres centroides en el dataset Iris.

Cada partícula representa:

`3 centroides × 4 características = 12 valores`

La función objetivo consiste en minimizar la suma de cuadrados intra-cluster (SSE).

Las etiquetas reales del dataset no se utilizan durante la optimización.

### Resultado

- SSE: `145.1457`
- Silhouette: `0.4536`
- ARI: `0.6525`

---

## Tecnologías utilizadas

- Python
- Google Colab
- NumPy
- pandas
- Matplotlib
- scikit-learn

---

## Ejecución

Los notebooks pueden ejecutarse directamente en Google Colab.

Pasos:

1. Descargar o abrir el archivo `.ipynb`.
2. Abrirlo mediante Google Colab.
3. Seleccionar `Entorno de ejecución`.
4. Seleccionar `Ejecutar todas`.
5. Revisar los resultados y gráficos generados.

No se requieren datasets externos porque los ejemplos utilizan datasets incluidos en scikit-learn.

---

## Estructura del repositorio

```text
Actividad-03-Algoritmos-de-Enjambre/
│
├── README.md
├── 01_ABC_Feature_Selection.ipynb
├── 02_PSO_Hyperparameter_Tuning.ipynb
├── 03_PSO_NN_Sin_Backpropagation.ipynb
├── 04_PSO_Clustering_Alternativo.ipynb
└── Informe_Actividad_03_Algoritmos_Enjambre_3_paginas.pdf
