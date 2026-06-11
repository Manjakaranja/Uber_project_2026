# Uber Pickups Clustering – New York City

## Project Overview

This project explores Uber pickup activity in New York City using unsupervised machine learning techniques.

The objective is to identify recurring pickup hot zones and determine where drivers are most likely to find passengers. To answer this question, pickup locations were grouped into clusters and visualized on interactive maps.

Two clustering algorithms were applied and compared:

* K-Means
* DBSCAN

---

## Academic Context

This project was completed as part of the **Concepteur Développeur en Science des Données (CDSD)** certification program.

It belongs to **Bloc 3 — Analyse prédictive de données structurées par l'intelligence artificielle**, which focuses on the application of Machine Learning methods to structured datasets.

As part of the Fullstack Data Science curriculum, students are required to complete several machine learning projects, including:

* Walmart Sales
* Conversion Rate Challenge
* Uber Pickups

The purpose of this project is to use clustering techniques to identify Uber pickup hot zones in New York City and determine where drivers are most likely to find passengers.

---

## Objectives

The main objectives of this project are:

* Identify geographic Uber pickup hot zones.
* Visualize demand distribution across New York City.
* Analyze whether pickup zones change throughout the week.
* Compare K-Means and DBSCAN for spatial clustering.
* Provide recommendations for driver positioning.

---

## Dataset

The dataset contains Uber pickup records collected in New York City between 2014 and 2015.

Each record includes:

* Pickup date and time
* Latitude
* Longitude

Only pickup locations were used for the clustering analysis.

---

## Methodology

### Data Preparation

The monthly datasets were merged into a single dataframe and cleaned prior to analysis.

Pickup timestamps were converted into datetime format and used to create a weekday variable. A sample of observations was retained to reduce computation time while preserving the overall spatial distribution of pickups.

### K-Means Clustering

K-Means clustering was applied to latitude and longitude coordinates.

The number of clusters was evaluated using the Elbow Method and the Silhouette Score. Based on the combined interpretation of these metrics and the resulting maps, **K = 3** was selected.

### DBSCAN Clustering

DBSCAN was applied to the same geographic coordinates.

Unlike K-Means, DBSCAN does not require a predefined number of clusters and can identify dense pickup areas while treating isolated observations as noise.

This makes it particularly suitable for geographic data where demand zones do not follow simple geometric shapes.

---

## Results

The analysis revealed three major demand areas within New York City.

The highest concentration of pickups is located in Manhattan, with additional demand zones extending into Brooklyn and Queens. Smaller clusters are also present in more peripheral locations.

The weekday visualizations show that the location of the main pickup zones remains largely unchanged throughout the week. Although pickup intensity varies slightly from one day to another, the same areas consistently appear as the main demand hubs.

Both K-Means and DBSCAN identified similar high-demand areas across the city. However, DBSCAN produced more realistic clusters by separating dense pickup areas from isolated observations.

---

## Repository Structure

```text
.
├── data
│   ├── image
│   │   ├── Cluster_KMeans.html
│   │   └── Cluster_dbscan.html
│   └── raw
│       └── Uber datasets
├── notebook
│   └── Uber_Project.ipynb
├── requirements.txt
└── README.md
```

---

## Installation

Clone the repository:

```bash
git clone [<repository_url>](https://github.com/Manjakaranja/Uber_project_2026)
cd Uber_project_2026
```

Create and activate a virtual environment:

```bash
python -m venv env_uber
source env_uber/bin/activate
```

Install the required packages:

```bash
pip install -r requirements.txt
```

---

## Running the Project

Launch Jupyter Notebook:

```bash
jupyter notebook notebook/Uber_Project.ipynb
```

The notebook contains the complete workflow, including:

* Data preparation
* Clustering analysis
* Interactive visualizations
* Interpretation of results

Interactive maps generated during the analysis are available in:

```text
data/image/
```

---

## Conclusion

This analysis shows that Uber pickup activity in New York City is concentrated in a limited number of recurring geographic areas.

Manhattan is the main demand zone, while Brooklyn and Queens represent important secondary pickup areas. These locations remain stable throughout the week, suggesting that pickup demand is driven more by geography than by the specific day of the week.

For drivers, these results indicate that positioning near the major Manhattan demand corridor is likely to provide the greatest number of pickup opportunities. Brooklyn and Queens may also offer good opportunities during periods of increased demand.

Overall, DBSCAN gave the most useful results because it identified the main demand hubs while ignoring isolated pickups.

```
```
