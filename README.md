# Comparative Analysis of Book Adaptations on Netflix and Amazon Prime Video

## Project Overview

Streaming platforms such as Netflix and Amazon Prime Video increasingly rely on book-to-screen adaptations to attract audiences. However, adaptation success is influenced by multiple factors, including source material quality, genre, adaptation format, and audience reception.

This project presents a comparative analysis of book adaptations available on Netflix and Amazon Prime Video by integrating data from multiple sources, including Wikipedia, IMDb, and Goodreads. The study investigates adaptation quality, genre preferences, popularity, and the relationship between book ratings and screen adaptation ratings.

The final dataset consists of **248 confirmed book adaptations** released between **2015 and 2026**.


## Objectives

* Compare adaptation quality across Netflix and Amazon Prime Video.
* Analyze the relationship between Goodreads ratings and IMDb ratings.
* Examine genre preferences and their influence on audience reception.
* Compare the performance of movie and series adaptations.
* Investigate temporal trends in adaptation ratings.
* Explore the relationship between popularity and audience ratings.


## Dataset Description

The final integrated dataset contains the following attributes:

| Column           | Description                           |
| ---------------- | ------------------------------------- |
| Title            | Name of the adaptation                |
| Premiere         | Release date                          |
| Rated            | Content certification                 |
| imdb_rating      | IMDb audience rating                  |
| imdb_votes       | Number of IMDb votes                  |
| imdb_genre       | Genres associated with the adaptation |
| imdb_year        | Release year                          |
| imdb_type        | Movie or Series                       |
| platform         | Streaming platform                    |
| book_title       | Source book title                     |
| book_author      | Author of the source book             |
| goodreads_rating | Goodreads rating of the source book   |


## Data Collection Pipeline

### 1. Adaptation Dataset Collection

* Netflix and Amazon original titles were collected through web scraping from Wikipedia.
* IMDb metadata was retrieved using the OMDb API.
* Each title was manually verified to determine whether it was based on a book.
* Only confirmed book adaptations were retained for further analysis.

### 2. Goodreads Data Integration

* A Goodreads dataset obtained from Kaggle was used as the primary source.
* Extensive preprocessing was performed to standardize titles and author names.
* Exact and fuzzy matching techniques were applied to maximize successful matches.
* Unmatched books were manually verified and collected from Goodreads to ensure complete coverage.

### 3. Data Cleaning

* Invalid and excluded records were removed.
* Book titles were manually corrected where necessary.
* Unnecessary intermediate columns were dropped.
* Missing values and duplicate records were verified.
* The final cleaned dataset was prepared for exploratory data analysis.

## Repository Structure

```text
book_adaptations/
│
├── data/
│   ├── books/
│   │   ├── raw/
│   │   ├── processed/
│   │   └── final/
│   │
│   ├── movies/
│   │   ├── raw/
│   │   ├── processed/
│   │   └── final/
│   │
│   ├── series/
│   │   ├── raw/
│   │   ├── processed/
│   │   └── final/
│   │
│   └── final/
│       └── book_adaptations.csv
│
├── notebooks/
│   ├── 01_series_data_collection.ipynb
│   ├── 02_movies_data_collection.ipynb
│   ├── 03_book_data_collection.ipynb
│   ├── 04_data_cleaning.ipynb
│   └── 05_data_analysis.ipynb
│
├── visuals/
│   ├── correlation_heatmap.png
│   ├── genre_ratings.png
│   ├── goodreads_vs_imdb.png
│   ├── imdb_rating_distribution.png
│   ├── movies_vs_series.png
│   ├── platform_comparison.png
│   ├── platform_genre_comparison.png
│   ├── top_popular_adaptations.png
│   └── top_rated_adaptations.png
│
└── README.md
```


## Methodology

The project was completed using the following workflow:

1. Web scraped Netflix and Amazon original titles from Wikipedia.
2. Retrieved IMDb metadata using the OMDb API.
3. Manually verified whether each title was adapted from a book.
4. Integrated Goodreads ratings using a combination of automated matching and manual verification.
5. Performed extensive data cleaning and preprocessing.
6. Conducted exploratory data analysis to identify patterns, trends, and relationships.
7. Generated visualizations to communicate findings effectively.


## Key Findings

* Most adaptations receive moderate IMDb ratings, with the majority clustered between ratings of 6 and 7.
* Streaming platforms tend to adapt books that have already received positive reader reception, with Goodreads ratings concentrated around 4.0.
* Goodreads ratings exhibit only a moderate relationship with adaptation ratings, suggesting that highly rated books do not always result in successful adaptations.
* Drama is the dominant genre across both platforms, while historical and biographical adaptations tend to achieve the highest audience ratings.
* Series adaptations consistently outperform movie adaptations, indicating that episodic storytelling may be better suited for adapting literary works.
* Amazon and Netflix exhibit remarkably similar adaptation quality despite differences in catalog size.
* Popular adaptations tend to receive higher audience ratings, although popularity alone does not guarantee critical success.

## Sample Visualizations

### IMDb Rating Distribution

<img width="2074" height="1407" alt="imdb_rating_distribution" src="https://github.com/user-attachments/assets/c91fc606-111e-44b4-b735-a0d0e09539d1" />

### Goodreads Rating vs IMDb Rating

<img width="2034" height="1638" alt="goodreads_vs_imdb" src="https://github.com/user-attachments/assets/ab323ccf-3e0d-4270-a7e6-f79bbf886fa0" />


### Movies vs Series Comparison

<img width="1710" height="1332" alt="movies_vs_series" src="https://github.com/user-attachments/assets/748cfbe3-6fc5-4b9f-baa7-58e89f860b43" />



### Platform Comparison

<img width="1710" height="1332" alt="platform_comparison" src="https://github.com/user-attachments/assets/2a77fab8-eb70-4396-8072-b79c4df85727" />




### Genre Distribution Across Platforms

<img width="2970" height="1765" alt="platform_genre_comparison" src="https://github.com/user-attachments/assets/48b72844-fb9c-4069-aebd-b26dc6efad4d" />



### Correlation Heatmap

<img width="2023" height="1350" alt="correlation_heatmap" src="https://github.com/user-attachments/assets/c17add09-fe18-4fb9-9f69-c0ae9a3368ec" />




## Limitations

* The dataset contains substantially more Netflix adaptations than Amazon adaptations because Netflix data was collected from multiple Wikipedia pages, whereas Amazon data was obtained from a single Wikipedia source.
* Data collection relied primarily on publicly available Wikipedia pages; therefore, some adaptations may be missing.
* Goodreads and IMDb ratings are user-generated and may reflect subjective preferences and demographic biases.
* Certain years, genres, and genre combinations contain relatively few observations.
* Correlation analyses identify associations but do not establish causal relationships.


## Future Work

Potential extensions of this project include:

* Building machine learning models to predict adaptation success.
* Incorporating additional streaming platforms such as Disney+, Hulu, and Apple TV+.
* Expanding the dataset to include more adaptation metadata, such as budgets, runtime, and production studios.
* Investigating sentiment analysis using audience reviews.
* Performing network analysis between authors, genres, and adaptation performance.


## Tools and Technologies

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Requests**
* **BeautifulSoup**
* **RapidFuzz**
* **Jupyter Notebook**
* **OMDb API**


## Author

**Devashree Kinjale**

If you found this project interesting, feel free to explore the notebooks and visualizations included in this repository.
