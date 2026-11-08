
# Healthcare Spending and Life Expectancy

### DSC 209R — Project 3: Interactive Visualization

**Team:** Worldwide Health Team

**Team Members:**
- Jiamin (Carmen) Wu
- Justin Chanthabandith
- Matthew Takeuchi
- Kristen Oleson

---

## Research Question

**How does the relationship between healthcare spending and life expectancy vary across countries and over time?**

This project explores the relationship between healthcare spending and life expectancy using World Bank health indicators from 2000 to 2018.

Our goal was to create an interactive visualization that allows users to compare countries, explore historical trends, and identify differences in healthcare spending and health outcomes.

Each point represents a country or territory. The visualization uses healthcare spending per person and life expectancy at birth to explore patterns across different regions and years.

### Interactive Visualization

**[Launch the Interactive D3 Visualization](https://thejustinrock.github.io/dsc-209r-project-3/index.html)**

---

## Dataset

**Source:** World Bank — World Development Indicators

**Dataset:** Health Indicators (September 2021 snapshot)

**Time Period:** 2000–2018

**Key Variables:**

| Variable | Description |
|---|---|
| Healthcare Spending | Current health expenditure per capita in purchasing-power-adjusted international dollars |
| Life Expectancy | Life expectancy at birth, measured in years |
| Country | Country or territory associated with each observation |
| Region | World Bank geographic region |
| Year | Observation year from 2000 to 2018 |

### Data Preparation

We used the cleaned World Bank health indicators dataset and World Bank country metadata.

The data was prepared by:

- Excluding World Bank aggregate regions and income groups.
- Removing observations missing healthcare spending or life expectancy.
- Excluding observations with zero or negative healthcare spending.
- Using a logarithmic transformation of healthcare spending.
- Restricting two-year comparisons to countries with complete data in both selected years.

The logarithmic scale helps display the large differences in healthcare expenditure across countries.

### Data Sources

- [World Bank Health Indicators Dataset](https://github.com/light-and-salt/World-Bank-Data-by-Indicators/blob/master/health/health-raw-2021.csv)
- [World Bank Country Metadata](https://api.worldbank.org/v2/country?format=json&per_page=400)
- [World Bank Open Data](https://data.worldbank.org/indicator)

---

## Design Rationale

Our goal was to explore how healthcare spending and life expectancy vary across countries and over time. Our exploratory analysis showed that countries spending more on healthcare generally have higher life expectancies, but there are exceptions. For example, the United States spends significantly more per person than Japan but has a lower life expectancy.

### Visual Design

We chose scatter plots because they make it easy to compare two numerical variables and identify patterns, clusters, and outliers.

- **X-axis:** Healthcare spending per person, using a logarithmic scale to account for large differences between countries.
- **Y-axis:** Life expectancy at birth, measured in years.
- **Colors:** World Bank regions, making geographic patterns easier to identify.
- **Side-by-side charts:** Two years displayed using identical axes to allow consistent comparisons.

We initially considered a single scatter plot with a year slider but ultimately chose a side-by-side comparison to make changes over time easier to recognize.

Both charts use the same scales and matching countries, allowing users to compare the relationship across different years without being misled by changing axes or missing observations.

### Interactive Features

Our visualization includes several interactive features designed to encourage exploration.

**1. Year Selection**

Users can adjust the year slider to explore the relationship between healthcare spending and life expectancy from 2000 to 2018.

**2. Compare Two Years**

The comparison feature displays two scatter plots side by side using identical axes.

This makes it easier to identify how different countries and the overall relationship change over time.

**3. Country Selection**

Users can select or pin individual countries using the dropdown menu or by clicking directly on a point.

Selected countries are highlighted, making them easier to follow across years.

**4. Tooltips**

Hovering over a country displays information about its healthcare spending and life expectancy.

**5. Regional Colors**

Countries are colored according to their World Bank geographic regions, making it easier to recognize regional patterns.

**6. Correlation Analysis**

The visualization displays Pearson's correlation between log healthcare spending and life expectancy.

This helps users understand the strength of the relationship for the selected years.

### Design Considerations

We focused on healthcare spending and life expectancy rather than including every variable from the dataset.

Our goal was to keep the visualization straightforward while allowing users to explore meaningful patterns.

We also wanted the interactive features to provide additional insights beyond what a static visualization could show.

---

## Development Process

We began by exploring the World Bank health indicators dataset and creating six exploratory graphs examining healthcare spending, life expectancy, infant mortality, and regional differences.

These graphs helped us narrow our research question and identify interesting patterns.

### Initial Prototype

Our first D3 prototype included:

- A scatter plot of healthcare spending and life expectancy
- A year slider
- Regional filters
- Interactive tooltips
- Country trajectories

### Final Visualization

We later refined the design to include two coordinated scatter plots, allowing users to compare different years directly.

This improved the visualization by making changes over time easier to recognize without relying on memory.

We also incorporated country selection and contextual information to help users interpret differences between countries.

### Challenges

One of our main challenges was balancing interactivity with simplicity.

We wanted users to explore the data independently without overwhelming them with too many controls.

Maintaining consistent axes and comparing countries with complete data for both selected years were also important considerations.

### Team Contributions

| Team Member | Contributions |
|---|---|
| Jiamin (Carmen) Wu | Data cleaning, exploratory graphs, and initial D3 prototype |
| Justin Chanthabandith | [Confirm development and deployment contributions] |
| Matthew Takeuchi | [Confirm project contributions] |
| Kristen Oleson | Checkpoint video coordination and editing, reviewing exploratory graphs and research question, and documentation |

### Development Time

Our team spent approximately **[total people-hours]** developing the visualization.

The most time-consuming aspects were **[confirm main development challenges]**, including data preparation, implementation, and testing.

---

## Key Findings

Our visualization shows a strong positive relationship between healthcare spending per person and life expectancy.

Across 172 countries and territories with data in both 2000 and 2018, the correlation between log healthcare spending and life expectancy increased from **0.80 in 2000 to 0.84 in 2018**.

However, higher spending did not always correspond to longer life expectancy.

### United States vs. Japan (2018)

| Country | Healthcare Spending Per Person | Life Expectancy |
|---|---:|---:|
| United States | $10,624 | 78.6 years |
| Japan | $4,504 | 84.2 years |

The United States spent more than twice as much per person as Japan, but Japan had a life expectancy approximately 5.6 years higher.

These findings demonstrate that healthcare spending alone does not fully explain differences in life expectancy across countries.

**Important:** Correlation does not establish causation. Our visualization shows associations between healthcare spending and life expectancy, not whether increased spending directly causes longer lives.

---

## Technologies Used

- **D3.js:** Interactive data visualization
- **JavaScript:** Data handling and interaction logic
- **HTML:** Page structure
- **CSS:** Styling and responsive layout
- **GitHub Pages:** Web deployment

---

## Project Links

- **[Live Interactive Visualization](https://thejustinrock.github.io/dsc-209r-project-3/index.html)**
- **[Original Project Repository](https://github.com/thejustinrock/dsc-209r-project-3)**
- **[World Bank Data](https://data.worldbank.org/indicator)**

---

*DSC 209R — Data Visualization | UC San Diego | Fall 2026*
