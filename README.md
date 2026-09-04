# 🧠 Análisis exploratorio de biomarcadores asociados a la progresión clínica del Alzheimer

## Descripción

Este proyecto presenta un análisis exploratorio desarrollado en Python a partir de un conjunto de biomarcadores derivados de un modelo neurocomputacional orientado al estudio de la progresión clínica de la enfermedad de Alzheimer.

El análisis busca explorar la relación entre diferentes biomarcadores espectrales y de conectividad cerebral y las etapas clínicas, centrándose principalmente en **análisis de datos, exploración estadística y visualización**, para identificar patrones, tendencias y asociaciones entre los biomarcadores y el índice ordinal de severidad clínica.

> ⚠️ **Nota:** Este proyecto tiene un carácter académico y exploratorio. Los resultados no constituyen un diagnóstico médico ni deben utilizarse para decisiones clínicas.

---

## Contexto del proyecto

Este análisis forma parte de un trabajo académico más amplio basado en un modelo neurocomputacional que integra:

**Conectividad estructural → Dinámica neuronal → Señales M/EEG simuladas → Biomarcadores → Análisis / predicción**

El modelo original utiliza la dinámica de Wilson-Cowan para generar señales M/EEG sintéticas a partir de información de conectividad estructural y posteriormente extraer biomarcadores espectrales y de conectividad.

En este repositorio, el enfoque se centra específicamente en la etapa de **análisis de datos y exploración estadística** de las características obtenidas.

---

## Objetivo

Analizar mediante Python la relación entre biomarcadores derivados de señales M/EEG simuladas y conectividad cerebral, y las diferentes etapas clínicas asociadas a la progresión del Alzheimer.

### Preguntas de análisis

- ¿Cómo se distribuyen los biomarcadores entre las diferentes etapas clínicas?
- ¿Existen cambios en las bandas espectrales según la severidad?
- ¿Cómo se comportan la razón theta/alpha y el índice de slowing?
- ¿Qué relación existe entre los biomarcadores y el índice ordinal de severidad?
- ¿Qué biomarcadores presentan las asociaciones más relevantes?
- ¿Existen diferencias estadísticamente significativas entre las etapas clínicas?

---

## Dataset

El dataset utilizado contiene **16 registros**, correspondientes a sujetos agrupados en cuatro etapas clínicas:

| Etapa | Descripción                       |
| ----- | --------------------------------- |
| CN    | Cognitivamente normal             |
| EMCI  | Deterioro cognitivo leve temprano |
| MCI   | Deterioro cognitivo leve          |
| AD    | Enfermedad de Alzheimer           |

Cada registro contiene biomarcadores espectrales, medidas de conectividad y parámetros derivados del modelo neurocomputacional.

Los datos individuales originales de ADNI no se incluyen en este repositorio. El análisis utiliza únicamente características derivadas y datos anonimizados.

---

## Variables principales

### Biomarcadores espectrales

- `BP_delta`
- `BP_theta`
- `BP_alpha`
- `BP_beta`
- `BP_gamma`

Estos representan la proporción de potencia normalizada en diferentes bandas de frecuencia de las señales M/EEG simuladas.

### Biomarcadores derivados

- `theta_alpha_ratio`: razón entre la potencia theta y alpha.
- `slowing`: suma de las bandas delta y theta.

### Conectividad funcional

- `FC_strength`
- `FC_clustering`
- `FC_efficiency`

### Conectividad estructural

- `SC_strength`
- `SC_density`

### Variables del modelo

- `P_E`
- `G`
- `noise_std`
- `best_error`

### Variable objetivo

- `label`: etapa clínica.
- `severity_index`: índice ordinal utilizado para representar la progresión:

```text
CN   → 0
EMCI → 1
MCI  → 2
AD   → 3
```

---

## Metodología

El análisis se desarrolló siguiendo las siguientes etapas:

```text
Preparación y calidad de datos
        ↓
Análisis exploratorio
        ↓
Análisis estadístico
```

[Métodología a detalle](./analisis_biomarcadores_alzheimer.ipynb)

---

# Skills

- Python
- Pandas: Manipulación y análisis de datos.
- NumPy: Operaciones numéricas.
- Matplotlib: Visualización.
- Seaborn: Visualización estadística.
- SciPy: Análisis estadístico.
- Statsmodels: Corrección por comparaciones múltiples.
- Google Colab: Desarrollo y documentación del análisis.

---

# Hallazgos principales

1. `BP_theta` presenta una asociación positiva con la progresión ordinal de las etapas clínicas.
2. `BP_beta` presenta una asociación negativa con la progresión ordinal.
3. Las tendencias observadas en `theta_alpha_ratio` y `slowing` son compatibles con cambios en la actividad espectral, pero deben interpretarse con cautela.
4. Las medidas de conectividad presentan variabilidad considerable entre sujetos.
5. Los resultados estadísticos dependen fuertemente del reducido tamaño de la muestra.

El análisis exploratorio y estadístico puede utilizarse para identificar biomarcadores candidatos y patrones que posteriormente podrían estudiarse en cohortes más grandes.

---

# Limitaciones

- Tamaño de muestra reducido (n = 16), con cuatro registros por etapa clínica.
- Los biomarcadores M/EEG utilizados provienen de señales simuladas, no de registros M/EEG reales.
- El modelo neurocomputacional utiliza simplificaciones para representar la dinámica cerebral.
- La calibración se basa parcialmente en patrones espectrales reportados en la literatura.
- Los resultados son exploratorios y no permiten establecer relaciones causales.
- No se busca realizar una generalización clínica directa.
- Los resultados no deben interpretarse como un sistema de diagnóstico.

Estas limitaciones son especialmente importantes al interpretar los resultados estadísticos y cualquier modelo predictivo aplicado sobre estos datos.

---

# Conclusiones

El análisis permitió explorar la relación entre diferentes biomarcadores derivados de señales M/EEG simuladas, conectividad cerebral y un índice ordinal de severidad clínica.

Entre los resultados más relevantes se encuentran las asociaciones observadas para BP_theta y BP_beta, que mostraron relaciones monotónicas con el índice de severidad después de aplicar una corrección por comparaciones múltiples.

No obstante, debido al tamaño reducido de la muestra y a la naturaleza simulada de parte de los datos, estos resultados deben considerarse exploratorios y metodológicos.

---

## 👩‍💻 Autora

**Laura Beltrán**\
Ingeniera de Sistemas · Data Analytics

[GitHub](https://github.com/LauvB)
