# Hate Speech Characterization: NLP Feature Extraction

Este proyecto desarrolla un pipeline de análisis de lenguaje natural (NLP) estructurado en fases para caracterizar y diferenciar patrones lingüísticos entre discursos de odio y mensajes neutrales. El análisis se centra en la extracción de características morfosintácticas, entidades nombradas (NER) y métricas léxicas avanzadas utilizando **spaCy**.

## Objetivo
Identificar de forma analítica y estadística rasgos lingüísticos estructurales que permitan optimizar futuros modelos de Machine Learning para la clasificación de texto.

## Arquitectura del Pipeline (Modular)
Para optimizar recursos y facilitar la trazabilidad del dato, el desarrollo se ha estructurado en 5 fases secuenciales e independientes:

1. **Ingesta y Preprocesamiento:** Carga de >570k registros, tratamiento de codificación (*mojibake*), normalización Unicode (NFC), y limpieza algorítmica mediante expresiones regulares (`re`).
2. **Análisis Morfosintáctico:** Aplicación del pipeline industrial de spaCy para la extracción de features (POS tagging, lemas, densidad de sustantivos/adjetivos, distribuciones de género y número).
3. **Reconocimiento NER:** Detección de Entidades Nombradas para la identificación de *targets* u objetivos (Personas, Organizaciones, Localizaciones).
4. **Análisis Estadístico:** Cálculo de densidad léxica, proporciones estructurales (palabras/oraciones) e intersección de diccionarios de lemas.
5. **Dashboard Visual:** Renderizado de métricas y comparativas de clases mediante visualización avanzada.

## Hallazgos Clave
- **Estructura Directa:** El discurso de odio analizado es significativamente más corto, directo y de menor complejidad sintáctica. No es argumentativo, sino punzante.
- **Focalización Personal (NER):** Mientras el discurso neutro contextualiza geográficamente (LOC), el discurso hostil se centra obsesivamente en individuos concretos (PER).
- **Sesgo Morfosintáctico:** Existe un repunte asimétrico en el uso del Femenino Singular en contextos de odio, sugiriendo patrones de misoginia dirigida.
- **Polarización y Léxico:** El vocabulario hostil, más allá de los insultos, se instrumentaliza fuertemente a través de la polarización ideológico-política.

## Estructura del Repositorio

* `notebooks/`: Pipeline de ejecución:
    * `01_Ingesta_y_Preprocesamiento.ipynb`
    * `02_Analisis_Morfosintactico.ipynb`
    * `03_Reconocimiento_NER.ipynb`
    * `04_Analisis_Estadistico.ipynb`
    * `05_Dashboard_y_Conclusiones.ipynb`
* `reports/`: Artefactos generados por el análisis:
    * `tables/`: Listados técnicos (CSV) de frecuencias y palabras exclusivas.
    * `figures/`: El dashboard visual y gráficas individuales de los *insights*.
* `DATA_DICTIONARY.md`: Especificaciones completas del conjunto de datos.
* `README.md`
* `requirements.txt`

## Stack Técnico
- **Lenguaje:** Python 3.10
- **NLP Engine:** [spaCy](https://spacy.io/) (Modelo `es_core_news_md`)
- **Ingeniería de Datos:** Pandas, NumPy, Regex (`re`)
- **Visualización:** Matplotlib, Seaborn, WordCloud
