# Earthquake Analysis and Prediction

Earthquakes, sudden bursts of energy from the Earth's crust, can cause widespread damage and disrupt lives. While they're naturally occurring, predicting them could significantly reduce their impact. Traditionally, we only reacted to earthquakes after they happened, focusing on helping those affected. But now, advancements in earthquake science and data analysis offer a glimmer of hope: the possibility of forecasting seismic activity. By studying past earthquakes and identifying patterns, scientists can build more accurate models to predict future ones. This proactive approach empowers authorities to take preventive measures. They can issue warnings, design earthquake-resistant structures, and prepare for emergencies. Ultimately, predicting earthquakes could save lives and protect livelihoods from the devastating consequences of these natural disasters.

## Richter Scale

The Richter scale, developed by Charles F. Richter in 1935, is a logarithmic scale used to measure the magnitude of earthquakes. The magnitude quantifies the energy released at the earthquake's source. Each whole number increase on the Richter scale represents a tenfold increase in measured amplitude of seismic waves and approximately 31.6 times more energy release. For example, an earthquake with a magnitude of 6.0 is 10 times more powerful than one with a magnitude of 5.0. The Richter scale provides a standardized way to communicate the size and impact of seismic events, serving as a crucial tool for seismologists and emergency responders in assessing earthquake severity.

## Motivation

**Addressing the Pressing Need for Earthquake Prediction: A Project for Safer Communities**

The devastating consequences of earthquakes, with their potential for widespread destruction and loss of life, necessitate the urgent development of effective prediction models. This earthquake analysis and prediction project aims to address this critical need by leveraging the power of data and past seismic events to enhance our understanding and forecasting capabilities. Through in-depth exploration of historical data and identification of recurring patterns, we strive to develop highly accurate models that can predict future earthquakes with greater certainty. This knowledge will empower us to transition from a reactive to a proactive approach, enabling communities to implement crucial measures for risk mitigation and preparedness.

Our project seeks to deliver tangible outcomes that contribute to a safer future:

- **Early warnings**: Timely predictions will allow for evacuation of at-risk populations and implementation of emergency protocols, potentially saving countless lives.
- **Resilient infrastructure**: By incorporating earthquake-resistant design principles into critical infrastructure, we can minimize damage and ensure faster recovery times.
- **Enhanced preparedness**: Informed by accurate forecasts, communities can develop comprehensive response plans, allocate resources effectively, and raise public awareness, leading to a more effective response in the event of an earthquake.

By proactively addressing the threat of earthquakes through improved prediction capabilities, we can mitigate their devastating impact and build a more resilient future for vulnerable communities. This project represents a significant step towards achieving this vital goal.

## Goal

This project delves deep into earthquake data, dissecting the geological zones impacted by these tremors and their accompanying tsunamis. We aim to unravel the mysteries behind earthquakes, pinpointing the factors that influence their frequency and severity. This knowledge will serve as a cornerstone for preventive measures on local and global scales, allowing us to prioritize the construction of earthquake-resistant structures in vulnerable areas. By scrutinizing tectonic movements and uncovering long-term seismic patterns, we strive to enhance public awareness and preparedness. Ultimately, our objective is to predict high-risk seismic zones and develop accurate forecasts for future earthquakes, empowering communities to mitigate their devastating impact.

## Methodology

### Data Preprocessing and Cleaning:

- Loaded the dataset to access earthquake data for further examination.
- Inspected column names and data types to gain a preliminary understanding of the dataset's structure and composition.
- Scrutinized the dataset for values, aiming to detect and address any instances of duplicate entries that may compromise data integrity.
- Converted the date column from an object type to a datetime format to facilitate temporal analysis and ensure consistency in date-related operations.
- Verified each column for unique values, providing insights into the diversity and distinctiveness of data across different features.
- Reevaluated values, particularly from newly created features, to ensure accuracy and consistency in the dataset.
- Cleaned columns, specifically addressing the 'status' and 'data type' columns, by removing unnecessary values and ensuring data consistency.

### Exploratory Data Analysis and Feature Engineering:

Our objective was to visually depict the geographical impact of earthquakes and tsunamis, identify areas in need of earthquake-resistant structures, and gain insights into the factors influencing their frequency and severity.

- Extracted relevant columns from the date column to create additional features, enriching the dataset for more in-depth analysis.
- Generated a comprehensive profile report to conduct a thorough exploration of dataset characteristics, distributions, and potential anomalies.
- Plotted graphs to visually explore various relationships between different variables, gaining insights into potential patterns or trends.
- Utilized external library data to establish geographical boundaries corresponding to tectonic plates, enhancing the dataset's contextual information.
- Employed label encoding and color-coding techniques to transform non-numerical data into a numerical format, facilitating quantitative analysis.
- Calculated correlation metrics, with a particular focus on the magnitude variable, to understand relationships between different features in the dataset.

### Model Selection and Evaluation:

We used 40% of our dataset for training and testing the following models:

1. Linear Regression
2. Ridge Regression
3. XGBoost Regressor
4. Decision Tree
5. Random Forest

Model evaluation metrics include Mean Squared Error (MSE), Mean Absolute Error (MAE), and R-squared.

## Description of the Dataset

The earthquake dataset serves as an extensive repository capturing every recorded earthquake globally from 1990 to 2023. Comprising an impressive three million entries, each row corresponds to a distinct earthquake event, offering a comprehensive perspective. With a dataset size of 471MB, it provides valuable insights into seismic activities worldwide.

