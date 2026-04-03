# Hate Speech Characterization: NLP Feature Extraction

Este proyecto desarrolla un pipeline de análisis de lenguaje natural (NLP) para caracterizar y diferenciar patrones lingüísticos entre discursos de odio y mensajes neutrales. El análisis se centra en la extracción de características morfológicas, entidades nombradas (NER) y métricas léxicas utilizando **spaCy**.

## Objetivo
Identificar rasgos estadísticos y lingüísticos que permitan optimizar futuros modelos de clasificación de texto.

## Pipeline de Trabajo
1. **Data Cleaning & Normalization:** Tratamiento de *mojibake*, normalización Unicode (NFC), eliminación de ruido específico de usuarios y limpieza de caracteres especiales.
2. **Sampling Estratificado:** Gestión de datasets de gran volumen (>570k registros) asegurando la representatividad de las clases.
3. **Extracción de Features:**
   - Análisis morfológico (Género/Número/POS tagging).
   - Detección de Entidades Nombradas (NER) para identificación de targets de odio.
   - Análisis de densidad léxica y stopwords.
4. **Visualización Avanzada:** Dashboard integrado de métricas para comparación de clases.

## Hallazgos Clave
- **Longitud y Estructura:** El discurso de odio tiende a ser significativamente más corto y directo, con una menor complejidad sintáctica.
- **Entidades (NER):** Los textos neutrales presentan una mayor densidad de entidades de localización y organizaciones, mientras que el discurso de odio se concentra en términos de identidad personal.
- **Vocabulario:** Se identificaron patrones de insultos altamente repetitivos frente a la mayor variabilidad léxica del discurso informativo.

## Estructura del Proyecto

* `notebooks/`: Notebook principal con el análisis completo y visualizaciones (`hate_speech_analysis.ipynb`).
* `reports/`: Outputs relevantes:
    * `tables/`: Los listados técnicos (CSV) de frecuencias y palabras exclusivas.
    * `figures/`: El dashboard visual y las gráficas comparativas.
* `DATA_DICTIONARY.md`: Especificaciones del conjunto de datos.
* `requirements.txt`: Dependencias necesarias para la ejecución.

## Stack Técnico
- **Lenguaje:** Python 3.x
- **NLP Engine:** [spaCy](https://spacy.io/) (Modelo `es_core_news_md`)
- **Procesamiento de Datos:** Pandas, NumPy
- **Visualización:** Matplotlib (Gridspec), WordCloud, Tabulate