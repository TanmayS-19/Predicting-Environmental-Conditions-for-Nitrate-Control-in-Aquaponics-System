# Predicting Optimal Environmental Conditions for Nitrate Control in Aquaponics Systems


![image](https://github.com/user-attachments/assets/7ac78079-7324-4216-8425-53decbbd5810)


## Introduction
Aquaponics is an innovative and sustainable farming system that combines aquaculture (raising aquatic animals such as fish) with hydroponics (cultivating plants in water without soil). This system leverages the symbiotic relationship between fish and plants, where fish waste provides essential nutrients for plants, and plants help to filter and purify the water for the fish.

Aquaponics offers a sustainable solution to contemporary food production challenges by harnessing natural processes like the nitrogen cycle. It uses up to 90% less water compared to conventional agriculture, requires less land, and is ideal for urban or space-constrained environments. This system eliminates the need for synthetic fertilizers and pesticides, integrates fish and plant farming in a closed-loop system, and provides continuous production of both fish and crops. These attributes make aquaponics a highly sustainable and efficient method of farming.

Practitioners benefit significantly from aquaponics due to reduced resource consumption, lower operational costs, and the ability to produce fresh, organic food. However, maintaining the system’s balance is critical for achieving maximum yield. One of the most important factors in maintaining this balance is the nitrate level.

Nitrate (NO3-) is a vital nutrient for plant growth. In aquaponics systems, ammonia excreted by fish is converted into nitrate by beneficial bacteria through the nitrification process. Maintaining the right nitrate levels ensures optimal plant growth while preventing toxicity to fish. Insufficient nitrate levels can hinder plant growth, while excessive levels can harm fish health. Proper nitrate control prevents system imbalances, ensures water quality, and significantly improves crop yield and quality.

Environmental factors play a crucial role in controlling nitrate levels within aquaponics systems. Variables such as temperature, turbidity, dissolved oxygen, pH, and ammonia directly influence the nitrification process and overall system health. By analyzing fish populations of different species with varying environmental needs, data-driven techniques provide precise recommendations for these variables, enhancing system efficiency, productivity, and sustainability.

Leveraging historical data and machine learning, predictive models can empower practitioners to optimize aquaponics systems. These models identify patterns between environmental conditions and nitrate levels, providing actionable insights for maintaining the ideal parameters. This approach promotes urban agriculture, contributes to food security, and supports eco-friendly farming practices by fostering resilience, self-sufficiency, and resource efficiency in modern food systems.

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

![image](https://github.com/user-attachments/assets/94314e30-1b8b-48ed-aa1e-86c2dc773d22)

The dataset comprises three fish categories: **A**, **B**, and **C**. The distribution of fishes across these categories is as follows:
- **Category A**: 35.8%
- **Category B**: 42.3%
- **Category C**: 21.9%

This distribution indicates that **Category B** dominates the dataset, followed by **Category A** and **Category C**. The representation of each category ensures a balanced analysis, with significant insights derived for each fish type.

### 2. Nitrate Levels by Fish Category and Size

![image](https://github.com/user-attachments/assets/e15d507a-9ff0-418c-ae57-369658f0a281)

To explore the relationship between fish categories, sizes, and nitrate levels, the data was visualized using bar plots. The findings reveal:
- **Smaller fish (Size S)** consistently exhibit **lower nitrate levels** across all categories.
- **Medium-sized (M) and large (L) fish** show a gradual **increase in nitrate levels**, with large fish contributing the highest levels in each category.

This pattern highlights the correlation between fish size and nitrate levels, suggesting that larger fish populations may require careful monitoring to maintain the desired nitrate balance. The insight helps practitioners better manage environmental parameters based on the composition of their aquaponics systems.



