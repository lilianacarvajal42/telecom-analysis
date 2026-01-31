# Análisis de Comportamiento del Cliente - ConnectaTel 📊

## 🎯 Objetivo del Proyecto
El objetivo principal de este proyecto es evaluar el **comportamiento de los clientes** de la empresa de telecomunicaciones **ConnectaTel** en Latinoamérica, utilizando información registrada **hasta el año 2024**. A través de este análisis, se busca construir un perfil estadístico de los usuarios, detectar comportamientos atípicos (outliers) y diseñar segmentos de uso que permitan sugerir mejoras en los planes actuales y estrategias de retención.

---

## 📂 Datasets Utilizados
El análisis integra tres fuentes de datos principales:
* **`plans.csv`**: Contiene la estructura de costos, minutos y mensajes incluidos, así como tarifas por excedentes de los planes actuales.
* **`users.csv`**: Incluye datos demográficos (edad, ciudad), fecha de registro, plan contratado y estado de cancelación (*churn*).
* **`usage.csv`**: Detalle del uso real de los servicios, consolidando la cantidad y duración de las llamadas y mensajes enviados.

---

## ⚙️ Etapas del Análisis
El proyecto se dividió en las siguientes fases críticas:
1.  **Exploración y Diagnóstico**: Identificación de la calidad de los datos, detectando valores nulos y registros inconsistentes.
2.  **Limpieza Profunda**: Tratamiento de valores "sentinel" (como edades de -999 o ciudades marcadas con "?") y corrección de formatos de fecha para asegurar la consistencia temporal.
3.  **Análisis Estadístico**: Determinación de la distribución de las variables (simetría y sesgos) y cálculo de métricas de tendencia central.
4.  **Detección de Outliers (Método IQR)**: Identificación de usuarios con consumo extremo (Heavy Users) mediante el cálculo de rangos intercuartílicos.
5.  **Segmentación de Usuarios**: Creación de una clasificación propia ('Bajo', 'Medio' y 'Alto uso') mediante funciones personalizadas en Python para agrupar clientes según su actividad.
6.  **Visualización de Hallazgos**: Uso de librerías como `Seaborn` y `Matplotlib` para generar histogramas de capas y diagramas de caja (boxplots).

---

## 🚀 Cómo ejecutar el Notebook

### Opción 1: Google Colab (Recomendado)
1.  Ingresa a [Google Colab](https://colab.research.google.com/).
2.  Sube el archivo `.ipynb` del proyecto.
3.  Carga los archivos CSV (`plans.csv`, `users.csv`, `usage.csv`) en la carpeta de archivos temporal de la sesión (ícono de carpeta a la izquierda).
4.  Ejecuta todas las celdas en orden (`Entorno de ejecución` > `Ejecutar todas`).

### Opción 2: Entorno Local (Jupyter / VS Code)
1.  Clona o descarga el repositorio.
2.  Asegúrate de tener instaladas las dependencias necesarias:
    ```bash
    pip install pandas numpy matplotlib seaborn
    ```
3.  Ejecuta el servidor de Jupyter y abre el notebook asegurándote de que los archivos CSV estén en el mismo directorio.

---

## 🔄 Guía de Reproducción
Para obtener los mismos resultados del **Insight Ejecutivo**:
* **Variables de Consumo**: Al analizar la cantidad de llamadas y minutos, notarás un **sesgo a la derecha**, lo que implica que la mayoría consume poco, pero unos pocos elevan la media.
* **Límites de Outliers**: El límite superior para minutos de llamada se sitúa cerca de los **61.8 minutos**. Cualquier valor superior (hasta el máximo de 155) se considera un usuario extremo que debe ser analizado por separado.
* **Clasificación**: La función de segmentación utiliza umbrales de **5** y **10** interacciones para separar a los usuarios en sus respectivos niveles de valor para el negocio.

---

## 🏁 Conclusión y Cierre

El análisis integral de los datos de **ConnectaTel** ha permitido transformar registros crudos en una visión estratégica del negocio. A través de este proyecto, se han consolidado los siguientes pilares de valor:

* **Integridad de Datos**: Se garantizó la fiabilidad del análisis al corregir inconsistencias críticas en edades, ciudades y fechas, logrando una base sólida para la toma de decisiones.
* **Comprensión del Consumidor**: Se identificó que el **Plan Básico** es el motor del negocio, pero existe una oportunidad latente en los "Súper Usuarios" (outliers), quienes representan el segmento con mayor potencial de migración a servicios Premium.
* **Estrategia Segmentada**: La clasificación de usuarios en niveles de 'Bajo', 'Medio' y 'Alto uso' permite a ConnectaTel abandonar las estrategias masivas por campañas personalizadas que mejoran la experiencia del cliente y la rentabilidad.
* **Visión Basada en Datos**: El proyecto demuestra que la optimización de los planes actuales debe centrarse en la frecuencia de mensajería y la duración de llamadas, factores que definen el techo operativo de la red.

**Este análisis posiciona a ConnectaTel para evolucionar hacia una gestión proactiva, utilizando la ciencia de datos para anticipar necesidades y maximizar el valor de su base de clientes.**

---
