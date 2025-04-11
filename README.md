# Predicción de Salarios de Jugadores de FIFA

Este taller utiliza técnicas de Machine Learning (Random Forest y Gradient Boosting) para predecir los salarios de jugadores de fútbol basado en sus estadísticas en FIFA 19.

## Descripción

En este taller:
- Exploramos y visualizamos datos de +15,000 jugadores de FIFA 19
- Preparamos los datos para el modelado de ML
- Entrenamos y comparamos modelos de Random Forest y Gradient Boosting
- Evaluamos el rendimiento de los modelos para predecir salarios
- Utilizamos SHAP para interpretar las predicciones y entender las variables más importantes

## Resultados Clave

### Rendimiento de los Modelos

| Modelo | R² (Train) | MAE (Train) | R² (Test) | MAE (Test) |
|--------|------------|-------------|-----------|------------|
| Random Forest | 0.909 | 3,552 | 0.805 | 4,667 |
| Gradient Boosting | 0.987 | 1,670 | 0.769 | 4,828 |

### Interpretación

- **Sobreajuste en Gradient Boosting**: A pesar de su excelente rendimiento en entrenamiento (R² = 0.987), muestra una caída significativa en datos de prueba (R² = 0.769), indicando menor capacidad de generalización.

- **Mejor Generalización de Random Forest**: Mantiene mejor R² en prueba (0.805) y MAE ligeramente mejor (4,667 vs 4,828), siendo más estable para predicciones en nuevos datos.

- **Predicciones en casos extremos**:
  - Para jugadores como Messi (salario real: 565,000€), ambos modelos subestiman significativamente
  - Para Cristiano Ronaldo (salario real: 405,000€), las predicciones son más precisas, especialmente con Gradient Boosting
  - Para jugadores de bajo nivel (salario real: 1,000€), ambos modelos predicen con alta precisión

### Variables Más Influyentes (Análisis SHAP)

1. **Overall (Valoración General)**: Factor dominante en las predicciones salariales, con un impacto aproximadamente 8 veces mayor que cualquier otra variable
2. **Age (Edad)**: Segunda variable más importante
3. **International Reputation (Reputación Internacional)**: Tercer factor más relevante
4. **Habilidades técnicas específicas**: Tienen impactos marginales en comparación con el Overall

## Conclusiones

1. **Modelo recomendado**: Random Forest ofrece mejor balance entre precisión y generalización para aplicaciones prácticas.

2. **Factores determinantes**: La valoración general del jugador (Overall) es, por mucho, el principal determinante del salario, seguido a distancia por la edad y la reputación internacional.

3. **Limitaciones**: Los modelos tienen dificultades para predecir salarios muy altos de jugadores buenos, probablemente debido a la escasez de ejemplos de esta categoría en los datos de entrenamiento.

4. **Aplicación práctica**: Los clubes podrían utilizar principalmente la valoración general, con ajustes menores por edad y reputación, para estimar el valor de mercado de un jugador.

## Tecnologías utilizadas
- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- SHAP (SHapley Additive exPlanations)
- Jupyter Notebook

## Contexto
Taller desarrollado como parte del curso de Aprendizaje de Máquina Aplicado en la Especialización en Desarrollo de Software de la Universidad EAFIT.