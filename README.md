# Homicidios Ecuador (2021–2025) — Análisis y Pronóstico Semanal (ARIMA | Holt-Winters | LSTM)

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
- Notebook de análisis (Colab/Jupyter) con:
  - pruebas de estacionariedad
  - visualizaciones
  - modelado (ARIMA / Holt-Winters / LSTM)
  - rolling forecast
  - exportación de pronóstico a CSV (`pronostico_semanal_2026_2030.csv`)

> **Nota:** los nombres reales de tus notebooks/archivos pueden variar; ajusta esta sección a tu estructura.

---

## 🚀 Requerimientos

Se recomienda crear un entorno virtual:

```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
