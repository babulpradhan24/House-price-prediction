# 🏠 Bengaluru House Price Prediction

This project presents a machine learning pipeline built using **Scikit-learn** to predict residential property prices in **Bengaluru, India**. It demonstrates an end-to-end workflow including data preprocessing, model training, evaluation, and inference, structured in a modular and reproducible format.

---

## 📁 Dataset

The model is trained on the `Bengaluru_House_Data.csv` dataset, which includes various attributes related to residential properties in Bengaluru. Key features in the dataset include:

- 📍 `location` – locality of the property  
- 🛏️ `size` – number of bedrooms (e.g., "2 BHK", "4 Bedroom")  
- 📐 `total_sqft` – total area in square feet  
- 🚿 `bath` – number of bathrooms  
- 🌇 `balcony` – number of balconies  
- 💰 `price` – sale price in Lakhs  

---

## 🧭 Project Workflow

### 📦 1. Importing Dependencies

This step imports the necessary Python libraries:
- `pandas`, `numpy` for data manipulation  
- `matplotlib`, `seaborn` for visualization  
- `scikit-learn` for modeling and evaluation  

---

### 📂 2. Data Loading

- Load the dataset from CSV  
- Display initial rows for exploration and understanding

---

### 🧹 3. Data Cleaning

- ❌ Drop irrelevant columns: `area_type`, `availability`, `society`  
- 🧼 Remove rows with missing data  
- 🔢 Convert `size` (e.g. "2 BHK") into numerical `bhk`  
- 📏 Parse `total_sqft` ranges and convert to numeric  
- 🗺️ Group infrequent locations (≤10 listings) as `other`  

---

### ✂️ 4. Train-Test Split

- Data is split using an 80/20 ratio  
- Ensures that the test set provides an unbiased evaluation of the model

---

### 🔧 5. Preprocessing Pipeline

- 🔢 **Numeric features** are scaled using `StandardScaler`  
- 🔤 **Categorical features** (`location`) are one-hot encoded  
- 🧱 All preprocessing steps are combined using `ColumnTransformer` and `Pipeline` for consistency and reproducibility

---

### 🧠 6. Model Training

- A `RandomForestRegressor` is trained using the Scikit-learn pipeline  
- 🌲 Ensemble methods like Random Forest help reduce overfitting and capture nonlinear patterns

---

### 📊 7. Model Evaluation

Evaluate the model using:
- 📉 **RMSE (Root Mean Squared Error)** – to measure average prediction error  
- 📈 **R² Score** – to measure variance explained by the model  

```python
print(f"RMSE: {rmse:.2f}")
print(f"R² Score: {r2:.4f}")
