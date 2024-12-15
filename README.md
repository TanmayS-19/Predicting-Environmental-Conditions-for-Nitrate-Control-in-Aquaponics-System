# Predicting Optimal Environmental Conditions for Nitrate Control in Aquaponics Systems


![image](https://github.com/user-attachments/assets/7ac78079-7324-4216-8425-53decbbd5810)


## Introduction

Aquaponics is an innovative and sustainable farming system that combines aquaculture (raising aquatic animals such as fish) with hydroponics (cultivating plants in water without soil). This closed-loop system relies on the symbiotic relationship between fish and plants, where fish waste, rich in ammonia, serves as a natural fertilizer for plants. Beneficial bacteria in the system convert ammonia into nitrates, which are vital nutrients for plant growth. In return, the plants filter and purify the water, creating a healthy environment for the fish.

This integrated approach offers numerous advantages over conventional farming. Aquaponics uses up to 90% less water, requires significantly less land, and eliminates the need for synthetic fertilizers or pesticides. It is particularly well-suited for urban and space-constrained environments, providing a sustainable method to produce fresh fish and organic crops year-round. The system’s efficiency makes it an ideal solution for addressing modern food production challenges, including resource scarcity, urbanization, and the need for eco-friendly agricultural practices.

A critical factor in aquaponics is maintaining the balance of the system, particularly with nitrate levels. Nitrate (NO3-), a byproduct of the nitrification process, is essential for healthy plant growth but must remain within specific ranges to avoid toxicity for fish. Imbalanced nitrate levels can hinder plant growth or harm fish, jeopardizing the entire system. Key environmental parameters—such as temperature, turbidity, dissolved oxygen, pH, and ammonia—directly influence nitrate levels and the overall health of the system.

To optimize aquaponics systems, predictive models utilizing historical data and machine learning can play a crucial role. These models analyze the complex interactions between fish populations, environmental variables, and nitrate concentrations, offering precise recommendations for maintaining ideal conditions. This data-driven approach enhances the efficiency and sustainability of aquaponics systems, empowering practitioners to achieve higher yields while minimizing resource use. By promoting eco-friendly farming and self-sufficient food production, aquaponics represents a forward-thinking solution to contemporary agricultural challenges.



## Proposed Model and Its Utility for Farmers

To address the challenges of maintaining optimal nitrate levels in aquaponics systems, we propose a predictive machine learning model. This model leverages historical data to determine the ideal environmental conditions for achieving a farmer's desired nitrate levels. By analyzing the relationships between fish population, species, size, and environmental parameters, the model provides actionable recommendations that empower practitioners to maximize system efficiency and yield.

## Data Collection

The data used for this model was sourced from a labeled dataset specifically designed for monitoring water quality in aquaponics systems. Real-time data was gathered using IoT-enabled sensors deployed in aquaponics fishponds. These sensors continuously recorded key environmental parameters, including pH levels, temperature, dissolved oxygen, and ammonia concentrations, across various fish species. 
To enhance the dataset and aid predictions, we created a derived variable called **Fish Size**, classifying fish into **S (Small)**, **M (Medium)**, and **L (Large)** based on their lengths and weights. 
The collected data underwent meticulous preprocessing to address missing values and inconsistencies, ensuring a clean and unified dataset suitable for building accurate and reliable predictive models.


### Data Inputs and Outputs
Our model is built upon a carefully curated dataset, where the input features (`X`) include:
- **Population**: Number of fish in the system.
- **Category**: Fish species (e.g., A, B, C).
- **Size**: Fish size categories (Small, Medium, Large), derived from:
  - **Fish Length (cm)**
  - **Fish Weight (g)**
- **Nitrate Levels (mg/L)**: Desired nitrate concentration required for optimal plant growth.

The output variables (`y`) predicted by the model are the optimal environmental conditions:
- **Temperature (°C)**
- **Turbidity (NTU)**
- **Dissolved Oxygen (mg/L)**
- **pH**
- **Ammonia (mg/L)**

### How the Model Works
1. **Data Analysis**: The model starts by identifying patterns in historical data, examining how various fish populations and species interact with their environmental needs to influence nitrate levels.
2. **Predictive Power**: Using advanced machine learning algorithms, such as Random Forest Regression or Gradient Boosting, the model predicts the precise environmental variables needed to achieve the desired nitrate levels.
3. **Farmer-Friendly Recommendations**: Based on the input data (e.g., fish type, population, and nitrate requirement), the model generates easy-to-interpret outputs that help farmers adjust their systems effectively.

### Practical Utility for Farmers
By integrating this predictive model into an aquaponics system, practitioners gain the ability to:
- **Optimize Growth Conditions**: Receive precise recommendations for factors like temperature, pH, dissolved oxygen, and ammonia levels, ensuring both plant health and fish safety.
- **Improve System Efficiency**: Reduce trial-and-error in managing environmental conditions, saving time and resources.
- **Enhance Productivity**: Maximize crop yields and fish growth by maintaining the delicate balance required in aquaponics systems.
- **Support Sustainability**: Promote eco-friendly farming practices that conserve water, reduce waste, and eliminate synthetic fertilizers.
- **Adapt to Changing Needs**: Scale the system or modify environmental conditions to accommodate different fish species or plant types.

This data-driven approach transforms aquaponics management into a science-backed, precision-oriented process, enabling practitioners to produce fresh, organic food sustainably while contributing to global food security and resilience. By simplifying complex decision-making processes, the model ensures that aquaponics systems are accessible and efficient for farmers of all scales.

## Exploratory Data Analysis (EDA)

Understanding the data is crucial to building an effective predictive model. Below, we outline two key insights derived from the dataset:

### 1. Distribution of Fish Categories

![image](https://github.com/user-attachments/assets/de4d3f17-1b27-4a75-8577-5cb3cc6ea184)

The dataset comprises three fish categories: **A**, **B**, and **C**. The distribution of fishes across these categories is as follows:
- **Category A**: 39.8%
- **Category B**: 31.0%
- **Category C**: 29.2%

This distribution indicates that **Category A** dominates the dataset, followed by **Category B** and **Category C**. The representation of each category ensures a balanced analysis, with significant insights derived for each fish type.

### 2. Nitrate Levels by Fish Category and Size

![image](https://github.com/user-attachments/assets/49ce206c-6802-49a0-8af8-d62b2dd95d7b)

To explore the relationship between fish categories, sizes, and nitrate levels, the data was visualized using bar plots. The findings reveal:
- **Smaller fish (Size S)** consistently exhibit **lower nitrate levels** across all categories.
- **Medium-sized (M) and large (L) fish** show a gradual **increase in nitrate levels**, with large fish contributing the highest levels in each category.

This pattern highlights the correlation between fish size and nitrate levels, suggesting that larger fish populations may require careful monitoring to maintain the desired nitrate balance. The insight helps practitioners better manage environmental parameters based on the composition of their aquaponics systems.


# Results

## Introduction
For our use case, we decided to go with **Decision Tree (DT)**, **Random Forest (RF)**, and **Extreme Gradient Boosting (XGB)** due to the multi-output regression scenario. Each model was selected for its unique strengths and capabilities in predicting environmental conditions:  

- **Decision Tree (DT):** Chosen for its simplicity and interpretability, providing a baseline for comparison.  
- **Random Forest (RF):** Utilized for its ensemble learning approach, which effectively handles non-linear relationships.  
- **XGBoost (XGB):** Selected for its scalability, robust performance, and ability to capture complex interactions through boosting techniques.

To optimize performance, we implemented **automated hyperparameter tuning** using iterative looping techniques. This approach allowed us to identify the most optimized parameters for each model and maximize their predictive accuracy.

---

## Model Evaluation Process
We evaluated each model based on performance metrics such as **Mean Squared Error (MSE)**, **Root Mean Squared Error (RMSE)**, and **R² Score**. Additionally, we visualized the alignment of predicted vs. actual values for each model using scatter plots.

### Visualization of Results
To assess the model predictions visually, we created scatter plots comparing actual vs. predicted values for each feature. Each plot also includes a regression line to highlight the model's performance trends. These visualizations allowed us to evaluate the degree of alignment between predicted and actual outputs, offering clear insights into each model's accuracy.

---

## Decision Tree (DT) Results

### Model Performance

![image](https://github.com/user-attachments/assets/f41b0713-34e3-4784-8f35-42dfdf0333bb)

### Implementation of the model
For a sample input:

Sample Data from our Dataset:
- Temperature (C): 26.3125
- Turbidity (NTU): 100
- Dissolved Oxygen (mg/L): 3.2
- pH: 4.36175
- Ammonia (mg/L): 1.00036
- Nitrate (mg/L): 1100
- Population: 50
- Fish Length (cm): 33.24
- Fish Weight (g): 320.45
- Category: A
- Size: L

![image](https://github.com/user-attachments/assets/f4966290-8a3c-4407-937e-2ee86b9904be)


The recommended environmental conditions are:  

![image](https://github.com/user-attachments/assets/5b7a2800-344a-47cf-9dfc-4f359782178c)


### Observations from Visualizations

![image](https://github.com/user-attachments/assets/2f57d143-77ef-4202-b73b-288534bd1d25)


- The scatter plots for **DT** reveal moderate alignment between predicted and actual values, with notable deviations for certain features.  
- The regression lines indicate some predictive capability, but the variance around these lines reflects the model’s limitations in capturing intricate relationships.

**Conclusion for DT:** While DT provides a simple and interpretable solution, it struggles with the complexity of the multi-output regression task.

---

## Random Forest (RF) Results

### Model Performance

![image](https://github.com/user-attachments/assets/e2c3ff17-f67c-43e4-92fd-0833588ecf59)

### Implementation of the model
For a sample input: 

Sample Data from our Dataset:
- Temperature (C): 24.87525695
- Turbidity (NTU): 100
- Dissolved Oxygen (mg/L): 25.42495793
- pH: 8.521656782
- Ammonia (mg/L): 28.0886918
- Nitrate (mg/L): 909
- Population: 75
- Fish Length (cm): 19.46
- Fish Weight (g): 73.1
- Category: B
- Size: M

![image](https://github.com/user-attachments/assets/5efecf9a-feba-4945-81e4-b5344c828cbb)

The recommended environmental conditions are:  

![image](https://github.com/user-attachments/assets/81aa485d-852d-4e9a-a5c8-fcaaceaf5409)


### Observations from Visualizations

![image](https://github.com/user-attachments/assets/120e1325-949e-4b70-88a7-9142ec303787)

- The scatter plots for **RF** demonstrate better alignment between predicted and actual values compared to DT, with reduced variance around the regression lines.  
- The model effectively captures trends for most features, major deviations are observed for Dissolved Oxygen with some minor deviations for other features.

**Conclusion for RF:** RF’s ensemble learning approach enhances prediction accuracy and robustness, making it a reliable alternative for multi-output regression.

---

## XGBoost (XGB) Results


### Model Performance


![image](https://github.com/user-attachments/assets/a031b228-abd9-4212-a18c-1534a4aa4c73)



### Implementation of the model
For a sample input:

Sample Data from our Dataset:
- Temperature (C): 24.87480289
- Turbidity (NTU): 99
- Dissolved Oxygen (mg/L): 31.12043703
- pH: 8.519841242
- Ammonia (mg/L): 50.91882442
- Nitrate (mg/L): 1223
- Population: 75
- Fish Length (cm): 35.12
- Fish Weight (g): 195.2
- Category: B
- Size: L

![image](https://github.com/user-attachments/assets/a59daec3-b6c1-49f7-89c0-49e71358adc3)


The recommended environmental conditions are:  

![image](https://github.com/user-attachments/assets/cc7b5b5b-5b43-4ce0-9a78-3f623cc55ec8)


### Observations from Visualizations

![image](https://github.com/user-attachments/assets/ced935f1-7f4b-4cc0-ac75-b26ec300985d)

- The scatter plots for **XGB** show strong alignment between predicted and actual values, with minimal deviations.  
- The regression lines closely fit the data points, indicating high predictive accuracy across all features except Dissolved Oxygen.

**Conclusion for XGB:** XGBoost demonstrates exceptional performance, making it the most suitable model for this multi-output regression task.

---

## Model Comparison and Final Observations
### Summary Table
| Model          | MSE      | RMSE    | R² Score |
|----------------|----------|---------|----------|
| Decision Tree  | 24.8122  | 4.9812  | 0.7231   |
| Random Forest  | 22.7593  | 4.7707  | 0.7633   |
| XGBoost        | 14.9467  | 3.8661  | 0.8502   |

### Key Takeaways
- **XGBoost** delivers the best performance due to its ability to capture complex interactions, making it ideal for this scenario.  
- **Random Forest** strikes a balance between interpretability and performance, serving as a robust alternative to XGBoost.  
- **Decision Tree** provides a simple baseline but lacks the capacity to model intricate relationships effectively.

In the next section, we will conclude by summarizing the results and justifying why **XGBoost** is the optimal choice for our data and use case.

## Conclusion

This project successfully developed a predictive machine learning model to assist aquaponics practitioners in maintaining optimal environmental conditions for achieving desired nitrate levels. By leveraging input data such as the farmer's nitrate requirements, fish category, size, and population, we utilized advanced algorithms to predict key environmental parameters like temperature, turbidity, dissolved oxygen, pH, and ammonia levels. 

Our use case demonstrates the practical utility of this model: farmers provide specific details about their aquaponics system, and the model outputs precise recommendations to help maintain ideal nitrate levels. Among the models evaluated, XGBoost emerged as the most effective due to its ability to capture complex interactions within the dataset and its superior performance metrics compared to Decision Tree and Random Forest models. The robust scalability and fine-tuning capabilities of XGBoost made it the optimal choice for this multi-output regression task.

This predictive framework provides a data-driven solution for aquaponics practitioners, enabling them to maximize yield by maintaining an ideal balance between fish and plant health. The model not only reduces guesswork but also minimizes resource wastage, contributing to eco-friendly and sustainable farming practices. By addressing the challenge of nitrate imbalance, our solution empowers practitioners to enhance productivity, optimize system efficiency, and adapt to changing conditions with ease.

Practitioners can implement this project by integrating real-time data from IoT-enabled sensors into the predictive model pipeline. The outputs can guide them in adjusting system parameters to achieve desired outcomes, making aquaponics systems more accessible and efficient for farmers at all levels. This innovative approach transforms aquaponics management into a precision-oriented process, ensuring that farmers can consistently achieve high yields while maintaining ecological sustainability.

Through this project, we have demonstrated the significant potential of machine learning in advancing aquaponics farming, paving the way for further innovations in sustainable agriculture.



