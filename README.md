# LaLiga Statistics Analysis

This project was completed during my **Data Science Internship at Great Learning Pvt. Ltd.** (15 June 2020 to 16 August 2020). It focuses on applying statistical techniques to analyze LaLiga football team data, with the goal of developing metrics that help gauge team success over multiple seasons.

## ⚽ Domain

**Sports Analytics** – Spanish LaLiga Football Tournament

## 📌 Project Objective

To extract meaningful insights and performance metrics from historical LaLiga data such as team debut years, goals scored, matches won, points, and positional achievements. The project involved tasks such as data cleaning, arithmetic transformation, statistical aggregation, and custom metric calculation.

## 📁 Dataset Overview

- **File**: `Laliga.csv`  
- **Rows**: 61  
- **Columns**: 20  
- **Key Features**:
  - `Team`, `Points`, `GamesPlayed`, `GamesWon`, `GoalsFor`, `GoalsAgainst`
  - `Champion`, `Runner-up`, `Debut`, `BestPosition`

## 🔍 Tasks Performed

- Replaced invalid dash values with zero for computation compatibility
- Filtered teams that debuted between 1930–1980
- Computed and ranked top 5 teams based on:
  - Total points
  - Goal differences
  - Winning percentage
- Created a reusable function to compute goal difference (`GoalsFor - GoalsAgainst`)
- Added a `Winning_Percent` column = (GamesWon / GamesPlayed) * 100
- Grouped teams by `BestPosition` to calculate cumulative points across ranks

## 📈 Sample Insights

- **Top Goal Difference**: Real Madrid (+2807)
- **Top Winning Percent**: Real Madrid (~59.6%)
- **Maximum Cumulative Points by Best Position**:
  - Position 1 → 27,933 points
  - Position 2 → 6,904 points

## 🛠️ Technologies Used

- **Language**: Python
- **Libraries**: Pandas, NumPy

## 🎯 Learning Outcomes

- Exploratory data analysis using Pandas
- Custom metrics using functions and lambda expressions
- Statistical group operations and data transformation

## 🔗 Other Projects of this Internship

- **Project 1: Amazon E-commerce Purchase Analysis**  
  [GitHub Link](https://github.com/raunak-choudhary/Amazon-Ecommerce-Purchase-Analysis-Data-Science-Internship-2020.git)

- **Project 2: Insurance Cost Statistical Analysis**  
  [GitHub Link](https://github.com/raunak-choudhary/Insurance-Cost-Statistical-Analysis-Data-Science-Internship-2020.git)

## 👨‍💻 Author

**Raunak Choudhary**  
Email: [raunakchoudhary17@gmail.com](mailto:raunakchoudhary17@gmail.com)
