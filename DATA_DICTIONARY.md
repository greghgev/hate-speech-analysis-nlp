# Data Dictionary: Hatemedia Dataset

Este repositorio utiliza datos recabados en el marco del proyecto **Hatemedia (PID2020-114584GB-I00)**, financiado por MCIN/AEI/10.13039/501100011033, con el apoyo de **Possible Inc**.

## 1\. Información del Proyecto

  * **Contexto:** Análisis de discurso de odio en cinco medios digitales españoles (X, FB y Web) durante el periodo 2021-2022.
  * **Metodología de recolección:** [Informe final de scrapeo (DOI)](https://doi.org/10.6084/m9.figshare.25187591.v2)
  * **Web oficial:** [https://www.hatemedia.es/](https://www.hatemedia.es/)


## 2\. Recursos y Descargas

| Recurso | Descripción | Enlace |
| :--- | :--- | :--- |
| **Datos Brutos (Raw)** | Dataset original sin procesar (+570k registros). | [Descargar aquí](https://drive.google.com/file/d/1b0jnGLV3Uw8Ok9NtijJxqE8WcTWdhxZJ/view?usp=sharing) \* |
| **Datos Procesados** | Dataset tras limpieza de caracteres, normalización y filtrado. | [Ver carpeta](https://drive.google.com/drive/folders/11uQOBM1X73VSfuyJ6KxTVbjc7gJkJKUk?usp=sharing) |


## 3\. Estructura de los Datos

Evolución de los datos durante el proyecto:

### A. Dataset Original (`Raw`)

Contiene los campos base extraídos de las plataformas sociales. Las variables clave son:

  * `CONTENIDO A ANALIZAR`: Texto íntegro del mensaje.
  * `INTENSIDAD`: Etiqueta numérica de hostilidad (0 = Neutro, \>0 = Odio).
  * `TIPO DE MENSAJE`: Origen del registro (COMENTARIO, NOTICIA o TITULAR NOTICIA).

### B. Dataset Procesado (`Cleaned & Sampled`)

Versión optimizada para análisis de NLP:

1.  **Limpieza:** Corrección de *mojibake*, normalización Unicode (NFKC) y eliminación de ruido mediante Regex.
2.  **Submuestreo:** Reducción estratificada del volumen para garantizar representatividad estadística y eficiencia computacional.


## 4\. Artefactos de Análisis

Resultados derivados disponibles en...

... la carpeta `/reports/data/tables/`:

  * `analisis_frecuencias_top100.csv`: Distribución de lemas por clase.
  * `lemas_exclusivos_odio.csv`: Diccionario de términos únicos del discurso hostil.

... la carpeta `/reports/data/figures/`:

  * `dashboard_analisis_odio.csv`: Conclusiones finales más relevantes.
