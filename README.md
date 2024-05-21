# Flight Schedule Optimization

## Project Overview
This project focuses on analyzing and optimizing airplane connectivity using Graph Machine Learning and Linear Programming algorithms. Our goal is to enhance operational efficiency, improve customer satisfaction, and optimize economic performance within the aviation industry.

## Problem Statement and Objectives
The aviation industry faces numerous challenges that directly affect operational efficiency, customer satisfaction, and economic performance. In this project, we tackle five key problems:
1. **Predict Delays**: Develop predictive models for flight delays to enhance operational efficiency and reduce costs.
2. **Cluster Airports and Identify Hotspots**: Cluster airports based on traffic volume, delay patterns, and connectivity to propose targeted improvements.
3. **Find the Shortest Route**: Determine the shortest flying time between any two airports to enhance route planning.
4. **Optimize Routes Within a State**: Improve intra-state connectivity by finding the most efficient routes.
5. **Optimize Schedule**: Minimize total delay penalties and maximize the number of flights.

## Importance of the Study
Addressing these problems is crucial for:
- **Economic Efficiency**: Reducing delays and optimizing routes to lower operational costs.
- **Environmental Impact**: Reducing carbon emissions through optimized flight paths.
- **Passenger Experience**: Enhancing predictability and efficiency to improve customer satisfaction.
- **Strategic Planning**: Informing long-term infrastructure and policy decisions.

## Dataset
The dataset provides a comprehensive overview of flight information, including operational details, timings, and delays across various flights nationwide. Key attributes include:
- **Date and Identification**: Flight date, airline ID, aircraft registration number, and flight number.
- **Airport and Location Codes**: Origin and destination airport identifiers and IATA codes.
- **Timing and Delays**: Scheduled and actual departure/arrival times, various delay types, and cancellation reasons.
- **Performance Metrics**: Scheduled and actual elapsed times, and delay reasons quantified in minutes.

## Predicting Flight Arrival Delays (Machine Learning)
### Project Overview
Developed a predictive model to forecast flight delays, enhancing operational efficiency and improving passenger satisfaction.

### Data Collection and Preprocessing
- Focused on attributes like flight date, carrier ID, origin, destination, departure time, and arrival delay.
- Addressed missing data by eliminating columns with a high percentage of null values and dropping rows with any missing values.

### Correlation Analysis
- High correlation (0.84) between departure time and arrival time.
- Lesser correlations between other variables like carrier ID and cancellation status with delay times.

### Feature Engineering
- Categorized departure times into 'Morning,' 'Afternoon,' and 'Evening.'
- Extracted the month from flight dates and created a binary target variable indicating delay status.

### Model Building and Optimization
- Used a Gradient Boosting Classifier with SMOTE for class imbalance.
- Optimized the model with GridSearchCV.

### Model Evaluation
- Achieved 71.01% accuracy and 76.85% ROC AUC.
- Insights indicated "DEP_HOUR" as the most significant feature for predicting delays.

### Detailed Results
- **Accuracy**: 71.01%
- **ROC AUC**: 76.85%
- **Feature Importance**: Departure hour had the most significant influence, followed by departure delay.

## Airport Profiling (Clustering Analysis)
### Objective
Identify patterns in airport operations related to delays and cancellations using clustering techniques.

### Data Preparation and Exploration
- Loaded flight records dataset and handled missing values.

### Feature Selection
- Focused on departure/arrival delays, carrier-specific delays, weather delays, NAS delays, late aircraft delays, and cancellation rates.

### Clustering Analysis
- Used K-means clustering to group airports based on delay and cancellation characteristics.

### Detailed Results
- **Cluster 1 ("High Efficiency Low Impact")**: Lowest average delays and cancellations.
- **Cluster 2 ("Moderate Delays Controlled Impact")**: Moderate levels of delays primarily driven by NAS delays.
- **Cluster 3 ("Average Performance")**: Intermediate levels of delays and cancellations.
- **Cluster 4 ("High Delays and Cancellations")**: Highest delays and cancellations, particularly late aircraft delays.

### Insights and Recommendations
- **Cluster 1**: Maintain high standards and share best practices.
- **Cluster 2**: Enhance traffic management systems.
- **Cluster 3**: Strengthen contingency planning and real-time communication.
- **Cluster 4**: Implement rigorous schedule reviews and improve ground operations.

## Shortest Path between 2 Airports (Dijkstra’s Algorithm)
### Problem Statement
Develop an algorithm to determine the shortest paths in terms of flight time between two designated airports.

### Methodology
- Created a directed graph using NetworkX.
- Used shortest_simple_paths to generate all possible paths from source to target.
- Calculated total flying time for each path.

### Detailed Results
- **Example**: Three shortest paths between JFK and LAX with respective flight times provided.

## Optimize Airport Connectivity within a State (Kruskal’s)
### Data Preparation
Filtered dataset to include flights within California. Handled missing values and constructed a graph with delays as weights.

### Minimum Spanning Tree (MST)
- Used Kruskal's algorithm to compute MST.
- Compared total delays in full network vs. MST.

### Detailed Results
- **Total Delay in Full Network**: 562.0 minutes
- **Total Delay in MST**: 36.0 minutes
- **Efficiency**: Over 93% reduction in total delay using MST.

### Insights
- Visual representation of the network.
- Strategic planning recommendations for airlines and airport authorities.

## Optimization of Flight Schedules to Minimize Delay Penalties
### Problem Setup
- Defined a linear programming problem using the pulp library.
- Created binary decision variables for each flight.
- Objective: Maximize flights while reducing penalty costs by at least 20%.

### Penalty Estimation
- Assigned penalty costs to different types of delays to quantify financial impact.

### Detailed Results
- **Total Flights Before Optimization**: 1652
- **Total Flights After Optimization**: 1624
- **Total Penalty Cost Before Optimization**: $1,838,950
- **Total Penalty Cost After Optimization**: $1,468,400
- **Reduction in Penalty Costs**: $370,550 (20.15%)

### Insights
- Efficiency in operation and cost management.
- Strategic operational benefits.

##  Conclusion
The Flight Schedule Optimization project successfully addressed key challenges in the aviation industry using advanced analytical techniques. Our predictive models, clustering analyses, and optimization strategies demonstrated significant potential for improving operational efficiency, reducing costs, and enhancing passenger satisfaction. The detailed results highlighted the effectiveness of data-driven decision-making in optimizing flight schedules, minimizing delays, and improving overall connectivity.

