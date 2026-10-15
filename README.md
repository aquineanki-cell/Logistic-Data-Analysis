# Logistics Data Analysis & Optimization


This repository contains an end-to-end data analytics and predictive modeling pipeline developed during the Yuva Intern Data Analyst Program.

The project focuses on optimizing last-mile delivery operations by analyzing a dataset of 25,000 shipment records. The goal is to identify cost drivers, visualize performance bottlenecks across multiple logistics partners, and build a machine learning model to predict and prevent shipment delays.

📋 Project Overview

Last-mile delivery is often the most expensive and unpredictable phase of the supply chain. In this simulated scenario, the objective was to transition a centralized logistics aggregator from a reactive state to a predictive state. By analyzing historical delivery data (partner performance, weather conditions, vehicle types, and package weights), this project delivers actionable strategies to improve the On-Time Delivery (OTD) Rate and reduce wasted transportation costs.

🗓️ Project Pipeline (4-Week Breakdown)

Phase 1: Strategic Planning & KPI Definition

Defined the core business problem and framed the analytical approach.

Established primary KPIs: On-Time Delivery (OTD) Rate, Average Cost Per Kilometer, and Customer Satisfaction Score (CSAT).

Designed the 4-phase data science roadmap.

Phase 2: Data Preprocessing & Cleaning

Conducted initial data inspection using pandas.

Data Formatting: Fixed hidden data corruption where delivery_time_hours and expected_time_hours were exported as Unix epoch nanosecond strings, successfully extracting the actual integer hours.

Converted continuous floating-point delivery_id labels into proper categorical strings to prevent calculation errors.

Phase 3: Exploratory Data Analysis (EDA)

Generated statistical summaries and visual dashboards using matplotlib and seaborn.

Key Finding 1 (Cost Drivers): A correlation heatmap revealed a 0.99 correlation between distance and cost, but a 0.10 correlation between weight and cost, indicating a flaw in the current pricing model.

Key Finding 2 (Weather Impact): A grouped bar chart demonstrated that stormy weather pushes delay rates past 40%, particularly crippling exposed vehicles like scooters (43.05% delay rate).

Phase 4: Predictive Modeling & Optimization

Engineered features using One-Hot Encoding to convert categorical text data into machine-readable numerical formats.

Trained a Random Forest Classifier (80/20 train-test split) to predict binary shipment delays.

Model Performance: Achieved an overall accuracy of 71.48%.

Feature Importance: Identified distance_km (0.348) and package_weight_kg (0.320) as the overwhelming drivers of delivery delays, followed by stormy weather.

💡 Business Recommendations

Based on the predictive insights and EDA, the following operational changes are recommended:

Strict Weight-to-Distance Dispatch Thresholds: Implement automated rules restricting heavy packages from being assigned to light-duty vehicles on long-distance routes.

Dynamic Weather Routing: Automatically pause scooter and bike assignments when severe storms are forecasted, routing vulnerable packages to enclosed EV vans instead.

Smart Customer Estimates: Run the predictive model before a package leaves the warehouse. For high-risk deliveries, automatically append a 12-to-24 hour buffer to the expected delivery time at checkout to protect customer satisfaction scores.