The dataset includes the following columns:

- Time
- Place
- Status
- Tsunami
- Significance
- Data_Type
- Magnitude
- State
- Longitude
- Latitude
- Depth
- Date

[Data Source](https://www.kaggle.com/datasets/alessandrolobello/the-ultimate-earthquake-dataset-from-1990-2023/data) [Tectonic Data Source](https://github.com/fraxen/tectonicplates)

## Results and Analysis

The methodology used for the project had the above-mentioned steps and their respective results are as follows:

### Data Preparation and Exploratory Data Analysis:

#### Figure 1.1: Histogram of Earthquake Magnitudes

The distribution of earthquake magnitudes is evident in the histogram, spanning from approximately 2 to 9. A notable peak is observed in the frequency of earthquakes with a magnitude around 5. However, earthquakes with a magnitude of 7 or higher are comparatively infrequent.

![image](https://github.com/mubinmodi/Earthquake-Analysis-and-Prediction/assets/47493706/983de208-976e-4e6f-976d-426f37d5f10e)

### Figure 2.6
![image](https://github.com/mubinmodi/Earthquake-Analysis-and-Prediction/assets/47493706/eeab94d8-25fc-4e89-affb-5b586fa9b56b)

Filtered for earthquakes with a magnitude exceeding 8, significance surpassing 500, and depth greater than 100, our analysis reveals:

- **Tectonic Plate Correlation:** Earthquake occurrences align closely with plate boundaries, indicating higher frequency where plates meet.

- **High Seismic Activity Zones:** Red dots densely cluster along plate boundaries, especially in the circum-Pacific belt and Asia-Himalayas region.

- **Potential Risk Assessment:** Countries along plate boundaries face higher earthquake risk, influencing infrastructure and emergency planning.

- **Data Distribution Patterns:** Earthquakes aren't uniformly distributed along plate boundaries; some areas show higher activity.

- **Mid-Ocean Ridges and Continental Boundaries:** Seismic activity occurs along mid-ocean ridges and continental boundaries, illustrating different plate boundary types.



#### Figure 3.1: Correlation Matrix w.r.t Magnitude

![image](https://github.com/mubinmodi/Earthquake-Analysis-and-Prediction/assets/47493706/7ba74181-47db-4757-806d-03f9ef01bbc9)

Analyzing this correlation matrix allows us to pinpoint optimal parameters for our prediction algorithms by assessing their correlation with the target variable, which, in this case, is magnitude. This exploration helps identify key features that strongly influence our predictive models.

## Model Evaluation

### Random Forest Results:
- **Mean Squared Error (MSE)** on Test Set: 0.017138338539015818
- **Mean Absolute Error (MAE)** on Test Set: 0.01562594026571847
- **R-squared** on Test Set: 0.9898979234163428

## Conclusion

**Plate Boundaries and Tension:** The concentration of earthquakes and tsunamis near tectonic plate boundaries is predominantly attributed to the tension along these boundaries. Tectonic plates, immense pieces of the Earth's crust, interact at these boundaries, creating stress and tension that can result in seismic activities.

**Identifying High-Impact Areas:** Understanding this connection allows for the confident identification of high-impact areas prone to significant seismic events. This knowledge underscores the critical need for constructing resilient structures in regions located near tectonic plate boundaries, where the risk of earthquakes and tsunamis is notably higher.

**Predictive Model Success:** The success in forecasting earthquake magnitudes using advanced models like Linear Regression, Ridge Regression, XGBoost Regressor, Decision Tree, and Random Forest highlights the effectiveness of machine learning techniques in predicting seismic events. These models utilize historical data to provide valuable insights into potential future occurrences.

### Performance Metrics:

- **Linear Regression:** MSE: 0.18299, MAE: 0.29188, R-squared: 0.89214
- **Ridge Regression:** MSE: 0.18299, MAE: 0.29188, R-squared: 0.89214
- **XGBoost Regressor:** MSE: 0.01768, MAE: 0.01990, R-squared: 0.98958
- **Decision Tree:** MSE: 0.03146, MAE: 0.01931, R-squared: 0.98145
- **Random Forest:** MSE: 0.01714, MAE: 0.01563, R-squared: 0.98990

- Among the linear models (Linear Regression, Ridge Regression), both perform similarly with high R-squared values.
- XGBoost Regressor outperforms linear models with significantly lower MSE and MAE, and a higher R-squared value.
- Decision Tree and Random Forest models show strong performance, with Random Forest slightly edging out XGBoost in terms of MSE and MAE.

In general, the tree-based models (XGBoost, Decision Tree, Random Forest) demonstrate superior predictive performance compared to the linear models in this scenario. Random Forest and XGBoost, in particular, showcase excellent performance with the lowest MSE, MAE, and highest R-squared values among all models.

## Project Impact

The project's comprehensive exploration of earthquake data contributes significantly to our geological understanding. It untangles the complexities surrounding seismic events and identifies key factors influencing their occurrence and intensity. These findings are paramount for implementing preventive measures and prioritizing the construction of earthquake-resistant structures, particularly in regions vulnerable to seismic activities. The project's impact extends beyond data analysis, emphasizing the practical implications for enhancing resilience and preparedness in earthquake-prone areas.

## References
- [Earthquake Dataset](https://www.kaggle.com/datasets/alessandrolobello/the-ultimate-earthquake-dataset-from-1990-2023/data)
- [Tectonic Data](https://github.com/fraxen/tectonicplates)

