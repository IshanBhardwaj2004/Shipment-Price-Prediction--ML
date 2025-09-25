# 🚢 Shipment Price Prediction - Machine Learning Project

## 📋 Project Overview

This project focuses on predicting shipment costs for art sculptures using machine learning techniques. The model analyzes various factors such as artwork dimensions, material type, shipping method, and customer information to accurately predict shipping costs.

## 🎯 Problem Statement

Art galleries and sculpture dealers need accurate cost estimates for shipping valuable artworks. Traditional pricing methods often lead to inaccurate estimates, resulting in either overcharging customers or incurring losses. This ML model provides precise shipment cost predictions based on historical data.

## 📊 Dataset Description

The dataset contains **6,500+ shipment records** with the following key features:

### Numerical Features (6):
- **Artist Reputation**: Artist's reputation score (0-1)
- **Height**: Sculpture height in inches
- **Width**: Sculpture width in inches  
- **Weight**: Sculpture weight in pounds
- **Price Of Sculpture**: Original artwork price
- **Base Shipping Price**: Base shipping cost

### Categorical Features (13):
- **Material**: Brass, Clay, Aluminium, Wood
- **International**: Yes/No for international shipping
- **Express Shipment**: Yes/No for express delivery
- **Installation Included**: Yes/No for installation service
- **Transport**: Airways, Roadways, Waterways
- **Fragile**: Yes/No fragility indicator
- **Customer Information**: Working Class, Wealthy
- **Remote Location**: Yes/No for remote delivery
- **Scheduled Date**: Shipment scheduling date
- **Delivery Date**: Expected delivery date
- **Customer Location**: Customer's location

### Target Variable:
- **Cost**: Final shipment cost (negative values indicate refunds/adjustments)

## 🔧 Data Preprocessing

### Missing Value Handling:
- **Artist Reputation**: 11.54% missing → Median imputation
- **Height**: 5.77% missing → Median imputation  
- **Width**: 8.98% missing → Median imputation
- **Weight**: 9.03% missing → Median imputation
- **Material**: 11.75% missing → Most frequent imputation
- **Transport**: 21.42% missing → Most frequent imputation
- **Remote Location**: 11.86% missing → Most frequent imputation

### Feature Engineering:
- **Date Features**: Extracted Month and Year from Scheduled Date
- **Log Transformation**: Applied to target variable for normalization
- **Power Transformation**: Applied to 'Price Of Sculpture' and 'Weight' to handle outliers

### Data Cleaning:
- Removed high-cardinality columns: Customer Id, Artist Name, Customer Location
- Dropped original date columns after feature extraction
- No duplicate records found

## 🤖 Machine Learning Pipeline

### Preprocessing Pipeline:
```python
# Numerical Features Pipeline
- Imputation: Mean strategy
- Scaling: RobustScaler

# Categorical Features Pipeline  
- Imputation: Most frequent strategy
- Encoding: OneHotEncoder

# Outlier Features Pipeline
- Imputation: Median strategy
- Transformation: PowerTransformer
```

### Model Evaluation:
The project tested multiple regression algorithms:

| Model | R² Score | RMSE | MAE |
|-------|----------|------|-----|
| **Random Forest Regressor** | **95.57%** | **0.3472** | **0.2033** |
| Decision Tree | 89.99% | 0.5219 | 0.3275 |
| K-Neighbors Regressor | 84.06% | 0.6588 | 0.4263 |
| Linear Regression | 82.18% | 0.6966 | 0.4841 |

## 🏆 Best Model: Random Forest Regressor

**Performance Metrics:**
- **R² Score**: 95.57% (Test Set)
- **RMSE**: 0.3472
- **MAE**: 0.2033
- **Training R²**: 99.45%

## 📁 Project Structure

```
Shipment-Price-Prediction--ML/
├── shipment_price_prediction_ (2).ipynb  # Main analysis notebook
├── train.csv                              # Training dataset
├── LICENSE                                # Project license
└── README.md                             # This file
```

## 🛠️ Technologies Used

- **Python 3.x**
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **Scikit-learn**: Machine learning algorithms and preprocessing
- **Matplotlib & Seaborn**: Data visualization
- **Jupyter Notebook**: Interactive development environment

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### Running the Project
1. Clone the repository
2. Open `shipment_price_prediction_ (2).ipynb` in Jupyter Notebook
3. Run all cells to reproduce the analysis
4. The model will be trained and evaluated automatically

## 📈 Key Insights

1. **Random Forest** outperformed other algorithms significantly
2. **Artist Reputation** and **Weight** are crucial factors in cost prediction
3. **Express Shipment** and **International** shipping significantly impact costs
4. **Material type** affects shipping complexity and cost
5. **Remote locations** increase shipping costs due to accessibility challenges

## 🔮 Future Enhancements

- [ ] Hyperparameter tuning for Random Forest
- [ ] Feature importance analysis
- [ ] Cross-validation implementation
- [ ] Model deployment as web service
- [ ] Real-time prediction API
- [ ] Additional feature engineering (distance calculations, seasonal factors)

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Ishan** - Machine Learning Engineer

---
