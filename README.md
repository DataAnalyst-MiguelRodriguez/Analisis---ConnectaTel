ConnectaTel | Análisis de clientes y patrones de uso de telecomunicaciones

📊 Descripción del proyecto

Análisis exploratorio de datos (EDA) enfocado en el comportamiento de clientes de una empresa de telecomunicaciones en Latinoamérica.

Este proyecto analiza información de clientes, planes contratados y registros de uso para identificar patrones de consumo, evaluar la calidad de los datos y segmentar usuarios según sus características demográficas y nivel de actividad.

Mediante Python, Pandas y herramientas de visualización, se desarrolló un flujo de trabajo que abarca la exploración, limpieza, transformación, integración y análisis de datos, con el objetivo de convertir información sin procesar en hallazgos útiles para la toma de decisiones comerciales.

El análisis utiliza registros de uso correspondientes a 2024 y considera la información disponible de clientes registrados entre 2022 y 2024, después de identificar registros con fechas fuera del periodo de estudio.

🎯 Objetivos del proyecto

Evaluar la estructura, integridad y calidad de los datos.

Identificar valores nulos, registros inválidos, fechas inconsistentes y valores atípicos.

Limpiar y transformar los datos para facilitar su análisis.

Integrar información de clientes con sus patrones de uso.

Analizar la distribución de edad, mensajes, llamadas y minutos de llamada.

Segmentar clientes según su edad y nivel de consumo.

Traducir los hallazgos en recomendaciones comerciales para retención y oportunidades de monetización.

🛠️ Tecnologías y herramientas

Python: procesamiento y análisis de datos.

Pandas: limpieza, transformación, agrupación y combinación de datasets.

NumPy: operaciones numéricas y tratamiento de valores inválidos.

Matplotlib: visualización de datos.

Seaborn: histogramas, diagramas de caja y gráficos de distribución.

Jupyter Notebook: desarrollo y documentación del análisis.

📁 Datos analizados

El proyecto utiliza tres conjuntos de datos:

Dataset

Registros

Descripción

plans.csv

2

Información de los planes, precios, servicios incluidos y costos adicionales.

users_latam.csv

4,000

Información de clientes: edad, ciudad, fecha de registro, plan y fecha de baja.

usage.csv

40,000

Registros de actividad relacionados con llamadas y mensajes.

Los archivos de datos deben estar disponibles en el entorno de ejecución para reproducir el análisis.

🔎 Metodología

1. Exploración y comprensión de los datos

Inspección de dimensiones, tipos de datos y estructura de las tablas.

Revisión de estadísticas descriptivas.

Análisis de variables numéricas y categóricas.

Identificación de problemas de calidad antes de realizar transformaciones.

2. Calidad y limpieza de datos

Se identificaron problemas relevantes que podían afectar la interpretación de los resultados:

Valores faltantes: la columna city presenta aproximadamente 11.73% de valores nulos y churn_date 88.35%.

Datos de uso incompletos: duration presenta 55.19% de valores nulos y length 44.74%.

Valores inválidos: se detectó -999 en la variable age, un valor imposible para una edad real.

Fechas fuera del periodo: se encontraron 40 registros con año de registro 2026, aunque el análisis se centra en información hasta 2024.

Valores atípicos: se identificaron observaciones extremas en mensajes, llamadas y minutos de llamada.

Se aplicaron transformaciones para tratar valores inválidos, estandarizar fechas y preparar los datos para el análisis. También se investigó la relación entre los valores faltantes de las variables de uso y el tipo de actividad, con el fin de comprender mejor su patrón.

3. Integración y creación de métricas

Se agregaron los registros de uso por cliente y se combinaron con la información demográfica y comercial.

Se construyeron variables para representar:

Cantidad de mensajes por usuario.

Cantidad de llamadas por usuario.

Minutos acumulados de llamada.

Segmentos de uso.

Grupos de edad.

4. Análisis exploratorio y visualización

Se utilizaron estadísticas descriptivas, histogramas y diagramas de caja para estudiar:

La distribución de edades.

Los patrones de consumo de mensajes y llamadas.

Las diferencias observadas entre los planes Básico y Premium.

La asimetría de las distribuciones de uso.

La presencia y magnitud de valores atípicos.

Los valores extremos se conservaron para el análisis cuando no existía evidencia suficiente para clasificarlos como errores, evitando eliminar automáticamente comportamientos potencialmente reales.

5. Segmentación de clientes

Se desarrollaron dos criterios de segmentación.

Por nivel de uso

Bajo uso: menos de 5 llamadas y menos de 5 mensajes.

Uso medio: no cumple el criterio de bajo uso y registra menos de 10 llamadas y menos de 10 mensajes.

Alto uso: no cumple los criterios anteriores.

Error de datos: categoría utilizada cuando faltan las métricas necesarias para clasificar al usuario.

Por edad

Joven: menor de 30 años.

