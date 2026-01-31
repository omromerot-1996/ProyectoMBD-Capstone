 Homicidios Ecuador (2021–2025) — Análisis y Pronóstico Semanal (ARIMA | Holt-Winters | LSTM)

Este repositorio contiene un pipeline en **Python (Google Colab/Jupyter)** para el análisis de la serie temporal de **homicidios intencionales en Ecuador**, agregada a frecuencia **semanal (W-SUN)**. Incluye:

- **Pruebas de estacionariedad** (ADF y KPSS) en niveles y primera diferencia  
- **Visualización exploratoria** (tendencia, boxplots, estacionalidad, correlación)  
- **Modelado y evaluación** con **ARIMA**, **Holt-Winters (ETS)** y **LSTM**  
- Evaluación con:
  - **Split fijo**: train 26 semanas, test 26 semanas
  - **Rolling forecast (walk-forward)** con ventana fija de 26 semanas  
- **Proyección semanal hasta 2030** usando el mejor modelo por nivel (según RMSE)

---

## 🗃️ Contenido

- `Muestra.xlsx`: archivo de referencia para alinear el esquema (columnas) del dataset.
- `mdi_homicidios_intencionales_pm_2014_2024.xlsx`: dataset histórico (2014–2024).
- `mdi_homicidiosintencionalse_pm_2025_enero_octubre.xlsx`: dataset 2025 (enero–octubre).
- Notebook(s) de análisis (Colab/Jupyter) con:
  - Pruebas de estacionariedad
  - Visualizaciones
  - Modelado (ARIMA / Holt-Winters / LSTM)
  - Rolling forecast
  - Exportación de pronóstico a CSV (`pronostico_semanal_2026_2030.csv`)

> **Nota:** Los nombres reales de tus notebooks/archivos pueden variar; ajusta esta sección a tu estructura del repositorio.

---

## 🚀 Requerimientos

Se recomienda crear un entorno virtual:

```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
Instala dependencias:

pip install -r requirements.txt
Si no tienes requirements.txt, instala manualmente:

pip install numpy pandas matplotlib openpyxl statsmodels scikit-learn tensorflow pmdarima tbats
▶️ Cómo ejecutar el proyecto
1) Ejecutar en Google Colab (recomendado)
Abre el notebook en Colab.

Sube los archivos Excel cuando el notebook lo solicite:

Muestra.xlsx

mdi_homicidios_intencionales_pm_2014_2024.xlsx

mdi_homicidiosintencionalse_pm_2025_enero_octubre.xlsx

Ejecuta las celdas en orden.

El pipeline generará:

Tablas de métricas (RMSE, MAE, MAPE)

Gráficos (real vs predicho, residuales, etc.)

Archivo pronostico_semanal_2026_2030.csv

2) Ejecutar en local con Jupyter
Abre el notebook:

jupyter notebook
Ejecuta el notebook paso a paso asegurando que los Excel estén en el mismo directorio (o ajustando rutas).

📊 Resultado esperado
Series semanales (W-SUN) para:

Total país

Provincia: Guayas

Cantón: Guayaquil

Evaluación comparativa de modelos (ARIMA, Holt-Winters, LSTM) con métricas:

RMSE

MAE

MAPE

Rolling forecast con ventana de entrenamiento fija de 26 semanas

Pronóstico semanal hasta 2030 (mejor modelo por nivel)

Exportación de resultados:

pronostico_semanal_2026_2030.csv
📌 Notas adicionales
El análisis trabaja con frecuencia semanal W-SUN (semanas cerradas en domingo).

El periodo principal de modelado está filtrado a 2021–2025.

En cantón, se contempla que el dataset pueda contener GUAYAQUIL o GUAYQUIL.

Si el mejor modelo seleccionado fuera ARIMA para el bloque de proyección a 2030, el notebook lanza una excepción (ese bloque no incluye ARIMA por defecto).
