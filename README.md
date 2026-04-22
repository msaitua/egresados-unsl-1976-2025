# 📊 Histórico de Egresados UNSL — 1976 a 2025

> **Universidad Nacional de San Luis (UNSL)**  
> Fuente: Base institucional de egresados  
> Cobertura: 1976 – 2025

---

## 🎯 Descripción

Este repositorio contiene el análisis completo del **registro histórico de egresados** de la Universidad Nacional de San Luis. El dataset incluye **18.708 egresados** con datos individuales de carrera, facultad, año de ingreso y año de egreso, permitiendo calcular tasas y tiempos de graduación reales.

---

## 📁 Estructura

```
unsl-egresados-xlsx/
├── README.md
├── data/
│   ├── egresados_limpio.csv             ← Dataset completo (18.708 filas)
│   ├── egresados_por_anio.csv           ← Egresados por año de egreso
│   ├── egresados_por_facultad.csv       ← Total por unidad académica
│   ├── egresados_por_carrera.csv        ← Total por carrera
│   └── duracion_por_facultad.csv        ← Duración promedio por facultad
├── visualizaciones/
│   └── dashboard.html                   ← Dashboard interactivo (6 secciones)
└── docs/
    └── metodologia.md
```

---

## 📊 Variables del Dataset

| Variable | Descripción |
|----------|-------------|
| `facultad` | Unidad académica |
| `carrera` | Nombre de la carrera |
| `legajo` | Número de legajo del estudiante |
| `anio_ingreso` | Año de primera inscripción |
| `titulo` | Título obtenido |
| `anio_egreso` | Año de graduación |
| `duracion` | Años entre ingreso y egreso (calculado) |

---

## 📈 Hallazgos Principales

### Totales

| Indicador | Valor |
|-----------|-------|
| Total egresados registrados | 18.708 |
| Período de cobertura | 1976 – 2025 |
| Cohortes de ingreso | 1964 – 2025 |
| Récord anual | 959 egresados (2024) |
| Duración promedio | 7.3 años |
| Duración mediana | 7.0 años |
| Carreras registradas | 140 |
| Títulos únicos | 163 |

---

### 🏫 Egresados por Unidad Académica

| Unidad Académica | Egresados | Duración prom. |
|-----------------|-----------|----------------|
| Fac. Química, Bioquímica y Farmacia | 3.978 | 7.9 años |
| Fac. de Ciencias Humanas | 3.399 | 6.5 años |
| Fac. Cs. Físico-Matemáticas y Naturales | 2.610 | 7.4 años |
| Fac. de Ciencias de la Salud | 2.127 | 7.2 años |
| Fac. de Psicología | 1.858 | **9.6 años** |
| Instituto Politécnico y Artístico Univ. | 1.653 | **4.8 años** |
| Fac. Cs. Económicas, Jurídicas y Sociales | 1.466 | 7.5 años |
| Fac. de Ingeniería y Cs. Agropecuarias | 1.266 | 8.7 años |
| Fac. de Turismo y Urbanismo | 349 | **4.1 años** |

---

### 🎓 Top 10 Carreras

| Carrera | Egresados |
|---------|-----------|
| Licenciatura en Psicología | 1.355 |
| Farmacia | 1.222 |
| Lic. en Ciencias de la Computación | 1.079 |
| Licenciatura en Enfermería | 801 |
| Profesorado de Educación Inicial | 750 |
| Profesorado en Cs. de la Educación | 647 |
| Contador Público Nacional | 603 |
| Bioquímica | 563 |
| Lic. en Comunicación Social | 455 |
| Lic. en Fonoaudiología | 429 |

---

### 📅 Evolución por Década

| Década | Egresados |
|--------|-----------|
| 1976–1989 | ~246 |
| 1990–1999 | 1.831 |
| 2000–2009 | 5.700 |
| 2010–2019 | 6.276 |
| 2020–2025 | 4.655 |

---

### ⏱️ Tiempo de Graduación

- **Mediana**: 7 años
- **Solo el 11%** egresa en ≤5 años (tiempo nominal)
- **El 38%** tarda entre 6 y 8 años
- **El 10%** tarda más de 12 años
- La duración promedio **aumentó** levemente: 6.8 años (1990s) → 7.8 años (2020s)

---

## 🚀 Cómo Usar

```bash
git clone https://github.com/msaitua/unsl-egresados-xlsx.git
cd unsl-egresados-xlsx
open visualizaciones/dashboard.html
```

```python
import pandas as pd
df = pd.read_csv('data/egresados_limpio.csv')
df['duracion'] = df['anio_egreso'] - df['anio_ingreso']

# Egresados por año
df.groupby('anio_egreso').size().plot()

# Duración promedio por facultad
df[df['duracion']>=0].groupby('facultad')['duracion'].mean().sort_values()
```

---

## 🔄 Comparación de Fuentes Disponibles

| Fuente | Tipo | Egresados | Período | Datos disponibles |
|--------|------|-----------|---------|-------------------|
| `Egresados_UNSL.xlsx` | Base institucional | 18.708 | 1976–2025 | ✅ Individuales |
| `54-2024-NOM-cuadros3y11.txt` | SIU estadístico | 152 | 2012–2024 | ✅ Agrupados por cohorte |
| `54-2025-NOM-cuadros3y11.txt` | SIU estadístico | — | 2013–2025 | ❌ Protegidos |

---

*Generado con Python · pandas · Abril 2025*
