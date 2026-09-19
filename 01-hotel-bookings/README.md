# Hotel Booking Cancellations — Exploratory Data Analysis

An exploratory analysis of hotel booking behavior, examining which booking, customer, and 
operational factors are associated with cancellations.

This is a **descriptive, exploratory** project — the goal is to understand patterns and 
compare customer segments, not to build a predictive model.

## Dataset

**Source:** [Hotel Booking Demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) 
(Antonio, Almeida & Nunes, 2019), via Kaggle

The dataset contains 119,390 bookings (87,396 after removing duplicates) across 32 columns, 
covering a City Hotel and a Resort Hotel in Portugal, with arrivals between 2015 and 2017.

## Objectives

This project explores eight main questions:

- What's the overall cancellation rate, and does it differ by hotel type?
- Does party size change the cancellation rate?
- Does traveling with kids affect the cancellation rate?
- Is lead time (how far ahead people book) linked to cancellation?
- Does length of stay matter?
- Are new guests more likely to cancel than returning guests?
- Do people with a history of canceling keep canceling?
- Does time spent on the waiting list affect cancellation?

## Key Findings

- The overall cancellation rate is ~27.5%, with City Hotel (30.0%) canceling more often than 
  Resort Hotel (23.5%).
- Guest history is the strongest signal found: new customers cancel at 28.3% vs. 7.6% for 
  returning customers — the largest gap in the analysis. This lines up with a related 
  pattern: once a guest has even one completed (non-canceled) stay, their cancellation rate 
  drops to and stays around ~5%.
- Party size and traveling with kids both increase cancellation risk, which ran counter to 
  the initial assumption that larger or family bookings would be more "locked in."
- Lead time shows a steady upward trend — the further in advance a booking is made, the more 
  likely it is to be canceled — though the reliability of that trend weakens sharply past 
  ~300 days due to small sample sizes.
- Several other splits (previous cancellation count, length of stay, waiting list days) 
  showed dramatic-looking percentages, but many came from bins with only a few dozen 
  bookings or fewer, so they're flagged as low-confidence rather than treated as solid 
  findings.

Full reasoning, caveats, and sample sizes for each finding are in the notebook itself.

## Data Cleaning Notes

The raw dataset has no booking ID column. `duplicated()` flags 31,994 fully identical rows 
(~27% of the dataset) — matching across all 32 columns, not just a few. Given the size of 
that match, these are treated as genuine duplicate records and dropped, though this is an 
assumption rather than a certainty (it's possible a small fraction are coincidental matches 
rather than true duplicates). This is also called out inline in the notebook.

## Tools Used

- `pandas` / `numpy` — data cleaning and aggregation
- `matplotlib` / `seaborn` — visualization

## Structure
The full analysis, including all charts and written observations, is available in 
`EDA.ipynb`.