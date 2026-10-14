# Análisis de Comportamiento de Clientes y Segmentación — ConnectaTel

## Objetivo del Proyecto
Evaluar el comportamiento de uso de los suscriptores de la empresa de telecomunicaciones ConnectaTel durante el periodo de 2024. El análisis abarca la limpieza de datos, el perfilamiento estadístico, la identificación de patrones de consumo intensivo (outliers) y la segmentación de usuarios por edad y nivel de actividad, con el fin de generar recomendaciones comerciales estratégicas y optimizar la oferta de planes.

## Datasets Utilizados
- `plans.csv`: Información sobre los planes tarifarios vigentes (precio mensual, minutos incluidos, mensajes incluidos y costo por exceso).
- `users_latam.csv`: Perfil sociodemográfico de los clientes (ID, edad, ciudad, fecha de registro, tipo de plan y fecha de cancelación/churn).
- `usage.csv`: Registro de eventos de uso de la red (ID de evento, ID de usuario, tipo de tráfico, fecha, duración de llamadas en minutos y extensión de mensajes).

## Etapas del Análisis
1. **Carga y Exploración Inicial:** Revisión del volumen de datos, tipos de variables e identificación preliminar de inconsistencias.
2. **Diagnóstico y Limpieza de Datos:**
   - Tratamiento de datos faltantes tipo MAR (*Missing At Random*) en variables de uso (`duration` y `length`).
   - Reemplazo de valores *sentinels* (`-999` en edad y `?` en ciudad).
   - Normalización de fechas e imputación con `NaT` para registros fuera de rango (año 2026).
3. **Agregación de Métricas por Usuario:** Consolidación del tráfico de llamadas, minutos consumidos y mensajes enviados por suscriptor.
4. **Análisis Exploratorio y Outliers:** Evaluaciones de distribución e inspección visual con BoxPlots. Se validó la permanencia de los valores atípicos superiores por corresponder a patrones reales de alto uso de la red.
5. **Segmentación de Clientes:** Clasificación de usuarios según grupos de edad (*Joven*, *Adulto*, *Adulto Mayor*) y volumen de actividad (*Bajo uso*, *Uso medio*, *Alto uso*).
6. **Insight Ejecutivo:** Elaboración de hallazgos clave y recomendaciones de negocio para tomadores de decisiones.

## Cómo Ejecutar el Notebook

1. Abre `notebooks/telecom-analysis.ipynb`
2. Ejecuta las celdas en orden
3. El notebook carga automáticamente el dataset desde `/data/` o desde un enlace público
