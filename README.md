# Healthcare Spending and Life Expectancy

**DSC 209R — Project 3: Interactive Visualization**  
**UC San Diego | Fall 2026**

**Team:** Worldwide Health Team

**Team Members:**
- Jiamin (Carmen) Wu
- Justin Chanthabandith
- Matthew Takeuchi
- Kristen Oleson

---

## Research Question

### How does the relationship between healthcare spending and life expectancy vary across countries and over time?

This project explores the relationship between healthcare spending and life expectancy using World Bank health indicators from 2000 to 2018.

Our goal was to create an interactive visualization that allows users to compare countries, explore historical trends, and identify differences in healthcare spending and health outcomes.

Each point represents a country or territory, with healthcare spending per person on the horizontal axis and life expectancy at birth on the vertical axis.

**[Launch the Interactive D3 Visualization](https://thejustinrock.github.io/dsc-209r-project-3/index.html)**

---

## Dataset

**Source:** World Bank — World Development Indicators  
**Dataset:** Health Indicators (September 2021 extract)  
**Time Period:** 2000–2018

### Key Variables

| Variable | Description |
|---|---|
| Healthcare Spending | Current health expenditure per person in current purchasing-power-adjusted international dollars (current PPP). Values are not adjusted for inflation. |
| Life Expectancy | Life expectancy at birth, measured in years |
| Country | Country or territory associated with each observation |
| Region | World Bank region (current classification, e.g., "Middle East, North Africa, Afghanistan & Pakistan") |
| Year | Observation year from 2000 to 2018 |

### Data Preparation

We used the cleaned World Bank health indicators dataset and World Bank country metadata.

The data was prepared by:

- Excluding World Bank aggregate regions and income groups.
- Removing observations missing healthcare spending or life expectancy.
- Excluding observations with zero or negative healthcare spending.
- Assigning regions using current World Bank country metadata.
- Restricting two-year comparisons to countries with complete data in both selected years.

These steps help ensure meaningful comparisons across countries and years.

### Data Sources

- [World Bank World Development Indicators, health data (September 2021 extract, via the light-and-salt/World-Bank-Data-by-Indicators GitHub repository)](https://github.com/light-and-salt/World-Bank-Data-by-Indicators/blob/master/health/health-raw-2021.csv)
- [World Bank Country Metadata](https://api.worldbank.org/v2/country?format=json&per_page=400)
- [World Bank Open Data](https://data.worldbank.org/indicator)

---

## Design Rationale

Our goal was to explore how healthcare spending and life expectancy vary across countries and over time. Our exploratory analysis showed that countries spending more on healthcare generally have higher life expectancies, but there are exceptions. For example, the United States spends significantly more per person than Japan but has a lower life expectancy.

### Visual Design

We chose scatter plots because they make it easy to compare two numerical variables and identify patterns, clusters, and outliers.

| Visual Element | Design Choice | Purpose |
|---|---|---|
| **X-Axis** | Healthcare spending per person (logarithmic scale) | Accommodates large spending differences between countries |
| **Y-Axis** | Life expectancy at birth (years) | Allows direct comparison of health outcomes |
| **Colors** | World Bank regions | Helps identify geographic patterns |
| **Side-by-Side Charts** | Two years with identical axes | Enables consistent comparisons over time |

We kept a year slider and added an optional comparison mode that shows an earlier year side by side, making changes over time easier to recognize.

Both charts use the same scales and matching countries, allowing users to compare the relationship across years without being misled by changing axes or missing observations.

### Interactive Features

Our visualization includes several features designed to encourage exploration.

| Feature | Description |
|---|---|
| **Year Selection** | Use the slider to choose a year from 2000 to 2018. In comparison mode, the slider sets the later year. |
| **Compare Two Years** | Check the box and choose an earlier year to view two scatter plots side by side with identical axes. |
| **Pin a Country** | Click a point or use the dropdown to highlight a country and trace its trajectory. Click the point again to unpin it. Points can also be selected with the keyboard (Enter or Space). |
| **Tooltips** | Hover over a point to view the country, year, healthcare spending, and life expectancy. |
| **Regional Colors** | Identify geographic patterns using colors assigned to World Bank regions. |
| **Correlation Analysis** | Shows Pearson's correlation between log healthcare spending and life expectancy. Comparison mode uses only countries with data in both selected years. |

### Design Considerations

We focused on healthcare spending and life expectancy rather than including every variable from the dataset. Our goal was to keep the visualization simple and easy to navigate while still allowing users to explore meaningful patterns.

By combining year comparisons, country selection, and interactive details, users can investigate differences that would be harder to recognize in a static visualization.

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

We removed the regional filters from the prototype to keep the controls simple. Regions are still shown by color. We also fixed the x-axis range to the spread of the data, showed the introductory note only for the default 2000 vs. 2018 view, and broke country trails at years with missing data.

### Challenges

One of our main challenges was balancing interactivity with simplicity.

We wanted users to explore the data independently without overwhelming them with too many controls.

Maintaining consistent axes and comparing countries with complete data for both selected years were also important considerations.

### Team Contributions

| Team Member | Contributions |
|---|---|
| **Jiamin (Carmen) Wu** | Proposed the research question and World Bank dataset, cleaned the data, created six exploratory graphs, and developed the initial D3 prototype. |
| **Justin Chanthabandith** | Coordinated the team, expanded and refined the D3 prototype into the final interactive visualization, and maintained the GitHub repository. Also helped record the checkpoint video. |
| **Matthew Takeuchi** | Contributed to discussions about the dataset and research question, helped coordinate and record the checkpoint video, and submitted it to Canvas. |
| **Kristen Oleson** | Reviewed the exploratory graphs, helped coordinate the checkpoint video, contributed to research question discussions, wrote the design rationale and development process documentation, and updated the project README. |

### Development Time

Our team spent approximately **[FILL IN]** people-hours developing the visualization.

The most time-consuming aspects were **[FILL IN]**, including data preparation, implementation, and testing.

---

## Key Findings

Our visualization shows a strong positive association between log healthcare spending per person and life expectancy.

Across **172 countries and territories** with data in both 2000 and 2018, the correlation between log healthcare spending and life expectancy increased from **0.80 in 2000** to **0.84 in 2018**.

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

| Technology | Purpose |
|---|---|
| **D3.js** | Interactive data visualization |
| **JavaScript** | Data handling and interaction logic |
| **HTML** | Webpage structure |
| **CSS** | Styling and layout |
| **GitHub Pages** | Hosting and deployment |

---

## Project Links

- **[Live Interactive Visualization](https://thejustinrock.github.io/dsc-209r-project-3/index.html)**
- **[Original Project Repository](https://github.com/thejustinrock/dsc-209r-project-3)**
- **[World Bank Open Data](https://data.worldbank.org/indicator)**

---

*DSC 209R — Data Visualization | UC San Diego | Fall 2026*
