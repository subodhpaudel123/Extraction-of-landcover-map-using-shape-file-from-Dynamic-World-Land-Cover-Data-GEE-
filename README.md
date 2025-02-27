
**Land Cover Change Detection Using Google Earth Engine & ArcGIS Pro**  

This repository contains scripts and workflows for analyzing **land cover change** in **Hetauda Sub-Metropolitan City, Makawanpur** using **Google Earth Engine (GEE)** and **ArcGIS Pro**.  

## **Overview**  
The workflow includes:  
✅ **Extracting** Dynamic World land cover data for **2016** and **2024** using Google Earth Engine.  
✅ **Processing** the exported raster layers in **ArcGIS Pro** to create a land cover change map.  
✅ **Visualizing** transitions between land cover types such as **forest to built-up area, crop to shrubland, etc.**  

## **Dataset**  
- **Source:** Google Dynamic World (`GOOGLE/DYNAMICWORLD/V1`)  
- **Resolution:** 10 meters  
- **Classes:**  
  - 🌊 **Water**  
  - 🌳 **Trees**  
  - 🌿 **Grass**  
  - 🌾 **Crop**  
  - 🌱 **Shrub & Scrub**  
  - 🏢 **Built-up area**  
  - 🏜 **Bare land**  
  - 🌊 **Flooded Vegetation**
  - ❄️ **Snow**
     

## **Installation & Dependencies**  
Ensure the following **Python libraries** are installed before running the script:  

```bash
pip install geemap geopandas earthengine-api
```

## **Authentication for Google Earth Engine**  
Before running the script, authenticate with **Google Earth Engine**:  

```python
import ee
ee.Authenticate()
ee.Initialize()
```

## **Workflow**  

### **1️⃣ Exporting Land Cover Data from Google Earth Engine**  
The script extracts **land cover data** for 2016 and 2024:  

```python
years = [2016, 2024]
for year in years:
    export_dynamic_world(year, region)
```
The exported raster files are saved in **Google Drive**.

### **2️⃣ Processing in ArcGIS Pro**  
- Load the **2016** and **2024** raster layers.  
- Use **Raster Calculator**:  

  ```text
  Change_Map = "LandCover_2024 - LandCover_2016"
  ```

- Assign symbology to highlight **land cover transitions**.  

## **Results**  
The final output includes:  
✅ **Land Cover Maps for 2016 and 2024**  
✅ **Land Cover Change Map (2016-2024)**  

<p align="center">
  <img src="your-image-url-here" width="80%" alt="Land Cover Change Map">
</p>
