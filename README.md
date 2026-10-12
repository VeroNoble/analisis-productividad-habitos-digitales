# Análisis de productividad y hábitos digitales

Trabajo Práctico Integrador de la Tecnicatura Superior en Ciencia de Datos e IA.

## Objetivo

Analizar la relación entre hábitos digitales (horas de pantalla, técnicas de gestión del tiempo, sesiones de enfoque) y la productividad percibida, aplicando el flujo completo de un proyecto de datos: limpieza, análisis exploratorio, estadística inferencial y modelado predictivo.

## Datos

Dataset de 60 registros generado de forma sintética dentro del propio notebook (no depende de ningún archivo externo), simulando una encuesta con variables como edad, ocupación, horas de pantalla diaria, uso de técnicas de productividad, principal distractor, sesiones de enfoque diario y productividad percibida (escala 1-10).

## Enfoque

1. **Limpieza y preparación**: verificación de nulos, duplicados y categorías, detección de outliers (regla de 3 desvíos estándar) y creación de variables derivadas (`Indice_Enfoque`, `Segmento_Edad`).
2. **Análisis exploratorio (EDA)**: 6 visualizaciones (distribución de productividad, sesiones de enfoque vs. productividad, densidad de horas de pantalla, impacto de distractores, eficiencia por segmento etario, adopción de técnicas por ocupación).
3. **Estadística inferencial**: medidas de tendencia central y dispersión, probabilidad simple y condicional, prueba de hipótesis con correlación de Pearson entre sesiones de enfoque y productividad.
4. **Modelado**: un modelo de regresión lineal (predice productividad) y uno de clasificación logística (predice uso de técnicas de productividad), con partición 80/20 y evaluación de métricas.

## Resultados

- Correlación fuerte entre sesiones de enfoque y productividad percibida: **r = 0.878** (p < 0.001).
- El modelo de regresión lineal explica el **83.2%** de la variabilidad de la productividad (R² = 0.832, MAE = 0.68). Es un resultado esperable: la productividad se generó a partir de las sesiones de enfoque y las horas de pantalla, y el modelo recupera esa relación.
- El modelo de clasificación logística tuvo bajo desempeño (accuracy = 41.7%): predijo la clase mayoritaria para todos los casos de prueba. La variable objetivo (uso de técnicas de productividad) se generó al azar, sin relación con las demás variables, por lo que no hay señal que aprender; el tamaño de la muestra (60 registros) refuerza esa limitación.

## Herramientas

Python · pandas · numpy · matplotlib · seaborn · scikit-learn · scipy

## Cómo correrlo

```bash
pip install -r requirements.txt
jupyter notebook analisis_productividad_habitos_digitales.ipynb
```

No requiere ningún archivo de datos adicional: el dataset se genera dentro del propio notebook.
