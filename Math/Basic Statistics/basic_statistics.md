# Basic Statistics

## Table of Contents
1. [Preliminaries](#preliminaries)
2. [Part I Exploratory Data Analysis](#part-i-exploratory-data-analysis)
3. [Data Summary](#data-summary)
4. [Summary Measures](#summary-measures)

## Preliminaries

At some point in their work, researchers face the challenge of analyzing and understanding a set of data relevant to their particular subject of study. They will need to process the data to transform it into information, compare it with other results, or even assess its fit with a theory.

Statistical inference is one of the branches of statistics. This is the part of scientific methodology that aims to collect, reduce, analyze, and model data, from which, finally, inferences are made for a population from which the data (the sample) were obtained. An important aspect of data modeling is making revisions, based on which decisions can be made.

**Model**

Fundamentally, when analyzing data, we look for some form of regularity or pattern, or even model, present in the observations.

Imagine we are studying the relationship between income and consumption expenditure for a group of individuals. We might obtain a graph like the one in the figure. Intuitively, we expect an individual's expenditure to be directly related to their income, so it is reasonable to assume a "linear relationship" between these two quantities. The points in Figure, of course, do not all lie on a straight line; this would be our standard or model. The difference between the data and the model constitutes the residuals.

<img width="493" height="288" alt="image" src="https://github.com/user-attachments/assets/93cb3a92-c725-4a87-ad25-e8b6ec8a542e" />

### Datasets

A dataset is a collection of data, usually tabulated. Each element indicates several characteristics. Each column represents a particular variable. Each row corresponds to a specific member of the dataset. Each value is known as a datum.

## Part I Exploratory Data Analysis

## Data Summary

**Types of Variables**

Among qualitative variables, we can further distinguish between two types: nominal qualitative variables, for which there is no ordering in their possible realizations, and ordinal qualitative variables, for which there is an order in their results.

Similarly, quantitative variables can be classified dichotomously: (a) discrete quantitative variables, whose possible values ​​form a finite or enumerable set of numbers, and which often result from a count, such as the number of children (0, 1, 2, ...); (b) continuous quantitative variables, whose possible values ​​belong to a range of real numbers and which result from a measurement, such as the height and weight (or rather, mass) of an individual.

<img width="529" height="259" alt="image" src="https://github.com/user-attachments/assets/4d448269-39ef-4159-8dfb-8a6f8520a300" />

For each type of variable, there are appropriate techniques for summarizing information, hence the advantage of using an identification typology. However, we will examine which techniques used in one case can be adapted to others.

On qualitative variables. In some situations, numerical values ​​can be assigned to the various qualities or attributes (or even classes) of a qualitative variable and then the analysis can be carried out as if it were quantitative, as long as the procedure is interpretable.

**Frequency Distributions**

When studying a variable, the researcher's main interest is to understand its behavior, analyzing the occurrence of its possible realizations.

| Level of Education | frequency Nᵢ | Proportion fᵢ | Percentage 100*fᵢ |
|:---:|:---:|:---:|:---:|
| Elementary | 12 | 0.3333 | 33.33 |
| High School | 18 | .5000 | 50.00 |
| Higher Education | 6 | 031667 | 16.67 |
| Total | 36 | 1.0000 | 100.00 |

**Measurement Scales**

There are four measurement scales that can be considered:

**Frequency Distributions**

When studying a variable, the researcher's main interest is to understand its behavior, analyzing the occurrence of its possible realizations.

**Nominal Scale**

In this scale, we can only state whether one measurement is different from another, and it is used to categorize individuals in a population. An example is an individual's sex. For each category, we associate a different numeral (letter or number). For example, in the case of sex, we can associate the letters M (male) and F (female), or 1 (male) and 2 (female). We cannot perform arithmetic operations here, and an appropriate measure of position is the mode.

<img width="457" height="332" alt="image" src="https://github.com/user-attachments/assets/68eaa5f9-36bf-442a-9016-f5fd3011d74b" />

**Ordinal Scale**

Here, we can say that one measurement is different and greater than another. We have the previous situation, but the categories are ordered, and the order of the associated numerals orders the categories. For example, an individual's socioeconomic class can be low (1 or X), middle (2 or Y), and high (3 or Z). Order-preserving transformations do not alter the structure of an ordinal scale. In the example above, we can represent the categories by 1, 10, and 100, or A, L, and Z. Appropriate measures of position are the median and the mode.

<img width="457" height="332" alt="image" src="https://github.com/user-attachments/assets/05a5fa1f-1bb6-4b31-b329-8c907891fbd2" />

**Interval Scale**

In this scale, we can state that one measurement is equal or different, greater, and how much greater than another. We can quantify the difference between the categories of the ordinal scale. We need an arbitrary origin and a unit of measurement. For example, consider an individual's temperature on the Fahrenheit scale. The origin is 0°F and the unit is 1°F. Transformations that preserve the structure of this scale are of the type y = ax + b, a > 0. For example, the transformation y = 5/9 (x – 32) transforms Fahrenheit degrees into Celsius. For this scale, we can perform arithmetic operations, and the mean, median, and mode are appropriate measures of position.

<img width="457" height="332" alt="image" src="https://github.com/user-attachments/assets/2aded91f-2335-45c4-9fe1-8fa915280e66" />

**Ratio Scale**

Given two measurements on this scale, we can determine whether they are equal, or whether one is different, how much larger, and how many times the other. The difference with the interval scale is that there is now an absolute zero. An individual's height is an example of a measurement on this scale. If it is measured in centimeters (cm), 0 cm is the origin and 1 cm is the unit of measurement. An individual who is 190 cm is twice as tall as an individual who is 95 cm, and this relationship continues to hold if we use 1 m as the unit. In other words, the structure of the ratio scale is not altered by transformations of the form y = cx, c > 0. For example, y = x/100 transforms cm into m. The statistics appropriate for the interval scale are also appropriate for the ratio scale.

<img width="457" height="332" alt="image" src="https://github.com/user-attachments/assets/874d5763-b202-4a97-b0de-89eebab21e1b" />

**code**

```python
import pandas as pd
import plotly.express as px

# Sample data with more variety
data = {
    "Employee": ["A", "B", "C", "D", "E", "F", "G", "H"],
    "Department": ["HR", "IT", "Sales", "IT", "HR", "Finance", "Sales", "Finance"],   # Nominal
    "Satisfaction": ["Low", "Medium", "High", "Medium", "High", "Low", "Medium", "High"],  # Ordinal
    "Temperature_C": [22, 25, 28, 20, 24, 26, 23, 27],  # Interval
    "Salary": [3000, 4500, 5000, 4000, 5500, 3200, 4700, 6000],  # Ratio
    "Age": [25, 32, 41, 29, 35, 26, 38, 45],  # Ratio (extra example)
    "Work_Experience": [1, 5, 10, 3, 8, 2, 7, 15]  # Ratio (extra example)
}

df = pd.DataFrame(data)

# Convert Satisfaction to an ordered categorical type
satisfaction_order = ["Low", "Medium", "High"]
df["Satisfaction"] = pd.Categorical(df["Satisfaction"], categories=satisfaction_order, ordered=True)

print(df.dtypes)
print(df)

# --- Common Layout Settings ---
def apply_custom_layout(fig, title):
    fig.update_layout(
        title=dict(
            text=f'<b style="background: -webkit-linear-gradient(#B0F60F, #3DCE4F); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">{title}</b>',
            x=0.5,
            font=dict(size=22)
        ),
        plot_bgcolor="#000000",
        paper_bgcolor="#1A1A1D",
        font=dict(color="#FFFFFF"),
        xaxis=dict(showgrid=False),
        yaxis=dict(showgrid=False),
        showlegend=True
    )
    return fig

# Utility function to save charts
def save_chart(fig, name):
    fig.write_html(f"./html/{name}.html", include_plotlyjs="cdn", config={"displaylogo": False})
    fig.write_image(f"./img/{name}.png")

# Nominal: Count of employees by department
fig1 = px.histogram(df, x="Department")
fig1 = apply_custom_layout(fig1, "Nominal Scale: Department Distribution")
fig1.show(config={"displaylogo": False})
save_chart(fig1, "nominal_department_distribution")

# Ordinal: Average salary by satisfaction level
fig2 = px.bar(df.groupby("Satisfaction")["Salary"].mean().reset_index(),
              x="Satisfaction", y="Salary")
fig2 = apply_custom_layout(fig2, "Ordinal Scale: Average Salary by Satisfaction")
fig2.show(config={"displaylogo": False})
save_chart(fig2, "ordinal_salary_by_satisfaction")

# Interval: Temperature distribution
fig3 = px.scatter(df, x="Employee", y="Temperature_C", size="Salary", color="Department")
fig3 = apply_custom_layout(fig3, "Interval Scale: Temperature by Employee")
fig3.show(config={"displaylogo": False})
save_chart(fig3, "interval_temperature_by_employee")

# Ratio: Salary distribution
fig4 = px.box(df, x="Department", y="Salary", color="Department")
fig4 = apply_custom_layout(fig4, "Ratio Scale: Salary Distribution by Department")
fig4.show(config={"displaylogo": False})
save_chart(fig4, "ratio_salary_distribution")

# Extra Ratio Example: Age vs Work Experience
fig5 = px.scatter(df, x="Age", y="Work_Experience", size="Salary", color="Department")
fig5 = apply_custom_layout(fig5, "Ratio Scale: Age vs Work Experience")
fig5.show(config={"displaylogo": False})
save_chart(fig5, "ratio_age_vs_experience")

```

## Summary Measures

**Measures of  Position** _mean, median, and mode_

Typically, one of the following measures of central position (location) is used: mean, median, or mode.

The mode is defined as the most frequent occurrence of the set of observed values; the median is the occurrence that occupies the central position of the series of observations, when they are arranged in ascending order; and finally, the arithmetic mean is the sum of the observations divided by their number.
