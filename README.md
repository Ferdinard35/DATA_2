# DATA_2

Ghana Agricultural Market Data Pipeline & Power BI Intelligence System

## Overview
This project analyzes Ghanaian agricultural commodity prices across regions, districts, and markets to understand pricing patterns, market relationships, and co-movement between products. The workflow combines cleaned market data, exploratory analysis in Python, and a Power BI dashboard for business-facing insights.

The analysis focuses on identifying which commodities move together over time, using Pearson correlation to detect strong positive relationships. This makes it possible to spot market-linked products such as maize, tubers, fruits, and spices that tend to rise or fall in similar patterns.

## Project Goal
The main objective is to transform raw Ghana agricultural market data into a usable intelligence system that helps answer questions such as:

- Which commodities are strongly correlated in price movement?
- Which products move most similarly to ginger?
- How do prices vary across regions and markets over time?
- How can the results be shared through a dashboard for decision-making?

## Dataset
The project uses a cleaned commodity price dataset located at:

- `Dataset/Commodity prices _(Cleaned).csv`

The dataset includes the following fields:

- Region
- District
- Date
- Market
- Commodity
- Price
- Type

This dataset represents retail agricultural market observations across Ghana and supports time-series and correlation analysis.

## Methodology
The analysis pipeline follows these steps:

1. Load the cleaned CSV dataset.
2. Convert the `Date` column to a proper datetime format.
3. Ensure the `Price` column is numeric.
4. Remove invalid or incomplete rows.
5. Aggregate average daily prices by date and commodity.
6. Convert the data to a wide format for correlation analysis.
7. Filter commodities with enough observations for meaningful analysis.
8. Compute the Pearson correlation matrix.
9. Extract the strongest positive commodity pairs.
10. Visualize the top correlated pairs and the strongest co-movement with ginger.

## Key Insights from the Analysis
The project identifies the commodities with the strongest positive relationships in price movement. Examples from the generated output include:

- White maize × Yellow maize: 0.949
- Yam puna × Yam white: 0.934
- Ademe/ Ayajo/ Jute mallow × Alefu/ Amaranthus: 0.934
- Plantain apem × Plantain apentu: 0.920
- Banana exotic × Banana local: 0.907

A separate ginger-focused analysis shows the top commodities co-moving with ginger, including:

- Tiger nut: 0.730
- Cassava dough: 0.575
- Garden egg: 0.537
- Plantain ripe: 0.517
- Banana local: 0.514

These outputs are saved as visual charts in the `chart_image` folder.

## Tools and Technologies
This project uses:

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Power BI

## Project Structure

- `README.md` — project overview and documentation
- `Dataset/Commodity prices _(Cleaned).csv` — cleaned Ghana commodity dataset
- `src/Correlation_analysis.ipynb` — identifies the strongest commodity correlations
- `src/Ginger.ipynb` — analyzes the top commodities co-moving with ginger
- `Dashboard/Community Dashboard.pbix` — Power BI dashboard file
- `chart_image/` — exports of the generated analysis charts
- `Docs/` — supporting project documentation
- `Presentation/` — presentation materials

## Outputs
The project produces both analytical charts and dashboard outputs:

- Correlation heatmap for commodity prices
- Bar chart of the top 5 positively correlated commodity pairs
- Bar chart of the top 5 commodities most correlated with ginger
- Power BI dashboard summarizing market trends and commodity insights

## Reproducing the Analysis
To reproduce the results:

1. Open the notebook files in `src/`.
2. Ensure the dataset path points to the correct CSV file in your environment.
3. Run the notebook cells in order.
4. Review the generated plots and correlation tables.

> Note: The notebooks currently reference a local Windows file path. If you are running the project from a different machine or directory, update the file path before executing the code.

## Use Cases
This project is useful for:

- Agricultural market monitoring
- Price trend analysis
- Commodity dependency and co-movement analysis
- Data storytelling and dashboard-based reporting
- Early identification of linked market products

## Summary
DATA_2 team worked on  a practical data analytics project that turns Ghana agricultural market pricing data into actionable insights. It combines Python-based statistical analysis with a Power BI dashboard to provide a complete view of commodity relationships and market behavior.

