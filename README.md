# Evaluación Parcial N°2 – Near Earth Objects (NEO)

**Curso**: Programación para la Ciencia de Datos (SCY1101)
**Evaluación**: Parcial N°2
**Dataset**: NASA Near Earth Objects (NEO) — `neo.csv`

---

## Descripción

Proyecto sobre el dataset NEO de la NASA, que contiene 90.836 registros de asteroides cercanos a la Tierra. El objetivo es predecir si un asteroide es potencialmente peligroso (`hazardous`) a partir de sus características físicas y orbitales, usando técnicas de aprendizaje supervisado y no supervisado.

---

## Estructura del Proyecto

```text
proyecto-neo/
|-- data/
|   |-- raw/           # Dataset original sin modificaciones
|   |   `-- neo.csv
|   `-- processed/     # Dataset limpio y transformado
|       `-- neo_clean.csv
|
|-- notebooks/
|   `-- neo_ev2.ipynb  # Notebook principal con el flujo completo
|
`-- README.md
```

---

## Flujo del Notebook

1. **Carga e Inspección Inicial** — estructura, tipos, nulos y variable objetivo
2. **Análisis Exploratorio (EDA)** — distribuciones, correlaciones y separación por clase
3. **Preparación de Datos** — limpieza, split estratificado y escalado en pipeline
4. **Modelado Supervisado** — pipelines con Regresión Logística, Random Forest y Gradient Boosting
5. **Evaluación con Validación Cruzada** — F1, ROC-AUC, precision y recall con 5 folds estratificados
6. **Optimización de Hiperparámetros** — GridSearchCV (Regresión Logística) y RandomizedSearchCV (Random Forest)
7. **Aprendizaje No Supervisado** — PCA y KMeans con análisis de silueta
8. **Conclusiones** — comparación final de modelos y hallazgos

---

## Requisitos

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## Reproducibilidad

Todos los procesos que involucran aleatoriedad usan `random_state=42`.

Para reproducir el análisis completo, ejecutar el notebook de arriba a abajo desde un entorno con las dependencias instaladas.

---

## Datos

| Variable               | Descripción                                                     |
| ---------------------- | ---------------------------------------------------------------- |
| `est_diameter_min`   | Diámetro mínimo estimado (km)                                  |
| `relative_velocity`  | Velocidad relativa respecto a la Tierra (km/s)                   |
| `miss_distance`      | Distancia mínima de aproximación a la Tierra (km)              |
| `absolute_magnitude` | Brillo intrínseco del asteroide                                 |
| `hazardous`          | Variable objetivo — si el asteroide es potencialmente peligroso |
