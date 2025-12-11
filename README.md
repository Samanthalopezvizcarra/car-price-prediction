# 🚗 Car Price Prediction

Proyecto para predecir el **valor de mercado de coches de segunda mano** utilizando diferentes modelos de machine learning, optimizando precisión, velocidad de predicción y tiempo de entrenamiento.

---

## 📘 Descripción del proyecto
Rusty Bargain es un servicio de venta de coches de segunda mano que desarrolla una app para que los usuarios conozcan rápidamente el valor de su vehículo.  
Se dispone de datos históricos, especificaciones técnicas, versiones de equipamiento y precios.

El objetivo es crear un modelo que determine el **precio del vehículo (`Price`)** y analizar el balance entre:

- Calidad de la predicción  
- Velocidad de predicción  
- Tiempo de entrenamiento  

---

## 🗂 Dataset
Archivo: `/datasets/car_data.csv`  

**Características principales:**
- `DateCrawled` — fecha de descarga del perfil  
- `VehicleType` — tipo de carrocería  
- `RegistrationYear` — año de matriculación  
- `Gearbox` — tipo de caja de cambios  
- `Power` — potencia (CV)  
- `Model` — modelo del vehículo  
- `Mileage` — kilometraje (km)  
- `RegistrationMonth` — mes de matriculación  
- `FuelType` — tipo de combustible  
- `Brand` — marca del vehículo  
- `NotRepaired` — si el vehículo ha sido reparado  
- `DateCreated` — fecha de creación del perfil  
- `NumberOfPictures` — número de fotos  
- `PostalCode` — código postal del propietario  
- `LastSeen` — última fecha de actividad  

**Objetivo:**  
- `Price` — precio en euros  

---

## 🛠️ Proceso del proyecto

### 1. Preparación de datos
- Exploración y limpieza del dataset  
- Codificación de variables categóricas según el algoritmo  
- División en conjuntos de entrenamiento y prueba  
- Medición de tiempos de ejecución para entrenamiento y predicción  

---

### 2. Entrenamiento y evaluación de modelos
Se entrenaron múltiples modelos con distintos hiperparámetros:

- **Linear Regression** – prueba de cordura (RMSE=3172.36)  
- **Decision Tree** – muy rápido pero alto error (RMSE=2191.97)  
- **Random Forest** – menor error (RMSE=1736.32) pero entrenamiento lento (>1100s)  
- **LightGBM** – buen equilibrio velocidad/precisión (RMSE=1792.44)  
- **XGBoost** – similar a LightGBM (RMSE=1814.79)  
- **LightGBM_2 y CatBoost** – rendimiento aceptable (RMSE≈1847), pero sin destacar frente a los anteriores  

**Métrica utilizada:** RECM / RMSE  

---

### 3. Observaciones
- Regresión lineal confirma que los modelos complejos aportan valor.  
- Decision Tree es rápido pero poco preciso.  
- Random Forest es más preciso, pero muy costoso computacionalmente.  
- LightGBM y XGBoost ofrecen **el mejor balance entre velocidad y precisión**, siendo ideales para una app que requiera predicciones rápidas y confiables.  

---

## 🏆 Conclusión
- **Si priorizamos precisión:** Random Forest  
- **Si priorizamos eficiencia y precisión equilibrada:** LightGBM o XGBoost  

---

## 🧰 Tecnologías utilizadas
- Python  
- pandas · numpy  
- scikit-learn  
- LightGBM · XGBoost · CatBoost  
- matplotlib / seaborn  
