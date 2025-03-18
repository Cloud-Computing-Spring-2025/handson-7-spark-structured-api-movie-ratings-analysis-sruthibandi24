# 🎥 Movie Ratings Analysis - Spark Assignment

## **Prerequisites**

Before starting the assignment, ensure you have the following software installed and properly configured on your machine:

1. **Python 3.x**:
   - [Download and Install Python](https://www.python.org/downloads/)
   - Verify installation:
     ```bash
     python3 --version
     ```

2. **PySpark**:
   - Install using `pip`:
     ```bash
     pip install pyspark
     ```

3. **Apache Spark**:
   - Ensure Spark is installed. You can download it from the [Apache Spark Downloads](https://spark.apache.org/downloads.html) page.
   - Verify installation by running:
     ```bash
     spark-submit --version
     ```

4. **Docker & Docker Compose** (Optional):
   - If you prefer using Docker for setting up Spark, ensure Docker and Docker Compose are installed.
   - [Docker Installation Guide](https://docs.docker.com/get-docker/)
   - [Docker Compose Installation Guide](https://docs.docker.com/compose/install/)

## **Setup Instructions**

### **Project Structure**
```
MovieRatingsAnalysis/
├── input/
│   └── movie_ratings_data.csv
├── outputs/
│   ├── binge_watching_patterns.csv
│   ├── churn_risk_users.csv
│   └── movie_watching_trends.csv
├── src/
│   ├── task1_binge_watching_patterns.py
│   ├── task2_churn_risk_users.py
│   └── task3_movie_watching_trends.py
└── README.md
```

### **Running the Analysis Tasks**
```bash
spark-submit src/task1_binge_watching_patterns.py
spark-submit src/task2_churn_risk_users.py
spark-submit src/task3_movie_watching_trends.py
```

## **Dataset**

### **Columns Description**
| Column Name           | Data Type | Description |
|------------------------|----------|-------------|
| UserID                 | Integer  | Unique user identifier |
| MovieID                | Integer  | Unique movie identifier |
| MovieTitle             | String   | Name of the movie |
| Genre                  | String   | Genre (Action, Comedy, Drama, etc.) |
| Rating                 | Float    | User rating (1.0 - 5.0) |
| ReviewCount            | Integer  | Number of reviews by the user |
| WatchedYear            | Integer  | Year watched |
| UserLocation           | String   | Country |
| AgeGroup               | String   | Age category (Teen, Adult, Senior) |
| StreamingPlatform      | String   | Platform watched |
| WatchTime              | Integer  | Total minutes watched |
| IsBingeWatched         | Boolean  | True if watched 3+ movies in a day |
| SubscriptionStatus     | String   | Active or Canceled |

## **Assignment Tasks**

### 👉 **Task 1 - Detect Binge-Watching Patterns**

#### **Objective**
Identify which age groups binge-watch the most.

#### **Code - src/task1_binge_watching_patterns.py**
```python
(from previous content)
```

#### **Expected Output (binge_watching_patterns.csv):**
| AgeGroup | BingeWatchers | Percentage |
|---------|--------------|-----------|
| Adult   | 16           | 50.0      |
| Senior  | 14           | 39.89     |
| Teen    | 17           | 53.13     |

---

### 👉 **Task 2 - Identify Churn Risk Users**

#### **Objective**
Find users with canceled subscriptions and low watch time (<100 minutes).

#### **Code - src/task2_churn_risk_users.py**
```python
(from previous content)
```

#### **Expected Output (churn_risk_users.csv):**
| Churn Risk Users                                  | Total Users |
|---------------------------------------------------|------------|
| Users with low watch time & canceled subscriptions| 11         |

---

### 👉 **Task 3 - Trend Analysis Over the Years**

#### **Objective**
Analyze yearly movie-watching trends and peak years.

#### **Code - src/task3_movie_watching_trends.py**
```python
(from previous content)
```

#### **Expected Output (movie_watching_trends.csv):**
| WatchedYear | MoviesWatched |
|------------|--------------|
| 2018       | 17           |
| 2019       | 16           |
| 2020       | 17           |
| 2021       | 12           |
| 2022       | 20           |
| 2023       | 18           |

---

## **Submission Guidelines**
- Submit all `src/` scripts
- Attach the `outputs/` CSV files
- Include this `README.md`
- Ensure dataset `movie_ratings_data.csv` is in `input/`
- Zip the folder and submit before the deadline

---

## **Challenges Faced**
- Managing large data loads while ensuring efficient computation.
- Ensuring correct percentage calculation and accurate joins.
- Filtering records based on multiple conditions.
- Formatting the output CSV to match exact expected results.

## **Approach**
- Defined a clear schema and loaded data efficiently with Spark.
- Used Spark DataFrame APIs to apply transformations and calculations.
- Applied groupBy, filter, join, and aggregation operations.
- Outputted results cleanly using `.coalesce(1)` to avoid multiple CSV parts.

## **Findings**
- Teenagers had the highest binge-watching percentage at 65.71%.
- 10 churn risk users were identified based on low watch time and canceled subscriptions.
- Movie-watching activity peaked in the year 2023, showing streaming trend growth.

👍 **Good luck, and happy analyzing!**

