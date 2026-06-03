# 🧪 Experimento A/B — Landing Page

**Proyecto de Análisis de datos | TripleTen**

---

## 📌 Descripción del Proyecto

Este proyecto analiza un experimento A/B realizado sobre una página de inicio (*landing page*) con dos versiones (**A** y **B**), con el objetivo de apoyar una **decisión de negocio basada en datos**. Se evalúan métricas clave como tasa de conversión, gasto promedio, fuente de tráfico y tipo de usuario para determinar qué versión ofrece el mejor rendimiento comercial.

---

## 🗂️ Estructura del Proyecto

```
landing-ab-experiment/
│
├── data/
│   └── landing_experiment.csv       # Dataset con 40,000 registros
│
├── notebooks/
│   └── S9_Landing_Experiment.ipynb  # Análisis completo paso a paso
│
└── README.md
```

---

## 📊 Dataset

El archivo `landing_experiment.csv` contiene información de usuarios expuestos a las dos versiones de la página dentro del experimento A/B.

| Variable | Descripción |
|---|---|
| `user_id` | Identificador único del usuario |
| `date` | Fecha de exposición a la página |
| `landing` | Versión de la página (`A` o `B`) |
| `region` | Región geográfica del usuario |
| `dispositivo` | Tipo de dispositivo utilizado |
| `traffic_source` | Canal de adquisición (`Organic`, `Ads`, `Email`, `Referral`) |
| `user_type` | Tipo de usuario (`new`, `returning`) |
| `converted` | Si el usuario convirtió (`1`) o no (`0`) |
| `gasto` | Monto gastado (0 si no convirtió) |

---

## 🔬 Metodología

El análisis sigue una lógica progresiva de 7 pasos:

1. 🔍 **Carga y validación de datos** — Revisión de calidad, tipos de datos y valores atípicos
2. 💰 **Comparación del gasto promedio** — Prueba t de Student para muestras independientes
3. 🎯 **Comparación de tasa de conversión** — Prueba Z de proporciones
4. 🌐 **Fuente de tráfico vs. conversión** — Prueba Chi-cuadrado de independencia
5. 👤 **Tipo de usuario vs. conversión** — Prueba Chi-cuadrado de independencia
6. 📈 **Visualización de resultados** — Gráficos de barras apiladas y proporciones
7. 🌟 **Insight ejecutivo** — Conclusiones y recomendaciones accionables para stakeholders

Nivel de significancia utilizado: **α = 0.05**

---

## 📈 Resultados Principales

### Comparación de versiones (A vs B)

| Métrica | Página A | Página B | Conclusión |
|---|---|---|---|
| Usuarios totales | 19,982 | 20,018 | Grupos balanceados ✅ |
| Conversiones | 2,512 | 3,194 | B convierte más |
| Tasa de conversión | ~12.57% | ~15.96% | **B superior** (+3.39 pp) |
| Gasto promedio (todos) | — | — | Diferencia significativa ✅ |

> La prueba estadística rechazó H₀ en ambos casos (p < 0.05), confirmando que las diferencias **no son atribuibles al azar**.

### Canales de tráfico

| Canal | Conversiones | Tasa de conversión |
|---|---|---|
| Email | 918 | **14.99%** ⭐ |
| Ads | 1,759 | 14.74% |
| Referral | 549 | 13.88% |
| Organic | 2,480 | 13.79% |

### Tipo de usuario

| Tipo | Conversiones | Tasa de conversión |
|---|---|---|
| Nuevo | 3,738 | 14.36% |
| Recurrente | 1,968 | 14.09% |

> No se encontró diferencia estadísticamente significativa entre tipos de usuario (p = 0.47).

---

## 💡 Recomendaciones de Negocio

1. **Implementar la Página B** como versión definitiva: genera un 27% más de conversiones que la Página A con evidencia estadística sólida.
2. **Invertir en canales de Email y Ads**: presentan las tasas de conversión más altas. Escalar estas campañas puede maximizar el retorno.
3. **No segmentar estrategias por tipo de usuario** (nuevo vs. recurrente) ya que la diferencia en conversión es mínima y estadísticamente no significativa.
4. **Optimizar el canal Organic**: aunque genera el mayor volumen de tráfico, tiene la tasa de conversión más baja. Mejorar el contenido o la experiencia de aterrizaje para este segmento podría tener alto impacto.

---

## 🛠️ Tecnologías Utilizadas

- Python 3
- pandas · numpy
- scipy.stats · statsmodels
- matplotlib · seaborn
- Jupyter Notebook

---

## 👩‍💻 Contexto Académico

Este proyecto fue desarrollado como parte del programa de **Ciencia de Datos** de [TripleTen](https://tripleten.com/), Sprint 9 — Análisis Estadístico y Experimentos A/B.

---

*TripleTen · Proyecto educativo · Análisis de Experimento A/B*
