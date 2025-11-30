# 🗺️ Python – Spatial Analytics: Madrid Tourism (Sample)

This repository contains a **small sample ("píldora")** from a larger spatial analytics project focused on hotel density and tourism infrastructure in central Madrid. It demonstrates geospatial data processing, density analysis and interactive map visualization using Python GIS libraries.

Este repositorio contiene una **pequeña muestra ("píldora")** de un proyecto mayor de analítica espacial centrado en la densidad hotelera e infraestructura turística del centro de Madrid. Demuestra procesamiento de datos geoespaciales, análisis de densidad y visualización interactiva de mapas usando librerías GIS de Python.

> ⚠️ **Note / Nota**: This is a limited extract for portfolio purposes. The original dataset and full analysis cannot be publicly shared due to data restrictions.  
> ⚠️ **Nota**: Este es un extracto limitado con fines de portfolio. El dataset original y el análisis completo no pueden compartirse públicamente por restricciones de datos.

---

## 📄 Files / Archivos

- `notebooks/Pildora_Analitica_espacial_mad_tour.ipynb` – Jupyter notebook with spatial density analysis and choropleth visualization.  
- `images/` – Screenshots of the interactive map and key statistics (if available).  
- `data/` – Placeholder (original shapefiles not included due to privacy/size constraints).

---

## 🎯 Objectives / Objetivos

- Load and merge multiple **spatial datasets** (hotels, tourism offices, neighbourhood boundaries) using **GeoPandas**.  
- Filter geographic areas (central Madrid districts/neighbourhoods).  
- Calculate **hotel density by neighbourhood** (spatial join and aggregation).  
- Generate an **interactive choropleth heatmap** with Folium showing hotel concentration.  
- Add markers for tourism offices with custom popups (name, address, website).  
- Compute **descriptive statistics**: mean, median, min/max hotels per neighbourhood and identify top tourism hotspots.

- Cargar y fusionar múltiples **datasets espaciales** (hoteles, oficinas de turismo, límites de barrios) usando **GeoPandas**.  
- Filtrar áreas geográficas (distritos/barrios del centro de Madrid).  
- Calcular **densidad hotelera por barrio** (join espacial y agregación).  
- Generar un **mapa de calor choropleth interactivo** con Folium mostrando la concentración de hoteles.  
- Añadir marcadores para oficinas de turismo con popups personalizados (nombre, dirección, web).  
- Calcular **estadísticas descriptivas**: media, mediana, min/max de hoteles por barrio e identificar los principales focos turísticos.

---

## 🛠️ Tech stack / Tecnologías utilizadas

- **Python 3.x**  
- **GeoPandas** – Spatial data manipulation, geometric operations and spatial joins.  
- **Folium** – Interactive web-based maps with choropleth layers and custom markers.  
- **Pandas** – Data aggregation and descriptive statistics.  
- **Matplotlib** – Basic plotting (if used for static visualizations).  
- **scikit-learn** – K-Means clustering (referenced but not fully shown in this sample).

---

## 🧹 Main workflow / Flujo principal

### 1. Data loading / Carga de datos

- Connect to Google Drive (Colab environment).  
- Load multiple shapefile layers: 5 hotel files, tourism offices, neighbourhood boundaries.  
- Merge all hotel datasets into a single GeoDataFrame (474 hotels total).

### 2. Spatial filtering / Filtrado espacial

- Filter neighbourhoods in central Madrid districts (43 neighbourhoods with geocodes from `079011` to `079076`).  
- Perform spatial joins to find hotels and tourism offices **within** central neighbourhoods using `gpd.sjoin(..., predicate='within')`.

### 3. Density calculation / Cálculo de densidad

- Group hotels by neighbourhood geocode and count total per neighbourhood.  
- Merge counts back to neighbourhood geodataframe.  
- Fill neighbourhoods with zero hotels (left join to preserve all neighbourhoods).

### 4. Choropleth visualization / Visualización choropleth

- Create a **Folium interactive map** centred on Madrid (40.4168, -3.7038).  
- Add a **choropleth layer** using the YlOrRd colour scheme to represent hotel density.  
- Add **GeoJson tooltips** showing neighbourhood name and hotel count on hover.  
- Add **blue markers** for each tourism office with popups displaying name, address and website link.

### 5. Descriptive statistics / Estadísticas descriptivas

- **Total hotels in central Madrid**: 214  
- **Mean hotels per neighbourhood**: 4.98  
- **Median**: 2  
- **Range**: 0–31 hotels  
- **Top 3 neighbourhoods**:  
  - 013 Cortes: 31 hotels  
  - 016 Sol: 29 hotels  
  - 011 Palacio: 20 hotels

---

## 📊 Key insights / Hallazgos principales

- **Geographic concentration**: The neighbourhoods of Cortes, Sol and Palacio concentrate over 35% of all hotels in central Madrid, reflecting their proximity to major tourist attractions (Puerta del Sol, Plaza Mayor, Royal Palace).  
- **Service coverage**: 6 tourism offices serve 214 hotels across 43 neighbourhoods, indicating potential service gaps in peripheral neighbourhoods.  
- **Spatial patterns**: The choropleth map reveals clear clustering of hotels in the historic centre (districts Centro and Chamberí), with minimal hotel presence in residential neighbourhoods like Legazpi, El Viso and Vallehermoso.

---

## 🎓 Use case / Caso de uso

This type of spatial analysis is useful for:

- **Urban planning**: Identify underserved areas for new tourism infrastructure.  
- **Business intelligence**: Support hotel chains in site selection for new openings.  
- **Policy making**: Monitor tourism concentration and potential overtourism hotspots.  
- **Academic research**: Study the relationship between tourism density and urban services.

Este tipo de análisis espacial es útil para:

- **Planificación urbana**: Identificar zonas desatendidas para nueva infraestructura turística.  
- **Inteligencia de negocio**: Apoyar cadenas hoteleras en la selección de ubicaciones para nuevas aperturas.  
- **Políticas públicas**: Monitorizar concentración turística y posibles focos de sobreturismo.  
- **Investigación académica**: Estudiar la relación entre densidad turística y servicios urbanos.

---

## 👤 Author / Autor

Created by **Jose Miguel Artiles** – Data Scientist & Economist-in-training.  
- GitHub: [JM-specialist-network](https://github.com/JM-specialist-network)  
- Email: joseartiles@g***l.com

- GitHub: [JM-specialist-network](https://github.com/JM-specialist-network)  
- Email: joseartiles@gmail.com
