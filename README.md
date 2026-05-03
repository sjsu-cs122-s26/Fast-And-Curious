# US Traffic Accident Analysis (2016-2023)

This project analyzes patterns in US traffic accidents using a large-scale dataset covering 2016 through 2023. We looked at how factors like weather, time of day, and location affect accident frequency and severity.

## Dataset

We used the US Accidents dataset (March 2023 version), which has around 7.7 million accident records collected from various traffic APIs and law enforcement sources. The data includes details like GPS coordinates, weather conditions, time, and severity ratings.

**Key columns we focused on:**
- Accident severity (1-4 scale)
- Location data (lat/long, city, state)
- Weather conditions (temperature, humidity, visibility, precipitation, etc.)
- Temporal features (date, time, day/night)
- Road features (junctions, traffic signals)

## Getting Started

### Prerequisites

Python 3.7+ and the packages in `requirements.txt`:

```bash
pip install -r requirements.txt
```

### Running the Analysis

The notebook was originally designed for Google Colab (it mounts Google Drive for the dataset), but you can run it locally by:

1. Downloading the dataset from [Kaggle](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents)
2. Updating the file path in the notebook
3. Running the cells in order

If you're using Colab, just mount your Drive and make sure the CSV is in the shared drive location specified in the code.

## What We Found

Some interesting patterns emerged:

**Time-based patterns:**
- Rush hours (7-9 AM and 4-6 PM) show the highest accident rates, which makes sense
- Weekdays have way more accidents than weekends
- We noticed a sharp drop in accidents during March 2020 (COVID lockdowns) followed by a gradual recovery

**Weather impact:**
- Most accidents happen in clear or fair weather, probably just because that's the most common condition
- But when we looked at severity, wintry conditions (snow, ice) tended to produce more serious accidents
- Low visibility conditions also correlate with higher severity

**Geographic distribution:**
- California, Texas, and Florida have the most total accidents, but that's partly because they're huge states
- When we adjusted for population, some smaller states actually have higher per-capita accident rates
- The heatmap shows major urban corridors light up as expected (I-5, I-95, etc.)

**Day vs Night:**
- More accidents happen during the day overall
- But nighttime accidents tend to be slightly more severe on average

## Visualizations

The notebook generates several charts:

- Hour/day heatmap showing when accidents cluster
- Monthly trend line with COVID-19 annotation
- Weather condition breakdowns
- State-level comparisons (raw counts and per-capita)
- Correlation heatmap for numerical features
- Interactive folium heatmap (sampled to 50k points for performance)

## Limitations

A few things to keep in mind:

- The dataset relies on reported accidents, so there's probably some underreporting bias
- Weather data quality varies by location and time
- We had to drop rows with missing critical fields (about 10-15% of the original data)
- The per-capita analysis uses 2022 census estimates, which aren't perfect for the full 2016-2023 range

## Future Work

Could be interesting to:
- Build a predictive model for accident severity
- Dig deeper into specific metro areas
- Analyze accident duration patterns
- Look at seasonal variations more carefully

## Acknowledgments

Dataset originally compiled by Sobhan Moosavi and published on Kaggle. Shoutout to the team members who worked on different parts of the analysis.
