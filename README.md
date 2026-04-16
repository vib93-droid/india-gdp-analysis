# India GDP Growth Analysis (1960–2022)

Unsupervised and supervised machine learning applied to 63 years of World Bank GDP data to identify and classify India's historical growth phases.

---

## Key Finding

The model's most counterintuitive result: **India's fastest GDP growth rates occurred when its economy was at its smallest.** The "High GDP" cluster — which captures India's largest absolute economy — coincides with the COVID-19 contraction years, where growth turned sharply negative. This pattern was discovered unsupervised; the algorithm was given no historical labels.

---

## Methodology

| Step | Technique | Purpose |
|------|-----------|---------|
| Clustering | K-Means (k=3) | Discover growth phases without labels |
| Classification | K-Nearest Neighbours | Predict phase from GDP + growth rate |
| Evaluation | Accuracy, Precision, Recall, F1 | Validate classification quality |

**Result:** 93.75% KNN classification accuracy across three phases.

---

## The Three Phases

| Cluster | Era (Approx.) | Characteristics |
|---------|--------------|-----------------|
| Low Growth (Red) | 1960–~2000 | Small economy, but growth rates of 6–10% — the licence raj and early liberalisation period |
| Moderate Growth (Orange) | ~2000–2019 | Rapid GDP scaling, growth moderating to 5–8% — the services and globalisation boom |
| High Growth (Green) | Post-2019 | Highest absolute GDP, but anomalous negative growth — COVID-era contraction |

> Note: "High Growth" refers to the highest GDP *level*, not growth rate — an intentional naming tension that reflects the data's story.

---

## Visualisations

**K-Means Clusters — GDP vs Growth Rate**

![Cluster Scatter](visuals/kmeans_scatter.png)

**Growth Phases Over Time (1961–2022)**

![Timeline](visuals/growth_timeline.png)

---

## Data Source

[World Bank — GDP (current US$), India](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD?locations=IN)

63 annual observations (1960–2022). Features used: GDP (USD Billion), GDP Growth Rate (%).

---

## How to Run

```bash
git clone https://github.com/vib93-droid/india-gdp-analysis
cd india-gdp-analysis
pip install -r requirements.txt
jupyter notebook india_gdp_analysis.ipynb
```

---

## Skills Demonstrated

- Unsupervised learning (K-Means clustering)
- Supervised classification (KNN)
- Model evaluation with multi-metric framework
- Economic interpretation of ML outputs
- Data visualisation with matplotlib
