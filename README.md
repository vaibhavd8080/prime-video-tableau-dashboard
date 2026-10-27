# Amazon Prime Video Catalogue Dashboard

An interactive data visualization project exploring the Amazon Prime Video catalogue using **Tableau, Python, Pandas, and Excel**.

## Dashboard Preview

![Amazon Prime Video Dashboard](dashboard/dashboard_preview.png)

**Live Interactive Dashboard:** [View on Tableau Public](https://public.tableau.com/app/profile/vaibhav.deshmukh3072/viz/Amazon_Prime_Video_DashboardTablaeu/Dashboard1?publish=yes)

---

## Project Overview

This project explores the Amazon Prime Video catalogue through data cleaning, exploratory analysis, data modelling, and interactive dashboard development.

The dashboard analyses movies and TV shows, genres, production countries, release trends, actors, directors, and IMDb ratings.

## Questions I Wanted to Answer

1. What is the catalogue made of, and how many movies and TV shows are included?
2. Which genres and production countries are most represented?
3. How has the number of releases changed over the years?
4. Which actors and directors are credited on the most titles?
5. What is the average IMDb score of titles in the catalogue?

## Key Findings

- The cleaned catalogue contains **9,868 titles**.
- It includes **8,511 movies (approximately 86.3%)** and **1,357 TV shows (approximately 13.7%)**.
- Drama is the leading genre, followed by Comedy, Thriller, Action, and Romance.
- The average IMDb score is approximately **5.98 out of 10**.
- The number of releases increases in more recent years. The peak year should be confirmed from the dashboard.
- Production is concentrated in several countries. The leading country should be confirmed from the dashboard.
- Joseph Kane, Sam Newfield, and Jay Chapman are among the directors with the most titles in this analysis.

*Note: These findings describe the dataset used in this project and do not necessarily represent the current Amazon Prime Video catalogue.*

## Dataset

The project uses Amazon Prime Video titles and credits data.

The cleaned Excel workbook is located at `data/amazon_prime_clean.xlsx` and contains four worksheets:

| Worksheet | Description |
|---|---|
| `titles_clean` | Title-level information, including content type, release year, runtime, certification, and ratings |
| `title_genres` | Title-to-genre associations |
| `title_countries` | Title-to-country associations |
| `credits_clean` | Actors, directors, and other available credit information |

## Data Cleaning and Preparation

I used **Python, Pandas, and Google Colab** to clean and prepare the data for analysis. The notebook is available in the `notebooks` folder.

The data-preparation process included:

- Removing duplicate records from the titles and credits data.
- Reviewing missing values and handling missing age certifications by assigning `Not Rated`.
- Separating multi-value genre and country fields into individual records.
- Creating additional analysis fields, including release decade, runtime band, rating gap, and IMDb rating band.
- Checking title identifiers to support accurate counting and relationships in Tableau.

The cleaned tables were saved together in `data/amazon_prime_clean.xlsx`.

## Data Model in Tableau

The `titles_clean` table serves as the main table. The genre, country, and credits tables are related to it using the title `Id`.

Using relationships and distinct counts of `Id` helps avoid counting the same title multiple times when it has multiple genres, countries, or credited people.

## Dashboard Features

| Dashboard Section | What It Shows | Visualization |
|---|---|---|
| KPI cards | Total titles, movies, TV shows, and average IMDb score | KPI cards |
| Top 10 genres | Most represented genres by title count | Horizontal bar chart |
| Movies vs. TV shows | Distribution of content types | Pie chart |
| Production countries | Geographic distribution of titles | Filled map |
| Titles released by year | Release trends over time, split by content type | Area chart |
| Top 10 actors | Actors credited on the most titles | Horizontal bar chart |
| Top 10 directors | Directors credited on the most titles | Horizontal bar chart |

### Filters and Calculated Fields

The dashboard includes a content-type filter and a release-year range filter.

The Movies and TV Shows KPI cards use their own fixed content-type filters so that each displays its respective total independently of the shared content-type filter.

The Actor Rank and Director Rank calculated fields help identify leading people by distinct title count, with the role separated for each chart.

*These interactive features should be tested in the published dashboard before submission.*

## Problems Encountered and Solutions

| Problem | Cause | Approach |
|---|---|---|
| The top directors chart showed too few directors | A Top N filter was applied before separating credit roles | Used a rank calculation for the director chart |
| The Movies and TV Shows cards displayed the same total | The dashboard-wide type filter affected both KPI cards | Gave each KPI card its own fixed content-type filter |
| Title counts were too high | Multiple genres, countries, and credits can repeat title records | Used relationships and distinct counts of title `Id` |

## Limitations

- The analysis measures catalogue titles, not actual viewing behaviour.
- Results depend on the dataset and its coverage.
- IMDb scores indicate audience ratings, not a definitive measure of content quality.
- The catalogue may change over time, so the results should not be interpreted as a live inventory.

## Repository Structure

```text
prime-video-tableau-dashboard/
├── README.md
├── .gitignore
├── dashboard/
│   ├── Amazon_Prime_Video_Dashboard.twbx
│   └── dashboard_preview.png
├── notebooks/
│   └── Amazon_Prime_Video_Data_Cleaning.ipynb
└── data/
    └── amazon_prime_clean.xlsx
```

## How to Explore the Project

1. View the dashboard preview image at `dashboard/dashboard_preview.png`.
2. Open `dashboard/Amazon_Prime_Video_Dashboard.twbx` in Tableau Desktop or Tableau Public.
3. Review the data-cleaning workflow in `notebooks/Amazon_Prime_Video_Data_Cleaning.ipynb`.
4. Explore the prepared tables in `data/amazon_prime_clean.xlsx`.

The packaged Tableau workbook is intended to include the data needed to open the dashboard. The separate Excel workbook is provided for data inspection and project documentation.

## Tools and Technologies

- Python
- Pandas
- Google Colab
- Microsoft Excel
- Tableau
- Git and GitHub

## Skills Demonstrated

- Data cleaning and preprocessing
- Exploratory data analysis
- Data modelling and relationships
- Calculated fields and ranking
- Interactive dashboard design
- Data visualization
- Analytical storytelling
- Project documentation

## Author

**Vaibhav Deshmukh**

- **GitHub:** [vaibhavd8080](https://github.com/vaibhavd8080)
- **Email:** [vaibhavd8080@gmail.com](mailto:vaibhavd8080@gmail.com)

---

*Created as a data analytics and visualization portfolio project.*



