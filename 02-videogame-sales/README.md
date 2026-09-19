# Video Game Sales — Exploratory Data Analysis

An exploratory data analysis of global video game sales, examining how publishers, genres, 
platforms, and individual titles perform across different regional markets.

## Dataset

**Source:** [Video Game Sales](https://www.kaggle.com/datasets/gregorut/videogamesales) (Kaggle)

The dataset contains 16,598 games with sales figures (in millions of units) broken down by 
region — North America, Europe, Japan, and the rest of the world — along with each game's 
platform, genre, publisher, and release year.

## Objectives

This project explores four main questions:

- **Publishers** — Who are the top publishers globally and by region, and how does their 
  popularity vary across markets?
- **Genres** — Which genres are most popular globally and by region?
- **Platforms** — Which platforms perform best overall, and how does that differ by region?
- **Games** — Which individual titles are the best-sellers globally and by region, and what 
  does that reveal about regional taste?

A fifth section examines how strongly regional sales figures correlate with each other, to 
quantitatively test whether regions actually share similar taste or diverge from one another.

## Key Findings

- The market is highly concentrated: just three publishers (Nintendo, EA, and Activision) 
  account for nearly 58% of all global unit sales.
- North America and Europe behave almost like a single combined market — similar publisher, 
  genre, and platform preferences, with a 0.77 sales correlation between the two.
- Japan is a clear outlier. It shows strong domestic loyalty across publishers, platforms, 
  and genres (favoring Role-Playing games well above the global average), and correlates 
  weakly with every other region.
- Sony's success is concentrated in hardware rather than publishing — it dominates the 
  platform charts but ranks only 4th among publishers — while Nintendo dominates both.
- "Other" regions (Latin America, Australia, etc.) lean toward Sony hardware and mature, 
  open-world titles, and show a notable appetite for football/soccer games.

## Data Cleaning Notes

- 58 missing `Publisher` values were filled with `"Unknown"`.
- The `Year` column was dropped entirely. It records each game's *release* year, while sales 
  figures represent *cumulative lifetime sales* recorded at the time of data collection — 
  meaning a game released years ago but replayed recently would still have all of its sales 
  attributed to its original release year. This makes any year-over-year trend analysis 
  unreliable, so time-based analysis was intentionally excluded from this project.
- `Rank` was recomputed from `Global_Sales` after cleaning to ensure consistency.

## Tools Used

- `pandas` / `numpy` — data cleaning and aggregation
- `matplotlib` / `seaborn` — visualization

## Structure

The full analysis, including all charts and written observations, is available in 
`EDA.ipynb`.