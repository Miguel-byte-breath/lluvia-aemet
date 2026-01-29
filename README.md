# 🌧️ S.I.G. Agro-Climático: Análisis de Precipitación AEMET

Este repositorio contiene una herramienta técnica diseñada para la **caracterización climática de parcelas agrícolas**. Permite procesar datos históricos de precipitación para determinar el régimen de lluvias, calcular medias mensuales y facilitar la toma de decisiones basada en datos reales de AEMET.



## 🚀 Funcionalidades Clave

* **📍 Localización de Parcela**: Sistema de búsqueda de estaciones meteorológicas mediante coordenadas decimales, identificando automáticamente la estación más cercana y calculando la distancia geodésica.
* **📊 Procesamiento de Series Históricas**: Capacidad para leer y limpiar archivos JSON de AEMET OpenData, eliminando ruidos en los datos (como los registros anuales acumulados "Mes 13").
* **📈 Análisis de Medias Mensuales**: Generación automática de la "Normal Climatológica" de la parcela, calculando cuánto llueve de media cada mes según el histórico cargado.
* **📉 Visualización Dinámica**: Gráficos de barras interactivos con etiquetas de datos para una interpretación rápida de los meses más húmedos y secos.
* **📥 Exportación de Informes**: Generador de archivos Excel (.xlsx) que incluye tanto el historial cronológico como el resumen de medias mensuales.

## 📐 Lógica de Procesamiento

La herramienta aplica criterios de limpieza y ordenación para asegurar la integridad del informe:

1. **Conversión de Coordenadas**: Transformación de formato GMS (Grados, Minutos, Segundos) de AEMET a Grados Decimales para compatibilidad con GPS estándar.
2. **Filtrado de Registros**:
   
   $$Precipitación_{Mensual} = \sum \text{Dato validado (excluyendo totales anuales)}$$

3. **Cálculo de la Media del Periodo**:
   
   $$\mu_{mes} = \frac{\sum P_{i}}{n}$$
   
   *Donde **P<sub>i</sub>** representa la precipitación del mes en el año **i**, y **n** el número total de años analizados.*

## 🛠️ Stack Tecnológico

* **Frontend**: HTML5, CSS3, JavaScript (ES6+).
* **Gráficos**: [Chart.js](https://www.chartjs.org/)
* **Exportación**: [SheetJS (XLSX)](https://sheetjs.com/)

---
*Herramienta desarrollada para el apoyo a la consultoría técnica y planificación agrícola.*
