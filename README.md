# Modelado y Simulación de la Demanda Eléctrica — Región Centro

Trabajo final de la materia **Modelos y Simulación** de la Licenciatura en Análisis y Gestión de Datos (UNSL).

Se analiza la demanda eléctrica de la Región Centro durante marzo de 2025, ajustando una distribución teórica a los datos reales y realizando simulaciones estocásticas para distintos escenarios.

---

## Contenido

- `demanda_energetica_modelo.ipynb` — notebook principal con el análisis completo

---

## Metodología

1. **Obtención de datos** — descarga de demanda eléctrica (MW) y temperatura (°C) desde la API pública de CAMMESA, con frecuencia de 15 minutos para todos los días de marzo 2025.

2. **Limpieza y preparación** — conversión de tipos, clasificación de días hábiles/no hábiles, manejo de feriados y eliminación de outliers.

3. **Análisis exploratorio** — visualización de curvas de demanda, boxplots, histogramas y detección de días atípicos.

4. **Ajuste de distribución** — comparación entre distribución Normal y LogNormal (pruebas de Shapiro-Wilk y Kolmogorov-Smirnov) para el horario diurno (08:00–18:00 hs). Se seleccionó la **distribución LogNormal** como mejor ajuste.

5. **Simulaciones estocásticas (Monte Carlo, n=10.000)**:
   - Escenario base: demanda diurna general.
   - Por tipo de día: días hábiles vs. no hábiles.
   - Escenario climático: impacto de un aumento hipotético de +2 °C en la temperatura sobre la demanda, mediante regresión lineal + simulación.

---

## Resultados principales

- La distribución **LogNormal** superó a la Normal en ambas pruebas de bondad de ajuste para la demanda diurna.
- Las simulaciones revelaron diferencias significativas entre días hábiles y no hábiles.
- El escenario de +2 °C proyecta un incremento estimado en la demanda media, con mayor varianza en los percentiles superiores.

---

## Tecnologías

Python · Jupyter Notebook · pandas · NumPy · SciPy · scikit-learn · Matplotlib · requests

---

## Datos

API pública de [CAMMESA](https://api.cammesa.com) — Compañía Administradora del Mercado Mayorista Eléctrico S.A.  
Región: Centro | Período: marzo 2025 | Frecuencia: 15 minutos

---

## Autor

**Ignacio Lopez Parra**  
Licenciatura en Análisis y Gestión de Datos — Universidad Nacional de San Luis
