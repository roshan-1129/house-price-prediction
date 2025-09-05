
# 🏠 House Price Prediction using Linear Regression

This project predicts house prices using the **California Housing Dataset** from scikit-learn.  
We use **Linear Regression** as the model and evaluate it using **Cross-Validation (RMSE & R² scores)**.  
Additionally, the project allows you to provide **custom input** (like rooms, income, location, etc.) and get a predicted price.  

## 📂 Project Structure
├── house_price_prediction.py # Main script
├── README.md # Documentation



## 📊 Dataset
We use the **California Housing Dataset**, which contains information about housing districts in California.  
Features include:
- `MedInc` → Median income in the district  
- `HouseAge` → Average age of houses  
- `AveRooms` → Average number of rooms  
- `AveBedrms` → Average number of bedrooms  
- `Population` → Population of the district  
- `AveOccup` → Average occupants per household  
- `Latitude` → Latitude of the district  
- `Longitude` → Longitude of the district  

Target:  
- **Median House Value** (in $100,000 units)


## ⚙️ Installation
Clone the repository and install dependencies:
```bash
git clone https://github.com/your-username/house-price-prediction.git

Dependencies:

numpy

pandas

scikit-learn

🚀 Usage
Run the script:

bash
Copy code
python house_price_prediction.py
🧠 Model Training & Evaluation
We use 5-Fold Cross-Validation to evaluate the model:

python
Copy code
from sklearn.model_selection import cross_val_score
scores = cross_val_score(model, X, y, cv=5, scoring='neg_mean_squared_error')
rmse_scores = np.sqrt(-scores)

Example Output:

Cross-validation RMSE scores: [0.72 0.68 0.75 0.70 0.69]
Average RMSE: 0.708
🔮 Custom Prediction
You can also predict the price for your own input:

python
Copy code
# Example input:
# [MedInc, HouseAge, AveRooms, AveBedrms, Population, AveOccup, Latitude, Longitude]

custom_input = np.array([[8, 20, 6, 1, 500, 3, 34, -118]])
predicted_price = model.predict(custom_input)[0]
print(f"Predicted House Price: ${predicted_price*100000:.2f}")
Example Output:

nginx
Copy code
Predicted House Price: $452,391.72
📈 Results
Evaluation Metric: RMSE & R²

The model captures housing price trends reasonably well, though more advanced models (Random Forest, XGBoost) can improve accuracy.

🔮 Future Improvements
Use feature scaling (StandardScaler)

Try polynomial regression or tree-based models

Deploy using Flask/Streamlit for an interactive web app
