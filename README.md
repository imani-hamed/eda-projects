# Basic-EDA

A collection of exploratory data analysis (EDA) projects, each built on a hand-picked, beginner-friendly dataset.

## Why this repo exists

When you're starting out with data analysis, the hardest part often isn't the analysis itself — it's finding a dataset that's actually good to practice on. A lot of "starter" datasets are either too clean to teach you anything (no missing values, no weird distributions, no ambiguity) or too messy to get through as a first project.

This repo is my attempt to fix that for other people learning EDA: a running list of datasets I've vetted and worked through myself, each with a full notebook of research questions, charts, and observations, so you can see one way to approach it — or just do your own version.

If you're learning EDA, feel free to use these datasets, fork the notebooks, or just read through the analysis to see the kind of questions worth asking.

**If you have opinions on the dataset choices, the analysis, or datasets you think belong here — please open an issue or a discussion.** This repo is as much about curating a good list as it is about the analysis itself, and outside opinions make that list better.

## Repo structure

```
Basic-EDA/
├── README.md                 <- you are here
├── requirements.txt          <- shared dependencies for all projects
├── 01-hotel-bookings/
│   ├── README.md              <- project-specific writeup
|   └── EDA.ipynb 
├── 02-.../
│   ├── README.md
│   └── EDA.ipynb
└── ...
```

Each project folder is self-contained: its own README with the dataset, objective, questions, and findings, plus the notebook itself.

## Projects

| Project | Dataset | Focus | Status |
|---|---|---|---|
| [Hotel Booking Cancellations](./hotel-booking-cancellations) | [Hotel Booking Demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) (Kaggle) | Categorical + numerical EDA, cancellation behavior | ✅ Complete |
| More coming | — | — | 🚧 In progress |

## Getting started

```bash
git clone https://github.com/imani-hamed/eda-projects.git
cd eda-projects
python -m venv venv
source venv/bin/activate        # on Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Then open any project's notebook with Jupyter:

```bash
jupyter notebook project-folder-name/EDA.ipynb
```

## Feedback & contributions

This is a learning-in-public project, so feedback is genuinely welcome:
- Think a dataset doesn't belong here, or know a better one? Open an issue.
- Spot an error or a question I should have asked in one of the notebooks? Open an issue or a PR.
- Want to suggest a dataset for a future project? Open a discussion.

## License

Feel free to reuse the notebooks and structure for your own learning. Dataset licenses belong to their original sources — check each project's README for attribution.
