# Machine-Learning-Based-Product-Prediction-System-for-Drop-shipping-
This project focuses on developing a Machine Learning-Based Product Recommendation System for dropshipping platforms. The system uses a Random Forest Classifier to predict whether a product is suitable for dropshipping based on various parameters.

### **Overview**

+ Problem Statement: Dropshippers face challenges in selecting the right products to offer due to the vast product choices available, leading to suboptimal business engagement and limited sales growth.

+ Objective: Develop a machine learning-based system to provide intelligent product recommendations, enhancing dropshippers' decision-making process and business engagement.

+ Solution:
    + Create an interface for dropshippers to input product details.
    + Use a Random Forest Classifier to predict product suitability with an accuracy of 92.47%.
    + Provide accurate recommendations to help dropshippers make informed decisions.

### **Usage**

1. **Install Required Packages:**

`pip install pandas scikit-learn`


2. **Load the Trained Random Forest Model:**
  + Specify the number of estimators (trees) for the Random Forest Classifier.

`from sklearn.ensemble import RandomForestClassifier
n_estimators = 100  
model = RandomForestClassifier(n_estimators=n_estimators, random_state=42)
model.fit(X_train, y_train)`

3. **Read the Test Dataset:**
   + Load the test dataset and map categorical "Order_Priority" values to numeric values.
   + Prepare the features (independent variables) for the test dataset.

`test_data = pd.read_csv("test.csv")  
test_df = pd.DataFrame(test_data)
test_df["Order_Priority"] = test_df["Order_Priority"].map(order_priority_mapping)
X_test = test_df[['Sales', 'Order_Quantity', 'Profit', 'Order_Priority']]`

4. **Make Predictions on the Test Dataset:**
    + Use the trained model to predict product suitability on the test dataset.
    + Convert the predictions to "Yes" or "No" based on the predicted values.
    + Add the "Result" column to the test dataset.

`test_predictions = model.predict(X_test)
test_predictions = ["Yes" if pred == 1 else "No" for pred in test_predictions]
test_df["Result"] = test_predictions
`

5. **Save the Updated Test Dataset:**
    + Save the test dataset with the "Result" column as a new CSV file.

`test_df.to_csv("test_with_results_randomforest.csv")`

I have uplaoded the code by using other alforithms too if you feel that there are some changes needed please contact me 

### Contributors

**1. Akbar khan**

**2. Saman Solapure**

**3. Kruna Nikam**

**4. Aarya Deshpande**
