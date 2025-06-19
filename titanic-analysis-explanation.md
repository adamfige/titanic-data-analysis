
# 📊 Titanic Survival Data Analysis - Full Explanation

This document explains the steps and results of the Titanic survival data analysis project.

## 📌 Project Idea

The project analyzes the famous Titanic passenger data to understand which factors affected passengers’ survival. The main questions are:
- Did women survive more than men?
- Did passengers in higher classes have better survival rates?
- Did age, fare, or embarkation point influence survival?

## 🧾 Step-by-Step Explanation

### 1. Load the Dataset
```python
df = sns.load_dataset('titanic')
```
We use the Titanic dataset available in the seaborn library. It includes features like `sex`, `age`, `pclass`, `survived`, and more.

---

### 2. Display Basic Info
```python
print(df.info())
print(df.head())
```
This gives an overview of the dataset and its structure.

---

### 3. Handle Missing Data
```python
df['age'].fillna(df['age'].median(), inplace=True)
df.dropna(subset=['embarked'], inplace=True)
```
- Fill missing `age` values with the median.
- Drop rows with missing `embarked` values.

---

### 4. Survival by Gender
```python
sns.countplot(x='sex', hue='survived', data=df)
```
**Result:** Women had a much higher survival rate than men.

✅ **Interpretation:** Women were prioritized during evacuation ("women and children first").

---

### 5. Survival by Class
```python
sns.countplot(x='pclass', hue='survived', data=df)
```
**Result:** First-class passengers had the highest survival rate.

✅ **Interpretation:** Wealthier passengers were located near lifeboats and were prioritized.

---

### 6. Correlation Heatmap
```python
sns.heatmap(df.corr(numeric_only=True), annot=True, cmap='coolwarm')
```
**Result:** Strong negative correlation between `pclass` and `survived`. Positive correlation between `fare` and `survived`.

✅ **Interpretation:** Higher class and higher fare increased the chance of survival.

---

## 📍 Conclusion

- **Sex, class, and fare** were the most important factors in survival.
- The analysis demonstrates how simple statistics and visualization can provide real insights into real-world events.

---

You can include this explanation in your GitHub repo as a reference for others viewing your project.
