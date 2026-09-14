# Hotel Booking Cancellations — EDA

An exploratory analysis of hotel booking behavior, looking at which booking, customer, and operational factors are associated with cancellations.

This is a **descriptive, exploratory** project — the goal is to understand patterns and compare customer segments, not to build a predictive model.

## Dataset

- **Source:** [Hotel Booking Demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) (Antonio, Almeida & Nunes, 2019), via Kaggle
- **Size:** 119,390 bookings (87,396 after removing duplicates), 32 columns
- **Scope:** Bookings for a City Hotel and a Resort Hotel in Portugal, arriving between 2015 and 2017

## Objective

Examine hotel booking behavior and identify which factors are associated with cancellation, without attempting to predict it.

## Research questions

1. What's the overall cancellation rate, and does it differ by hotel type?
2. Does party size change the cancellation rate?
3. Does traveling with kids affect the cancellation rate?
4. Is lead time (how far ahead people book) linked to cancellation?
5. Does length of stay matter?
6. Are new guests more likely to cancel than returning guests?
7. Do people with a history of canceling keep canceling?
8. Does time spent on the waiting list affect cancellation?

## Key findings

- **Overall cancellation rate is ~27.5%**, with City Hotel (30.0%) canceling more often than Resort Hotel (23.5%).
- **Guest history is the strongest signal found:** new customers cancel at 28.3% vs. 7.6% for returning customers — the largest gap in the analysis. This lines up with a related pattern: once a guest has even one completed (non-canceled) stay, their cancellation rate drops to and stays around ~5%.
- **Party size and traveling with kids both increase cancellation risk**, which ran counter to my initial assumption that larger or family bookings would be more "locked in."
- **Lead time shows a steady upward trend** — the further in advance a booking is made, the more likely it is to be canceled — though the reliability of that trend weakens sharply past ~300 days due to small sample sizes.
- Several other splits (previous cancellation count, length of stay, waiting list days) showed dramatic-looking percentages, but many came from bins with only a few dozen bookings or fewer, so they're flagged as low-confidence rather than treated as solid findings.

Full reasoning, caveats, and sample sizes for each finding are in the notebook itself.

## A note on data cleaning

The raw dataset has no booking ID column. `duplicated()` flags 31,994 fully identical rows (~27% of the dataset) — matching across all 32 columns, not just a few. Given the size of that match, I'm treating them as genuine duplicate records and dropping them, but this is an assumption rather than a certainty (it's possible a small fraction are coincidental matches rather than true duplicates). This is called out inline in the notebook as well.

## Structure

```
hotel-booking-cancellations/
├── README.md          <- this file
├── EDA.ipynb           <- the analysis

```

## How to run

From the repo root, with dependencies installed (see the main [requirements.txt](../requirements.txt)):

```bash
jupyter notebook EDA.ipynb
```
