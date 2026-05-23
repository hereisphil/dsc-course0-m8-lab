# Aviation Accident Analysis

## 👉 **GitHub Repository**: <https://github.com/hereisphil/dsc-course0-m8-lab>

A data-driven evaluation of aircraft crashworthiness and human injury risk patterns across general and commercial aviation. This project engineers safety metrics from historical NTSB flight data to isolate elite manufacturers and identify structural safety differences between **Small** and **Larger** airframes.

> **Student**: Phillip Cantu<br />**Date**: Saturday, May 23, 2026<br />**LinkedIn**: <https://linkedin.com/in/phillipcantu>

---

## 📊 Core Safety Insights & Findings

### 1. Small vs. Larger Aircraft Risk Profiles

Our analysis revealed two completely different safety patterns depending on the scale of the aircraft:

- **Small Aircraft (Continuous Risk Gradient):** Data distributions show a right-skewed smooth curve. While most incidents result in zero severe injuries, small aircraft exhibit a continuous tail of injury rates extending from `0.0` all the way to `1.0`. Because general aviation involves diverse environments (e.g., fields, unpaved runways), accidents present a sliding scale of risk rather than an all-or-nothing outcome.
- **Larger Aircraft (Binary Extremes):** Commercial and large-tier airframes display a strict "all-or-nothing" binary split. Accident data points cluster almost exclusively at the absolute polar boundaries: `0.0` (zero severe injuries) or `1.0` (catastrophic outcomes), with an empty void in the middle. Large aircraft are heavily engineered to completely absorb standard incidents with zero trauma, but crossing those extreme structural boundaries usually results in total loss events.

### 2. Hull Destruction Trends

- **The 0% Club:** Major commercial manufacturers (including **Airbus**, **Boeing**, and **Cessna's large-tier lines**) achieve a flawless **0.0% hull destruction rate** within the qualified high-sample dataset, emphasizing the success of modern aviation redundancy.
- **Legacy Airframe Vulnerability:** Older structural groups like legacy **Douglas** and **Lockheed** configurations show hull destruction rates approaching **25%**, showcasing the generational leap forward in modern aerospace materials.

---

## 🏆 Key Manufacturer Recommendations

Based on the intersection of low hull destruction and minimized severe injury profiles, the data highlights these top performers:

- **For Commercial/Large Scale Operations:** **Airbus** represents the industry benchmark. They maintain a perfect 0% hull destruction rate, and their accident data maps tighter to the safest `0.0` injury point than their direct commercial peers.
- **For General/Small Scale Operations:** **Grumman-Schweizer** excels across general aviation metrics, holding a hull destruction rate under 2% alongside the lowest overall average severe injury fraction.

---

## 🛠️ Project Structure & Workflow

The repository contains the complete pipeline divided into data preprocessing and analysis stages:

```text
├── data/
│   ├── AviationData.csv            # Raw historical accident data
│   └── cleaned_aviation_data.csv   # Post-vetted dataset (Filtered post-1983)
├── Aviation_Accidents_Cleaning.ipynb # Script handling encodings, missing values, & datetimes
├── Aviation_Accidents_Data_Analysis.ipynb # Notebook containing statistical math and Seaborn plots
├── README.md                       # Executive summary
└── LICENSE

```

### Engineered Metrics Utilized

1. **Severe Injury Fraction:** Calculated per incident to capture the true ratio of severe trauma relative to minor outcomes:

$$\text{Injury Fraction} = \frac{\text{Fatal} + \text{Serious}}{\text{Fatal} + \text{Serious} + \text{Minor}}$$

2. **Destruction Rate:** Evaluated using boolean vector math across the `is_destroyed` markers to measure macro-level frame durability by manufacturer.

---

## 📈 Visualizations Included in Notebooks

The `Aviation_Accidents_Data_Analysis.ipynb` notebook renders the following data visualizations:

- **Side-by-Side Horizontal Bar Charts:** Tracking the top 15 makes with the lowest mean severe injuries and hull destruction rates.
- **Seaborn Strip Plots:** Displaying the stark binary clustering behavior of larger commercial makes.
- **Seaborn Violin Plots:** Capturing the continuous distribution shape and medians of safety-vetted general aviation small makes.

_Note: All aggregated models were filtered to ensure a minimum sample size of $n \ge 10$ incidents per group to ensure high statistical reliability._
