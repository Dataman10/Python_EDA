# 📚 Books Data EDA Project

## 🧠 Project Overview

This project focuses on performing **Exploratory Data Analysis (EDA)** on a dataset containing information about various books.  
The goal of this analysis is to **understand the data**, identify **missing values**, **remove inconsistencies**, and generate **valuable insights** about publishing trends, author popularity, and other metrics.

---

## 📂 Dataset Information

**File Used:** `Books_Data_Clean.csv`

The dataset includes the following key columns:

- `Book Name` — Title of the book
- `Author` — Name of the author
- `Publishing Year` — Year the book was published
- `Genre` — Type of the book (e.g., Fiction, Non-fiction)
- `Price` — Price of the book
- `Ratings` — Average rating given by readers
- `Number of Reviews` — Total number of reviews received

---

## 🧹 Data Cleaning Steps

During the cleaning process, the following operations were performed:

1. **Handling Missing Values**

   ```python
   df.dropna(subset=["Book Name"], inplace=True)
   ```

   → Removed 21 rows where “Book Name” was missing.

2. **Removing Duplicates**

   ```python
   df.duplicated().sum()
   ```

   → Checked and removed duplicate rows to ensure data consistency.

3. **Fixing Invalid Publishing Years**

   ```python
   df = df[df["Publishing Year"] > 0]
   ```

   → Removed negative or unrealistic publishing years.

4. **Standardizing Column Names**
   → Renamed columns for easier readability (if required).

---

## 📊 Exploratory Data Analysis (EDA)

### 1️⃣ Statistical Summary

Used `df.describe()` to understand numerical distributions — mean, median, std deviation, etc.

### 2️⃣ Unique Value Analysis

```python
df.nunique()
```

→ Identified number of unique authors, genres, and publishing years.

### 3️⃣ Visualizations

EDA visualizations were created using **Matplotlib** and **Seaborn**:

- **Distribution plots** of Ratings, Price, and Publishing Year
- **Count plots** for Genre and Author frequency
- **Box plots** to detect outliers in Price
- **Correlation Heatmap** to analyze relationships between numerical features

Example:

```python
plt.figure(figsize=(10,6))
sns.heatmap(df.corr(), annot=True, cmap="coolwarm")
plt.title("Feature Correlation Heatmap")
plt.show()
```

---

## 💡 Key Insights

- Several records had invalid or negative publishing years — cleaned successfully.
- Majority of books were published **after 2000**.
- The “Book Name” column had **21 missing entries**, which were removed.
- A few authors have written multiple high-rated books, showing **consistent performance**.
- **Ratings and Number of Reviews** show a positive correlation, suggesting that popular books tend to receive higher ratings.

---

## 🧰 Tools & Libraries Used

| Library            | Purpose                                |
| ------------------ | -------------------------------------- |
| `pandas`           | Data loading, cleaning, transformation |
| `numpy`            | Numerical computations                 |
| `matplotlib`       | Visualization                          |
| `seaborn`          | Advanced visualizations                |
| `Jupyter Notebook` | Interactive environment for analysis   |

---

## 🧾 Project Structure

```
Books_EDA_Project/
│
├── Books_Data_Clean.csv      # Dataset
├── EDA.ipynb                 # Jupyter notebook containing all analysis
├── README.md                 # Project documentation
└── insights.txt              # Optional: text summary of findings
```

---

## 🚀 How to Run the Project

1. Clone this repository:

   ```bash
   git clone https://github.com/<your-username>/Books-EDA-Analysis.git
   cd Books-EDA-Analysis
   ```

2. Install dependencies:

   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

3. Open the notebook:
   ```bash
   jupyter notebook EDA.ipynb
   ```

---

## 🏁 Conclusion

This project demonstrates the importance of **data cleaning, visualization, and exploratory analysis** in understanding a dataset before building any predictive models.  
Through this EDA, clear patterns in publishing trends and reader behavior were identified — providing a strong base for further modeling or business analysis.

---

## ✨ Author

**Hitesh Moota**  
📍 Mumbai | 🎓 B.E. in Artificial Intelligence & Data Science  
📧 [hiteshmoota1@gmail.com](mailto:hiteshmoota1@gmail.com)  
💼 [LinkedIn](https://www.linkedin.com/in/hitesh-moota-6699ba235/) | 🧑‍💻 [GitHub]()
