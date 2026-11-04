
# Iris Atlas
### Can Mathematics Help Us Distinguish Iris Flower Species?

**Advanced Mathematics Project | Data Analysis with Python**

[View Live Research Website](https://phuonglynguyenorient-web.github.io/advanced-math-iris-project/)

---

## 1. Research Question

**How can mathematical relationships between flower measurements help distinguish different iris species?**

Flowers belonging to different species can have different physical characteristics. Mathematical and statistical methods allow us to investigate these differences quantitatively.

This project explores two complementary questions:

1. How does petal length differ among the three iris species?
2. How strongly are petal length and petal width related?

The objective is to identify and interpret mathematical patterns in the data, rather than to develop a complete species classification system.

## 2. Dataset

The project uses the **Iris dataset**, available from the UCI Machine Learning Repository.

**Dataset source:**  
https://archive.ics.uci.edu/dataset/53/iris

The dataset contains:

- 150 flower observations
- 3 species: Iris-setosa, Iris-versicolor, and Iris-virginica
- 50 observations per species
- 4 numerical measurements per flower
- No missing values

The four numerical variables are:

| Variable | Unit |
|---|---|
| Sepal length | cm |
| Sepal width | cm |
| Petal length | cm |
| Petal width | cm |

The analyses focus on petal length and petal width.

The original dataset is included in this repository as `iris.data`.

## 3. Mathematical Methods

Two distinct quantitative analyses are performed using Python.

### 3.1 Descriptive Statistics

The first analysis compares petal length across the three iris species.

For each species, we calculate:

- Sample mean
- Sample variance
- Sample standard deviation

The sample mean is:

$$
\bar{x}=\frac{1}{n}\sum_{i=1}^{n}x_i
$$

The sample variance is:

$$
s^2=\frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

The sample standard deviation is:

$$
s=\sqrt{s^2}
$$

These statistics describe the typical petal length and its variability within each species.

### 3.2 Ordinary Least Squares Regression

The second analysis investigates the relationship between petal length and petal width.

A simple linear regression model is fitted:

$$
\hat{y}_i=a+bx_i
$$

where:

- \(x_i\) is petal length.
- \(y_i\) is observed petal width.
- \(\hat{y}_i\) is predicted petal width.
- \(a\) is the intercept.
- \(b\) is the slope.

Ordinary least squares estimates the coefficients by minimizing the sum of squared residuals:

$$
\min_{a,b}\sum_{i=1}^{n}(y_i-a-bx_i)^2
$$

The coefficient of determination is:

$$
R^2=1-\frac{\sum_{i=1}^{n}(y_i-\hat{y}_i)^2}{\sum_{i=1}^{n}(y_i-\bar{y})^2}
$$

This statistic measures how much of the observed variation in petal width is accounted for by the fitted linear model.

## 4. Analysis One: Descriptive Statistics

The first analysis compares the average petal length and sample standard deviation of each iris species.

### Results

| Species | Mean Petal Length (cm) | Sample SD (cm) |
|---|---:|---:|
| Iris-setosa | 1.464 | 0.174 |
| Iris-versicolor | 4.260 | 0.470 |
| Iris-virginica | 5.552 | 0.552 |

### Interpretation

Iris-setosa has the shortest petals on average, while Iris-virginica has the longest.

Iris-versicolor lies between these two species.

The sample standard deviation is smallest for Setosa and largest for Virginica, indicating different levels of variability in petal length.

These results suggest that petal length is a useful measurement for investigating species differences.

However, differences between group averages do not establish that every individual flower can be classified correctly.

### Figure 1

[View Petal Length Comparison (PDF)](Figure1_Petal_Length.pdf)

This figure visualizes differences in petal length among the three iris species.

## 5. Analysis Two: Linear Regression

The second analysis uses ordinary least squares to model petal width as a function of petal length.

### Estimated Equation

$$
\widehat{\text{Petal Width}}
=0.4164(\text{Petal Length})-0.3665
$$

The coefficient of determination is:

$$
R^2=0.9269
$$

### Interpretation

The estimated slope is positive.

According to the fitted model, an additional centimetre of petal length corresponds to approximately 0.4164 centimetres of additional predicted petal width.

The R-squared value indicates that approximately **92.69% of the observed variation in petal width** is accounted for by petal length in the pooled linear regression model.

This suggests a strong positive overall linear association between petal length and petal width.

However, the regression combines observations from all three species. The strong overall relationship may partly reflect differences between species rather than an equally strong relationship within each species.

### Figure 2

[View Linear Regression Figure (PDF)](Figure2_Linear_Regression.pdf)

This figure shows the relationship between petal length and petal width together with the fitted regression line.

## 6. Discussion and Limitations

The two analyses provide complementary information.

Descriptive statistics reveal differences in typical petal length among the species, while linear regression identifies a strong overall association between two flower measurements.

Together, these results demonstrate how mathematical methods can reveal patterns in biological data.

Nevertheless, the project has several limitations:

- Group means and standard deviations do not fully describe the distribution of individual observations.
- The regression model pools observations from all three species.
- A strong linear relationship does not imply causation.
- The analyses do not directly estimate species classification accuracy.
- Only two of the four available numerical measurements are examined in detail.

Future work could investigate species-specific regression models, include additional measurements, or evaluate a classification model using unseen data.

## 7. Conclusion

The project demonstrates that mathematical methods can help us understand differences between iris species.

The descriptive statistical analysis shows substantial differences in average petal length among Iris-setosa, Iris-versicolor, and Iris-virginica.

The linear regression analysis reveals a strong positive overall association between petal length and petal width, with an R-squared value of approximately 0.9269.

These findings support the usefulness of mathematical analysis for exploring species differences.

However, identifying individual flowers accurately would require further classification analysis.

## 8. Repository Structure

```text
advanced-math-iris-project/
|
|-- README.md
|-- index.html
|-- iris.data
|-- Iris_Analysis.ipynb
|-- Figure1_Petal_Length.pdf
|-- Figure2_Linear_Regression.pdf
```

### File Descriptions

| File | Description |
|---|---|
| `README.md` | Project overview, methods, results, and instructions |
| `index.html` | Source code for the research website |
| `iris.data` | Original Iris dataset |
| `Iris_Analysis.ipynb` | Python notebook containing the mathematical analyses |
| `Figure1_Petal_Length.pdf` | Visualization of petal length across species |
| `Figure2_Linear_Regression.pdf` | Visualization of the fitted linear regression |

## 9. Reproducibility

The analyses can be reproduced using the files in this repository.

### Step 1: Download the Repository

Download the repository as a ZIP file from GitHub or clone it using:

```bash
git clone https://github.com/phuonglynguyenorient-web/advanced-math-iris-project.git
```

### Step 2: Prepare the Python Environment

Install Jupyter Notebook and the Python libraries required by the analysis.

For example:

```bash
pip install notebook numpy pandas matplotlib scipy
```

### Step 3: Open the Notebook

Open `Iris_Analysis.ipynb` in Jupyter Notebook.

Keep `iris.data` in the same directory as the notebook.

### Step 4: Run the Analysis

Execute the notebook cells in order.

The notebook contains the Python code used to calculate the statistics, estimate the regression relationship, and generate the visualizations.

The resulting figures are also available as PDF files in the repository.

## 10. Live Research Website

The complete research report is available as a public HTML website hosted using GitHub Pages.

**Website:**  
https://phuonglynguyenorient-web.github.io/advanced-math-iris-project/

**GitHub Repository:**  
https://github.com/phuonglynguyenorient-web/advanced-math-iris-project

## 11. References

**UCI Machine Learning Repository.** Iris Dataset.  
https://archive.ics.uci.edu/dataset/53/iris

**Fisher, R. A. (1936).** The use of multiple measurements in taxonomic problems. *Annals of Eugenics, 7*(2), 179–188.

---

*Advanced Mathematics Project — Iris Atlas*

