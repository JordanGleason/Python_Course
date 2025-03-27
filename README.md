# 💼 Data Analyst Job Market Project

🚀 **Quick Overview**  
This project breaks down real-world data from job listings to understand the data job market — specifically for data analyst roles. I wanted to know what skills actually matter, what they pay, and how trends shift over time. So I used real data, Python, and visualizations to answer those questions and guide my own learning path.

📊 **Data Source**: [Luke Barousse's Python Course](https://lukebarousse.com/python) — includes job titles, salaries, locations, and skills.

---

## ❓ Questions I Asked

- What are the most in-demand skills for the top 3 data roles?
- How are skill trends shifting for Data Analysts over time?
- What do jobs and skills pay for Data Analysts?
- What are the best skills to learn that are both high-paying and in demand?

---

## 🛠 Tools & Stack

- **Python** – the engine for everything
  - `pandas` – data manipulation
  - `matplotlib` / `seaborn` – data visualization
- **Jupyter Notebooks** – to keep code + notes together
- **VS Code** – for writing + debugging
- **Git & GitHub** – version control + publishing

---

## 🧹 Data Prep

```python
import ast
import pandas as pd
import seaborn as sns
from datasets import load_dataset
import matplotlib.pyplot as plt

# Load & clean
dataset = load_dataset('lukebarousse/data_jobs')
df = dataset['train'].to_pandas()
df['job_posted_date'] = pd.to_datetime(df['job_posted_date'])
df['job_skills'] = df['job_skills'].apply(lambda x: ast.literal_eval(x) if pd.notna(x) else x)

# Filter for US
df_US = df[df['job_country'] == 'United States']
```

---

## 🔍 Analysis Breakdown

### 1️⃣ Most Demanded Skills for Top 3 Data Roles
Pulled the top 5 skills for the 3 most common data jobs.

📓 Notebook → [`1_Skill_Demand.ipynb`](Python_Project/1_Skill_Demand.ipynb)

**Key Insights:**
- SQL is everywhere. Essential for Analysts and Scientists.
- Data Engineers = AWS, Azure, Spark.
- Python is the go-to for Data Scientists.

---

### 2️⃣ Skill Trends for Data Analysts
Tracked monthly skill popularity in 2023.

📓 Notebook → [`2_Skills_Trends.ipynb`](Python_Project/2_Skills_Trends.ipynb)

**Key Insights:**
- SQL stayed dominant but dipped late in the year.
- Excel demand spiked around fall.
- Tableau and Python stayed consistent.

---

### 3️⃣ Salary Breakdown
Analyzed salary distributions across roles + skills.

📓 Notebook → [`3_Salary_Analysis.ipynb`](Python_Project/3_Salary_Analysis.ipynb)

**Key Insights:**
- Senior Data Scientists/Engineers can exceed **$600K**.
- Data Analyst salaries are more stable.
- Skills like `dplyr` and `Gitlab` link to higher salaries.

---

### 4️⃣ Best Skills = High Pay + High Demand
Identified overlap between pay and popularity.

📓 Notebook → [`4_Optimal_Skills.ipynb`](Python_Project/4_Optimal_Skills.ipynb)

**Key Insights:**
- Oracle = highest salary, but not common.
- Python, Tableau, SQL Server = great balance.
- Tableau & Power BI = top-tier visualization skills worth learning.

---

## 🧠 What I Learned

- **Python** is a game-changer for data work
- Good data cleaning = better insights
- Salary ≠ demand — pick skills that hit both

---

## 📌 Final Thoughts
This project gave me a way to explore data analysis by analyzing data about analysts. Now I have a clearer learning path, better awareness of what's in demand, and a solid GitHub portfolio to show for it.

👉 **Check out the full project + notebooks here:** [🔗 GitHub Repo](https://github.com/JordanGleason)