Adulto: de 30 a 59 años.

Adulto mayor: 60 años o más.

Estos grupos permiten comparar perfiles de clientes y plantear estrategias comerciales diferenciadas.

📈 Principales hallazgos

Distribución por nivel de uso

Sobre los 4,000 clientes analizados, la clasificación generó los siguientes resultados:

Segmento

Clientes

Porcentaje

Uso medio

2,943

73.58%

Bajo uso

778

19.45%

Alto uso

278

6.95%

Error de datos

1

0.03%

Los porcentajes pueden no sumar exactamente 100% por redondeo.

Hallazgo principal: el segmento de uso medio concentra aproximadamente el 73.6% de los clientes. Es un grupo relevante para analizar oportunidades de fidelización y adecuación de los planes a las necesidades de consumo.

Patrones de consumo

El plan Básico representa la mayor parte de la base de clientes.

Las distribuciones de llamadas y minutos muestran una concentración de usuarios en niveles bajos y medios de consumo, con una cola hacia valores altos.

Se identificaron valores extremos en el volumen de mensajes, llamadas y minutos.

Las diferencias observadas entre los planes deben interpretarse considerando el tamaño desigual de sus grupos y la calidad de los datos.

Calidad de los datos

La presencia de valores faltantes y registros anómalos demuestra la importancia de evaluar la calidad de la información antes de construir indicadores o tomar decisiones de negocio.

En particular, los valores faltantes de duration y length están fuertemente asociados al tipo de actividad registrado. Este patrón debe investigarse antes de decidir si corresponde imputar los valores, mantenerlos como nulos o excluir determinadas observaciones.

💡 Recomendaciones de negocio

A partir de los patrones explorados, se plantean las siguientes líneas de acción:

Fidelización del segmento de uso medio: estudiar sus necesidades y evaluar ofertas que se ajusten a sus hábitos de consumo.

Oportunidades de monetización: investigar si los clientes de alto uso necesitan planes con mayores capacidades o beneficios adicionales.

Personalización de ofertas: analizar diferencias por edad y comportamiento antes de diseñar campañas segmentadas.

Revisión de los planes comerciales: contrastar las características y precios de los planes con el consumo real de los clientes.

Mejora de la calidad de los datos: documentar las reglas de limpieza, investigar los valores faltantes y validar los registros anómalos antes de utilizar los resultados en decisiones operativas.

Estas recomendaciones son hipótesis de trabajo derivadas del análisis exploratorio. Su impacto deberá evaluarse con datos adicionales y métricas de negocio.

▶️ Cómo ejecutar el proyecto

Requisitos

Python 3.10 o compatible.

Jupyter Notebook o JupyterLab.

Los archivos de datos utilizados en el análisis.

Instalación de dependencias

pip install pandas numpy matplotlib seaborn jupyter

Ejecución

Clona o descarga este repositorio.

Coloca los archivos CSV en la ubicación esperada por el notebook o actualiza las rutas de lectura.

Abre Analisis - ConnectaTel.ipynb en Jupyter Notebook, JupyterLab o un entorno compatible.

Ejecuta las celdas en orden para reproducir la exploración, limpieza, visualizaciones y segmentación.

Nota: el notebook original utiliza rutas como /datasets/plans.csv. Es necesario adaptarlas a la estructura de carpetas del entorno donde se ejecute.

🧠 Competencias demostradas

Exploratory Data Analysis (EDA).

Data Cleaning y Data Wrangling.

Data Quality Assessment.

Tratamiento de valores nulos y valores inválidos.

Análisis de outliers mediante el método IQR.

Transformación y agregación de datos.

Integración de datasets con Pandas.

Estadística descriptiva.

Visualización de datos.

Customer Segmentation.

Análisis de comportamiento de clientes.

Business Insights y recomendaciones comerciales.

Comunicación de resultados orientados al negocio.

🚀 Posibles mejoras futuras

Automatizar la validación de calidad de datos.

Documentar y comparar el impacto de distintas estrategias de imputación.

Validar las reglas de segmentación con criterios de negocio.

Incorporar indicadores de retención y abandono con definiciones claramente documentadas.

Analizar ingresos, costos y rentabilidad por segmento si se dispone de datos suficientes.

Crear un dashboard interactivo en Power BI o Tableau.

Añadir pruebas de consistencia y un archivo requirements.txt para facilitar la reproducibilidad.

👤 Autor

Miguel Angel Rodriguez Vega
Data Analyst en formación

LinkedIn: https://www.linkedin.com/in/miguel-rodriguez-dataanalyst/

Este proyecto forma parte de mi portafolio de análisis de datos y demuestra mi capacidad para explorar, limpiar, transformar e interpretar datos, identificar patrones de comportamiento y proponer recomendaciones orientadas a necesidades de negocio. Los resultados son exploratorios y deben validarse antes de utilizarlos como base de decisiones operativas.
