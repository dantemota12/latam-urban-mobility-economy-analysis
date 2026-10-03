# Urban Mobility & Economic Productivity in Latin American Cities (2024)
Python analysis of urban traffic and economic indicators in Latin American cities (2024): TomTom Traffic Index and OECD Cities data.

## Objective
Evaluate how urban mobility relates to economic productivity in major Latin American cities, in order to identify where investing in transport infrastructure would have the greatest impact.

## Tools
Python · Pandas · NumPy · Seaborn · Matplotlib · Jupyter Notebook

## Datasets
- **TomTom Traffic Index** (`tomtom_traffic.csv`): over 1 million traffic records by city (jams delay, traffic index, jam length and count, travel time per 10 km, minutes of delay).
- **OECD Cities** (`oecd_city_economy.csv`): GDP per capita, unemployment rate, PM2.5 and population by city.

## Process
1. Loaded and explored both datasets, detecting type issues (dates stored as text, European number formats with `.` for thousands and `,` for decimals, and `%` symbols).
2. Standardized column names to `snake_case`.
3. Converted dates to `datetime` and cleaned numeric columns to `float`; created a total `population` column.
4. Extracted the year and filtered 2024.
5. Aggregated traffic records into yearly averages by city.
6. Merged traffic and economic data with an inner join on `city` and `year`.
7. Visualized the data with a boxplot (traffic), a histogram (GDP per capita) and a comparison bar chart.
8. Exported the clean dataset to `ladb_mobility_economy_2024_clean.csv`.

## Key Findings
1. **Mexico City** has the highest average jams delay in the 2024 traffic data (about **2,833 minutes**), ahead of Tokyo, New York and London.
2. **No clear direct relationship between GDP per capita and congestion** was found in the visual analysis. Cities such as Mexico City, Bogotá (**1,142** minutes, GDP per capita **$11,442**) and Lima show extreme congestion with moderate GDP per capita.
3. **Montevideo** stands out as a positive outlier: the highest GDP per capita in the region (**$26,176**) with low congestion.
4. Congestion appears to be more related to population density, road infrastructure and urban planning than to purchasing power.

## Recommendations
- **Bogotá is the top priority** for transport investment: over 1,100 minutes of jams delay combined with a GDP per capita about 13.7% below the regional average.
- **Lima is the second priority**: high congestion, large population and a GDP per capita only slightly above the regional average, which limits its own funding capacity.
- Invest over a 5 to 10 year horizon in mass transit (metro and BRT) rather than car-oriented infrastructure.
- Validate TomTom data with local mobility records before making investment decisions.

## Limitations
The analysis covers a single year (2024) and a small number of cities, and the relationship between traffic and GDP was assessed visually.

## Files
- `sprint_5_-_Proyecto_5__cuaderno_de_jupyter_-_S5_ladb_mobility_economy_project_student.ipynb`: full analysis notebook (cleaning, merging, visualization and executive summary).
- `ladb_mobility_economy_2024_clean.csv`: final clean dataset.
- `images/`: screenshots of the charts.
- [View the project in Google Drive](https://drive.google.com/file/d/14shw9v7YJnlNFczSMpQFy6hAVye3ox2G/view?usp=sharing)
