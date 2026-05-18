# NCAA-Prediction-Project
Proyecto de predicción de resultados NCAA utilizando ingeniería de datos y machine learning.
# Forecast2026NCAA – Predicción del Torneo NCAA 2026

## Integrantes
- 21140339
- 21140338
- 21140357

## Objetivo
Desarrollar un modelo predictivo basado en Machine Learning para estimar resultados del torneo NCAA March Madness 2026 utilizando datos históricos, análisis estadístico y sistemas de ranking Elo.

## Tecnologías utilizadas
- Python
- Pandas
- Scikit-learn
- XGBoost
- LightGBM
- Jupyter Notebook
- GitHub
- Kaggle

# Introducción
El torneo NCAA March Madness es uno de los eventos deportivos universitarios más importantes de Estados Unidos. Debido a la gran cantidad de estadísticas históricas disponibles, este torneo representa una excelente oportunidad para aplicar técnicas de análisis de datos y aprendizaje automático.
En este proyecto se desarrolló un sistema de predicción utilizando datos históricos obtenidos desde Kaggle, aplicando procesos ETL, análisis exploratorio, ingeniería de características y modelos de Machine Learning.

# Fuente de Datos
Los datos fueron obtenidos de la competencia oficial de Kaggle:

https://www.kaggle.com/competitions/march-machine-learning-mania-2026

Archivos utilizados:
- WTeams.csv
- WRegularSeasonCompactResults.csv
- WNCAATourneyCompactResults.csv
- WNCAATourneySeeds.csv
- SampleSubmissionStage1.csv

# Modelo de Datos
Se diseñó un modelo relacional normalizado para organizar la información histórica del torneo NCAA.

## Tablas principales
### Teams
Contiene información de los equipos participantes.
### RegularSeasonResults
Almacena resultados de temporada regular.
### TournamentResults
Resultados oficiales del torneo NCAA.
### Seeds
Posiciones de clasificación de cada equipo.
## Relaciones
- Un equipo puede participar en múltiples temporadas.
- Una temporada contiene múltiples partidos.
- Cada partido tiene un ganador y un perdedor.

# Pipeline ETL
El proyecto implementa un proceso ETL dividido en tres etapas:

## Extracción
Lectura de archivos CSV desde Kaggle utilizando Pandas.

## Transformación
- Limpieza de datos
- Cálculo de Elo Ratings
- Creación de métricas estadísticas
- Ingeniería de características

## Carga
Los datos transformados se almacenan en DataFrames para entrenamiento de modelos predictivos.

# Análisis Exploratorio de Datos
Se analizaron patrones históricos del torneo NCAA para identificar tendencias importantes.

## Distribución de puntajes
La mayoría de los partidos presentan diferencias moderadas entre ganador y perdedor.

## Win Rate por Seed
Los equipos con seeds bajos presentan mayor porcentaje de victorias históricas.

# Sistema Elo
Se implementó un sistema Elo para medir la fuerza relativa de los equipos.

El Elo se actualiza después de cada partido considerando:
- Resultado del encuentro
- Diferencia de puntos
- Ventaja de localía

Este sistema permite representar el rendimiento histórico acumulado de cada equipo.

# Ingeniería de Características
Se construyeron variables predictivas basadas en estadísticas históricas.

## Variables principales
- EloRating_diff
- SeedNum_diff
- WinRate_diff
- AvgMargin_diff

Estas variables representan diferencias entre ambos equipos de un matchup.

# Modelos Utilizados
Se probaron múltiples modelos de Machine Learning:
- Logistic Regression
- XGBoost
- LightGBM

El modelo con mejor desempeño fue XGBoost debido a su menor LogLoss.

# Resultados

El modelo obtuvo resultados competitivos utilizando validación temporal.

## Métrica principal
- LogLoss: 0.4356

## Variables más importantes
- EloRating_diff
- SeedNum_diff
- WinRate_diff

Los resultados muestran que el sistema Elo fue una de las variables más relevantes.

# Conclusiones
El proyecto permitió aplicar conceptos de bases de datos, ETL y Machine Learning en un caso real de predicción deportiva.

Se comprobó que:
- Los sistemas Elo mejoran la predicción.
- La ingeniería de características es fundamental.
- XGBoost ofrece mejor desempeño que modelos lineales simples.

Como trabajo futuro se propone:
- Integrar datos externos como KenPom.
- Optimizar hiperparámetros.
- Implementar modelos Deep Learning.

