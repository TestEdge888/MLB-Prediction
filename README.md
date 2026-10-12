# Diamond Matchup

An MLB matchup predictor that compares teams using offensive and pitching statistics.

## About the Project

Diamond Matchup uses a statistical scoring model to compare the relative strengths of MLB teams. The model combines offensive statistics (55%) and pitching statistics (45%) to generate a matchup comparison.

The website allows users to select any two MLB teams and view their relative model scores.

## How It Works

The predictor analyzes team batting and pitching data to calculate a weighted score for each team. These scores are then normalized to show each team's relative strength in a head-to-head comparison.

The displayed percentages represent relative model scores, not validated win probabilities.

## Project Files

- `index.html` — Interactive website
- `scores.js` — Calculated team scores
- `build_scores.py` — Python script for generating team scores
- `source/` — Original prediction notebook and MLB datasets

## Running the Project

The website is hosted through GitHub Pages and can be accessed directly through a web browser.

To regenerate the team scores from the source data:

```python
python build_scores.py
```

## Author

Ryan — Statistical model and original Python implementation.
