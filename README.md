 # Credit Card Fraud Detection: A Complete Data Pipeline with PySpark and Python

This project explores and models credit card fraud using a synthetic dataset inspired by real-world transactions. It demonstrates a full end-to-end data science pipeline—from exploratory data analysis and feature engineering to model preparation—leveraging both **PySpark** for scalable data processing and **Python** for flexible modeling.

## 📊 Project Overview

Fraudulent credit card transactions pose a significant challenge in digital commerce. In this project, I analyze a large dataset of labeled transactions to uncover behavioral, geographic, and temporal patterns associated with fraud. I implement a complete feature engineering pipeline and prepare the data for machine learning using best practices in both Pandas and PySpark.

The goal is not only to detect fraud accurately, but to build a **robust and scalable data preparation workflow**, ready for production environments.

## 📂 Dataset

This project uses the **Fraud Detection dataset** from Kaggle. The data contains over **1.2 million synthetic credit card transactions**, each labeled as fraudulent (`is_fraud = 1`) or legitimate (`is_fraud = 0`).

Each transaction includes:
- Transaction amount and timestamp
- User demographics (e.g. age, gender, location)
- Merchant information
- Behavioral and contextual features

The dataset is **synthetic but modeled on real-world behavior**, preserving privacy while reflecting realistic fraud patterns.

You can download it here:
🔗 [Kaggle - Fraud Detection Dataset](https://www.kaggle.com/datasets/ealaxi/paysim1)

After downloading, place the following files in the project root:
- `fraudTrain.csv`
- `fraudTest.csv`

> ⚠️ Note: The datasets are not included in this repository due to size constraints.

## 🎯 Objectives

- Perform detailed **exploratory data analysis** (EDA)
- Engineer insightful features based on geography, time, behavior, and interactions
- Replicate key steps in **PySpark** to demonstrate scalability
- Prepare a fully numeric dataset ready for model training
- Evaluate class imbalance and fraud patterns

## 🧪 Key Steps

### 1. Exploratory Analysis (Pandas & Matplotlib)

- Analyze class imbalance (`is_fraud`)
- Visualize distribution of transaction amounts (with log transform)
- Explore city population, merchant frequency, job and category breakdowns
- Compare fraud vs non-fraud distributions using boxplots
- Derive `age` from `dob`, and explore time-based features (hour, weekday, month)

### 2. Feature Engineering (`basic_cleaning()`)

- Temporal features: hour, day of week, month, time since previous transaction
- Behavioral signals: average transaction by user, daily transaction count
- Contextual features: Haversine distance between user and merchant
- Relative signals: amount compared to ZIP and state medians
- Flags: high-value transactions, known merchants

### 3. Final Preprocessing (`preproc()`)

- Drop redundant or low-importance features
- Apply log-transforms to skewed variables
- One-hot encode categorical columns
- Impute missing values using the median
- Ensure final dataset is fully numeric and model-ready

### 4. PySpark Replication

To demonstrate scalability, I reimplemented all main steps in PySpark, including:

- Data loading and schema inspection
- GroupBy operations and proportions
- Feature engineering using `Window`, `withColumn`, and `pyspark.sql.functions`
- One-hot encoding with `StringIndexer` and `OneHotEncoder`
- Visualization support using `.toPandas()` + `seaborn`

## 📦 Technologies Used

- **Python 3.10**
- **Pandas / NumPy**
- **Matplotlib / Seaborn**
- **Scikit-learn**
- **LightGBM**
- **PySpark**
- **Jupyter Notebook**

## 💡 Highlights & Learnings

- Showed how EDA and data preparation can scale from local to distributed environments
- Built custom logic for time-sensitive fraud features
- Managed class imbalance and feature skewness
- Handled PySpark integration with Python-native visualizations and modeling tools

## 🚀 How to Reproduce

```
# Step 1: Clone the repository
git clone https://github.com/your-username/fraud-detection-pyspark.git
cd fraud-detection-pyspark

# Step 2: Install dependencies
pip install -r requirements.txt

# Step 3: Configure Java for PySpark (adjust path as needed)
export JAVA_HOME=/opt/homebrew/opt/openjdk@17/libexec/openjdk.jdk/Contents/Home

# Step 4: Launch Jupyter
jupyter lab

Then open `Fraud-Detection.ipynb` and run all cells.
```

## 📌 Status

✔️ Complete
📁 Includes both Pandas and PySpark implementations
🧠 Ready for model training or extension into production pipelines

## 🖥️ Project Presentation

A PDF presentation summarizing the project and key insights is available for quick review:
👉 [Fraud-Detection-Presentation.pdf](./Fraud-Detection-Presentation.pdf)


## 📬 Contact

Feel free to connect or reach out:

- 🌐 [GitHub](https://github.com/ninamcunha)
- 💼 [LinkedIn](https://www.linkedin.com/in/nina-menezes-cunha/)
- 📧 ninamcunha@gmail.com
