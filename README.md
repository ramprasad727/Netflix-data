# 🎬 Netflix Data Analysis

## 📌 Project Overview

This project performs an **Exploratory Data Analysis (EDA)** on the Netflix titles dataset using Python.

The main objective is to understand Netflix's content library by analyzing movies and TV shows based on their **type, release year, country, directors, ratings, duration, and genres**.

The project demonstrates practical skills in **Data Cleaning, Data Preprocessing, Exploratory Data Analysis, Data Visualization, and Python Data Analytics**.

---

## 🎯 Objectives

* Analyze the distribution of Movies and TV Shows on Netflix.
* Identify the years with the highest amount of content released.
* Find the top countries contributing Netflix content.
* Identify the most frequently appearing directors.
* Analyze the distribution of content ratings.
* Analyze the duration of TV Shows.
* Identify the most common genres on Netflix.
* Handle missing values and prepare the dataset for analysis.
* Create visualizations to communicate important findings.

---

## 🛠️ Technologies Used

| Technology       | Purpose                              |
| ---------------- | ------------------------------------ |
| Python           | Programming language                 |
| Pandas           | Data manipulation and analysis       |
| NumPy            | Numerical operations                 |
| Matplotlib       | Data visualization                   |
| Seaborn          | Statistical visualization            |
| Jupyter Notebook | Development and analysis environment |

---

## 📂 Dataset

The project uses the **Netflix Titles dataset** containing information about movies and TV shows available on Netflix.

### Important Columns

* `show_id` – Unique identifier for each title
* `type` – Movie or TV Show
* `title` – Name of the content
* `director` – Director of the content
* `cast` – Cast members
* `country` – Country associated with the content
* `date_added` – Date the content was added to Netflix
* `release_year` – Original release year
* `rating` – Content rating
* `duration` – Movie duration or number of TV seasons
* `listed_in` – Genres/categories
* `description` – Description of the content

---

## 🔄 Project Workflow

```text
Netflix Dataset
      ↓
Data Loading
      ↓
Data Understanding
      ↓
Data Cleaning
      ↓
Missing Value Handling
      ↓
Date Transformation
      ↓
Feature Extraction
      ↓
Exploratory Data Analysis
      ↓
Data Visualization
      ↓
Insights & Conclusions
```

---

## 🧹 Data Cleaning

The following preprocessing steps were performed:

### 1. Handling Missing Values

Missing values were checked using:

```python
df.isna().sum()
```

Missing values in columns such as:

* `duration`
* `director`
* `country`
* `cast`

were handled using the **mode value**.

Example:

```python
df['duration'] = df['duration'].fillna(df['duration'].mode()[0])
```

### 2. Date Processing

The `date_added` column was converted into a datetime format.

```python
df['date_added'] = pd.to_datetime(
    df['date_added'],
    format='%d %m %Y',
    errors='coerce'
)
```

Additional features were extracted:

```python
df['Year'] = df['date_added'].dt.year
df['Month'] = df['date_added'].dt.month
```

---

## 📊 Exploratory Data Analysis

### 1. Movies vs TV Shows

The project analyzes the number of Movies and TV Shows available in the dataset.

```python
df['type'].value_counts()
```

A Seaborn count plot is used to visualize the distribution.

---

### 2. Content Released by Year

The number of Netflix titles by release year is analyzed.

```python
a = df['release_year'].value_counts().sort_index()
```

A line plot is used to understand the trend of content releases over time.

---

### 3. Top 10 Countries

The project identifies the top countries contributing Netflix content.

```python
b = df['country'].value_counts().head(10)
```

The results are visualized using bar charts.

---

### 4. Top Directors

The most frequently appearing directors are identified.

```python
c = df['director'].value_counts().head(10)
```

A bar chart is used to visualize the top directors.

---

### 5. Rating Distribution

The project analyzes the distribution of Netflix content ratings.

```python
d = df['rating'].value_counts()
```

A Seaborn count plot is used for visualization.

---

### 6. TV Show Duration

TV Shows are filtered from the dataset:

```python
tv = df[df['type'] == 'TV Show']
```

The most common TV Show durations are then analyzed.

```python
e = tv['duration'].value_counts().head(5)
```

A pie chart is used to represent the distribution.

---

### 7. Top Genres

The `listed_in` column is split to analyze individual genres.

```python
genres = df['listed_in'].str.split(', ', expand=True).stack()
```

The top 10 genres are identified using:

```python
genres.value_counts().head(10)
```

A bar chart is used to visualize the most common genres.

---

### 8. Missing Value Visualization

A heatmap is created to visually inspect missing values.

```python
sns.heatmap(df.isnull(), cbar=True)
plt.show()
```

---

## 📈 Visualizations

The project includes visualizations for:

* 🎥 Movie vs TV Show distribution
* 📅 Content released by year
* 🌍 Top 10 countries
* 🎬 Top directors
* ⭐ Rating distribution
* 📺 TV Show duration
* 🎭 Top genres
* 🔎 Missing-value heatmap

---

## 🔍 Key Analysis Areas

The analysis focuses on answering questions such as:

1. Is Netflix's library dominated by Movies or TV Shows?
2. How has Netflix content changed across release years?
3. Which countries produce the most Netflix content?
4. Which directors appear most frequently?
5. Which ratings are most common?
6. What are the most common TV Show durations?
7. Which genres dominate Netflix's content library?

---

## 📁 Project Structure

```text
Netflix-Data-Analysis/
│
├── Netflix data.ipynb
├── netflix_titles.csv
├── README.md
└── images/
    ├── content_type.png
    ├── top_countries.png
    ├── top_directors.png
    ├── ratings.png
    ├── genres.png
    └── tv_duration.png
```

---

## ▶️ How to Run the Project

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/netflix-data-analysis.git
```

### Step 2: Navigate to the Project

```bash
cd netflix-data-analysis
```

### Step 3: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Step 4: Start Jupyter Notebook

```bash
jupyter notebook
```

### Step 5: Open the Notebook

Open:

```text
Netflix data.ipynb
```

Run the cells sequentially to reproduce the analysis.

---

## 💡 Skills Demonstrated

This project demonstrates the following Data Science skills:

* Python Programming
* Pandas
* NumPy
* Data Cleaning
* Missing Value Treatment
* Data Preprocessing
* Feature Engineering
* Exploratory Data Analysis
* Data Visualization
* Statistical Analysis
* Jupyter Notebook
* Data Interpretation

---

## 🚀 Future Improvements

The project can be further improved by adding:

* Interactive dashboards using **Power BI** or **Tableau**
* Advanced statistical analysis
* Correlation analysis
* More detailed country-level analysis
* NLP analysis of movie/show descriptions
* Recommendation system
* Machine Learning-based content recommendation
* Interactive Streamlit dashboard
* Deployment as a web application

---

## 👨‍💻 Author

**Ram Prasad**

Engineering Student | Aspiring Data Analyst & Data Scientist

### Areas of Interest

* Data Analytics
* Data Science
* Python
* Machine Learning
* Data Visualization
* Business Intelligence

---

## ⭐ If You Like This Project

If you find this project useful, consider giving the repository a ⭐ star and following the project for future updates.

---

## 📜 License

This project is created for **educational and portfolio purposes**.
