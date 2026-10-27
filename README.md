\# Amazon Prime Video Catalogue Dashboard



I built this Tableau project to explore the Amazon Prime Video catalogue. I cleaned and organised the data using Python and Pandas, then created a one-page Tableau dashboard to analyse movies and TV shows, genres, production countries, release trends, actors, directors, and IMDb ratings.







\*\*Live Dashboard:\*\*  \


\---



\## Questions I Wanted to Answer



1\. What is the catalogue made of, and how many movies and TV shows are included?

2\. Which genres and production countries are most represented?

3\. How has the number of releases changed over the years?

4\. Which actors and directors are credited on the most titles?

5\. What is the average IMDb score of titles in the catalogue?



\## Key Findings



\- The cleaned catalogue contains \*\*9,868 titles\*\*.

\- It includes \*\*8,511 movies (approximately 86.3%)\*\* and \*\*1,357 TV shows (approximately 13.7%)\*\*.

\- Drama is the leading genre in the analysis, followed by Comedy, Thriller, Action, and Romance.

\- The average IMDb score is approximately \*\*5.98 out of 10\*\*.

\- The number of releases increases in more recent years, with the peak year to be confirmed from the dashboard.

\- Production is concentrated in several countries, with the leading country to be confirmed from the dashboard.

\- Joseph Kane, Sam Newfield, and Jay Chapman are among the directors with the most titles in this analysis.



\*Note: These findings describe the dataset used in this project and do not necessarily represent the current Amazon Prime Video catalogue.\*



\## Dataset



The project uses Amazon Prime Video titles and credits data.



The cleaned Excel workbook is `data/amazon\_prime\_clean.xlsx`. It contains four worksheets:



| Worksheet         | What it contains                                                                                   |

| ----------------- | -------------------------------------------------------------------------------------------------- |

| `titles\_clean`    | Title-level information, including content type, release year, runtime, certification, and ratings |

| `title\_genres`    | Title-to-genre associations                                                                        |

| `title\_countries` | Title-to-country associations                                                                      |

| `credits\_clean`   | Actors, directors, and other available credit information                                          |



\## How I Prepared the Data



I used Python, Pandas, and Google Colab to clean and prepare the data for analysis. The notebook is available in the `notebooks` folder.



The data-preparation process included:



\- Removing duplicate records from the titles and credits data.

\- Reviewing missing values and handling missing age certifications by assigning `Not Rated`.

\- Preparing separate genre and country tables by splitting multi-value fields into individual records.

\- Creating additional analysis fields, including release decade, runtime band, rating gap, and IMDb rating band.

\- Checking title identifiers to support accurate counting and relationships in Tableau.



The cleaned tables were saved together in one Excel workbook, `data/amazon\_prime\_clean.xlsx`.



\## Data Model in Tableau



The `titles\_clean` table serves as the main table. The genre, country, and credits tables are related to it using the title `Id`.



Using relationships and distinct counts of `Id` helps avoid counting the same title multiple times when it has multiple genres, countries, or credited people.



\## What Is on the Dashboard?



| Dashboard section       | What it shows                                          | Visualisation        |

| ----------------------- | ------------------------------------------------------ | -------------------- |

| KPI cards               | Total titles, movies, TV shows, and average IMDb score | KPI cards            |

| Top 10 genres           | Most represented genres by title count                 | Horizontal bar chart |

| Movies vs TV shows      | Distribution of content types                          | Pie chart            |

| Production countries    | Geographic distribution of titles                      | Filled map           |

| Titles released by year | Release trends over time, split by content type        | Area chart           |

| Top 10 actors           | Actors credited on the most titles                     | Horizontal bar chart |

| Top 10 directors        | Directors credited on the most titles                  | Horizontal bar chart |



\### Filters and Calculated Fields



The dashboard includes a content-type filter and a release-year range filter.



The Movies and TV Shows KPI cards use their own fixed content-type filters so they can display their respective totals independently of the shared content-type filter.



The Actor Rank and Director Rank calculated fields help identify the leading people by distinct title count, with the role separated for each chart.



\*These features should be tested in the published dashboard before submission.\*



\## Problems I Encountered and How I Addressed Them



| Problem                                                | Cause                                                            | Approach                                             |

| ------------------------------------------------------ | ---------------------------------------------------------------- | ---------------------------------------------------- |

| The top directors chart showed too few directors       | A Top N filter was applied before separating credit roles        | Used a rank calculation for the director chart       |

| The Movies and TV Shows cards displayed the same total | The dashboard-wide type filter affected both KPI cards           | Gave each KPI card its own fixed content-type filter |

| Title counts were too high                             | Multiple genres, countries, and credits can repeat title records | Used relationships and distinct counts of title `Id` |



\## Limitations



\- The analysis measures catalogue titles, not actual viewing behaviour.

\- The results depend on the dataset and its coverage.

\- IMDb scores indicate audience ratings, not a definitive measure of content quality.

\- The catalogue may change over time, so the results should not be interpreted as a live inventory.



\## Repository Structure



```text

prime-video-tableau-dashboard/

├── README.md

├── .gitignore

├── dashboard/

│   ├── Amazon\_Prime\_Video\_Dashboard.twbx

│   └── dashboard\_preview.png

├── notebooks/

│   └── Amazon\_Prime\_Video\_Data\_Cleaning.ipynb

└── data/

&#x20;   └── amazon\_prime\_clean.xlsx

```



\## How to Explore the Project



1\. View the dashboard preview image at `dashboard/dashboard\_preview.png`.

2\. Open `dashboard/Amazon\_Prime\_Video\_Dashboard.twbx` in Tableau Desktop or Tableau Public.

3\. Review the data-cleaning workflow in `notebooks/Amazon\_Prime\_Video\_Data\_Cleaning.ipynb`.

4\. Explore the prepared tables in `data/amazon\_prime\_clean.xlsx`.



The packaged Tableau workbook is intended to include the data needed to open the dashboard. The separate Excel workbook is provided for data inspection and project documentation.



\## Tools and Technologies



\- Python

\- Pandas

\- Google Colab

\- Microsoft Excel

\- Tableau

\- Git and GitHub



\## Skills Demonstrated



\- Data cleaning and preprocessing

\- Exploratory data analysis

\- Data modelling and relationships

\- Calculated fields and ranking

\- Interactive dashboard design

\- Data visualisation

\- Analytical storytelling

\- Project documentation



\## Author



\*\*Vaibhav Deshmukh\*\*



GitHub: \[vaibhavd8080](https://github.com/vaibhavd8080)



Email: \[vaibhavd8080](https://github.com/vaibhavd8080)@gmail.com



\---



\*Created as a data analytics and visualisation portfolio project.\*



