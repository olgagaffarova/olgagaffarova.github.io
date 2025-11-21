# CitiBike NYC 2022 Ridership Analysis

## Skills & Tools

- **Programming:** Python
- **Analysis:** Data Cleaning, Wrangling, Visualization, Regression Analysis & Modeling
- **Techniques:** Grouping & Aggregating Data, Pareto Analysis, Supply-Demand Gap Analysis
- **Visualization:** Streamlit (Dashboard), Python (Kepler Maps, Matplotlib, Seaborn, Plotly)
- **Libraries:** pandas, NumPy, scikit-learn, statsmodels

---

## Project Objective

This analysis examines CitiBike's 2022 ridership to improve bike availability, optimize fleet management, and identify expansion opportunities across New York City.

---

## Scope

- Weather Impact and Fleet Optimization (Nov–Apr)
- Identifying Main Routes and Problem Stations
- Predictive Rebalancing Strategy
- Waterfront Expansion Opportunities
- Actionable Recommendations

---

## Key Findings

### 1. Pareto Analysis of CitiBike Routes (80/20 Rule)

To identify key corridors carrying most system traffic, we applied Pareto analysis to all Origin → Destination (OD) routes.

**Approach:**
- Count total trips for every OD pair
- Sort routes from highest to lowest volume
- Calculate each route's % contribution to total traffic
- Compute cumulative % to find where 80% of trips is reached

**Result:**  
Only **14% of all routes account for 80% of total CitiBike trips**.

![Main CitiBike Routes](citychart1.png)

These high-traffic corridors reveal:
- Main commuter pathways
- Areas with highest operational pressure
- Priority corridors for rebalancing and infrastructure expansion

---

### 2. Station Imbalance Analysis (Rentals vs Returns)

To identify stations that consistently run out of bikes or become overfilled, we calculated net flow for our top 14% most popular stations (which account for ~80% of demand).

**Net Flow = Trips Starting at Station – Trips Ending at Station**

- 🔵 **Positive net flow (blue):** More bikes leave than arrive → **shortage risk** → station needs bike delivery
- 🔴 **Negative net flow (red):** More bikes arrive than leave → **overflow risk** → station needs bike removal

![Station Imbalance Map](citychart2.png)

**Key Findings:**
- **Midtown stations** (Broadway, Madison Ave, West End Ave) show persistent shortages
- **Downtown stations** (Old Slip & South St, Washington Square E) accumulate bikes and frequently overflow

**Action:**  
By relocating bikes from overflowing red stations to shortage blue stations, CitiBike can:
- Reduce shortages and full-dock issues
- Improve rider experience
- Reduce redistribution truck mileage

---

### 3. Predictive Rebalancing Strategy

This analysis shows dynamic bike redistribution needs based on actual usage patterns. By analyzing net flow at each station, we predict where bikes need delivery or collection.

We computed the **80th percentile (top 20%) activity threshold** for each month, focusing on operationally critical stations where rebalancing decisions matter most.

![Rebalancing Strategy](citychart3.png)

**Operational Strategy:**

Schedule rebalancing trucks **1 hour before peak times:**
- **Morning prep (6–7 AM):** Position bikes at residential/transit hubs before commute
- **Afternoon prep (4–5 PM):** Position bikes at business districts before evening rush
- Use this data to create optimized collection/delivery routes
- Monitor real-time for weather, events, or anomalies

**Cost-Benefit:**
- Prevents lost revenue from empty stations (unsatisfied demand)
- Prevents operational issues from overflow (bikes blocking sidewalks)
- Improves customer satisfaction (bikes available when/where needed)

---

### 4. Waterfront Expansion Opportunities

We explored spatial demand clusters along Hudson and East Rivers to identify where new stations could relieve congestion and serve riders. This analysis applies a **supply-demand framework** to identify capacity gaps.

**Methodology:**

**Define Waterfront Zones** using Waterfront Access Plans (WAPs):
- Hunters Point
- Newtown Creek
- Harlem River (Core, North, South)
- Inwood
- Flushing
- Gowanus Canal

**Supply-Demand Gap Analysis:**
- **Supply:** % of stations within 400m of shoreline in WAP zones
- **Demand:** % of trips starting/ending in these zones
- **Gap:** Areas where demand exceeds supply

![Waterfront Zones](citychart4.png)

---

### Supply Analysis (Shoreline-Based)

- **Total stations:** 1,757
- **Waterfront stations (≤ 400m):** 268
- **Waterfront supply share:** 15.3%

![Supply Share](citychart5.png)

---

### Top Waterfront Origin → Destination Flows

The Sankey diagram below highlights the top 20 waterfront routes with highest trip counts. Each connection represents major flow between two waterfront stations, indicating pressure zones where additional docks could balance supply and ease congestion.

![Waterfront Flows Sankey](citychart6.png)

---

### Origin–Destination Matrix — Top Waterfront Routes

The matrix below shows trip volumes between the busiest waterfront station pairs. Darker cells indicate stronger flow intensity (higher trip counts).

![OD Matrix](citychart7.png)

---

## Recommendations

### Waterfront Expansion

**Finding:**  
Waterfront stations make up only **15.3%** of the network, while nearly **24%** of all trips start or end near the riverside. This indicates a **demand–supply gap of ~9 percentage points**.

**Action Plan:**

1. **Add new docking stations** along Hudson River and East River
2. **Prioritize high-pressure OD corridors** highlighted in the Sankey diagram:
   - Soissons Landing ↔ Vesey St & Church St
   - Roosevelt Island ↔ Pier 40 — Hudson River Park
3. **Focus on Public Access Zones:** Hunters Point, Newtown Creek, Harlem River areas, Inwood, Flushing, Gowanus Canal
4. **Deploy stations before peak-demand months** (May–September)

**Expected Impact:**
- Reduce bike shortages at popular leisure and commuter waterfront routes
- Improve accessibility for weekend and tourist riders
- Balance network capacity between inner-city and riverside zones

---

### Rebalancing Operations

1. Implement predictive rebalancing 1 hour before peak times
2. Focus redistribution on top 14% routes (80% of demand)
3. Prioritize Midtown deliveries and Downtown collections
4. Use real-time monitoring to adjust for weather and events

---

## Project Files

- 📊 [View Analysis Notebook](#)
- 📈 [Streamlit Dashboard](#)
- 📁 [Dataset & Code](#)

---

## Contact

Feel free to reach out if you have questions about this analysis!

- **LinkedIn:** [linkedin.com/in/gaffarova](https://www.linkedin.com/in/gaffarova/)
- **GitHub:** [github.com/olgagaffarova](https://github.com/olgagaffarova)
- **Email:** hola.gaffarova@gmail.com
