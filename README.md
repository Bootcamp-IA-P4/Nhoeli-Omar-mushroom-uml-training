# Taller de Aprendizaje No Supervisado - Clasificación de Hongos 🍄
<div align="center">
  <img src="https://cdn.pixabay.com/photo/2014/10/01/16/15/fly-agaric-468767_1280.jpg" alt="Banner centrado" width="700" height="350">
</div>

---
## 🚀 Índice

1. [Introducción](#introducción)
2. [Instalación](#instalación)
3. [Carga y Exploración de Datos](#carga-y-exploración-de-datos)
4. [Limpieza y Preprocesamiento](#limpieza-y-preprocesamiento)
5. [Codificación de Variables](#codificación-de-variables)
6. [División del Dataset](#división-del-dataset)
7. [Reducción de Dimensionalidad (PCA)](#reducción-de-dimensionalidad-pca)
8. [Clasificación Supervisada](#clasificación-supervisada)
9. [Clustering No Supervisado (KMeans)](#clustering-no-supervisado-kmeans)
10. [Visualización y Comparación](#visualización-y-comparación)
11. [Conclusiones](#conclusiones)
10. [Folder Structure](#folder-structure)
12. [Tecnologías Usadas](#tecnologías-usadas)
13. [Autores](#autores)

---

## 📌 Introducción

En este proyecto se analiza el conjunto de datos de **hongos** de la web UCI:  
🔗 [https://archive.ics.uci.edu/dataset/73/mushroom](https://archive.ics.uci.edu/dataset/73/mushroom)

Con un total de **8124 registros**, nuestro objetivo es **clasificar** si un hongo es **comestible** o **venenoso** a partir de sus características morfológicas.  
Se aplicaron técnicas de:

✅ Preprocesamiento  
✅ Reducción de dimensionalidad (PCA)  
✅ Clasificación supervisada (Random Forest)  
✅ Clustering no supervisado (KMeans)  

---
## ⚙️ Instalación

### 1️⃣ Clonar el repositorio
```bash
git clone https://github.com/Bootcamp-IA-P4/Nhoeli-Omar-mushroom-uml-training.git
cd Nhoeli-Omar-mushroom-uml-training
```
### 2️⃣ Crear y activar el entorno virtual
```bash
python -m venv .venv
source .venv/Scripts/activate # Windows
source .venv/bin/activate  # Linux/Mac
```
### 3️⃣ Instalar dependencias
```bash
pip install -r requirements.txt
```
---
## 📥 Carga y Exploración de Datos

- Cargamos el dataset original, con **8124 instancias** y **23 columnas categóricas**.
- Renombramos las columnas según la documentación oficial.
- La variable **class** es el objetivo:  
  - 🍽️ Edible (comestible): 4208 (51.8%)  
  - ☠️ Poisonous (venenosa): 3916 (48.2%)  

Balanceados de forma bastante equitativa.

---

## 🧹 Limpieza y Preprocesamiento

- Se buscaron valores nulos y especiales como `?`.
- La columna **stalk-root** contenía valores `?` → tratados como `null` y reemplazados por `unknown`.
- La columna **veil-type** tenía una sola categoría → **Eliminada**.

---

## 🔄 Codificación de Variables

- Todas las columnas son categóricas → **OneHotEncoder** para codificación numérica.
- La variable objetivo (`class`) se separó para el modelado.

---

## ✂️ División del Dataset

División de datos con `train_test_split`:  
- **67%** entrenamiento  
- **33%** prueba

Para obtener una buena estimación del rendimiento del modelo.

---

## 📉 Reducción de Dimensionalidad (PCA)

- Se aplicó **PCA** para reducir dimensiones a 2 componentes principales.
- Visualización con scatterplot → Las clases se separan claramente (aunque no perfectamente).

---

## 🌳 Clasificación Supervisada

- Entrenamiento de un **Random Forest** sobre datos transformados:
  - **Precisión (con PCA)**: 96%
  - **Precisión (sin PCA)**: 100%

Pruebas con diferentes cantidades de features:  
- Con solo 11 features (10%), ya se alcanza el **100% de precisión**.

---

## 🔍 Clustering No Supervisado (KMeans)

- Método del codo → Número óptimo de clusters: **4**.
- Entrenamiento de **KMeans** y visualización con `catplot`.
- Los clusters muestran agrupaciones naturales, con algunas zonas de solapamiento.

---

## 🎨 Visualización y Comparación

- Scatterplot con datos en espacio PCA, coloreado según **KMeans**.
- Se observa una clara estructura de agrupamientos.
- **KMeans**, incluso sin etiquetas, permite encontrar patrones significativos.

---

## 🏁 Conclusiones

✅ El dataset es altamente **separable**.  
✅ **Random Forest** logra precisión casi perfecta.  
✅ **KMeans** también identifica patrones claros sin etiquetas.  
✅ Las características morfológicas contienen información suficiente para distinguir los tipos de hongos.  
📈 Futuras mejoras: ajuste de hiperparámetros y más visualizaciones.

---
## 📁 Folder Structure

```bash
# Nhoeli-Omar-mushroom-uml-training
📂 Nhoeli-Omar-mushroom-uml-training/
├── 📂 .venv/ 
├── 📂 data/
├── 📂 notebook/
│   └── satisfaction-passenger.ipynb
├── 📂 doc/
│   └── Informe_aprendizaje_No_supervisado.pdf
├── 📜 README.md  
├── 📜 .gitignore  
├── 📜 requirements.txt  
```
---
## 💻 Tecnologías Usadas

**Lenguajes y Librerías:**

- Python  
- pandas  
- numpy  
- seaborn  
- matplotlib  
- scikit-learn (PCA, KMeans, RandomForestClassifier)

**Herramientas:**

<img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/visual_studio_code.png" >&nbsp;
<img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/python.png" >&nbsp;
<img width="50" src="https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg">&nbsp;
<img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/git.png">&nbsp;
<img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/jupyter_notebook.png">&nbsp;
<img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/pandas.png">&nbsp;
---

## ✨ Autores

- [Nhoeli Salazar](https://www.linkedin.com/in/nhoeli-salazar/)   
- [Omar Lengua Suárez](https://github.com/Omarlsant/)
---


🎓 ¡Gracias! 🎓

---
<p align="right">(<a href="#-index">⬆️ Back to top</a>)</p>
---
