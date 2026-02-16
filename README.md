# Analyzing Consumer Feedback on Spotify

In this project, we are interested in understanding consumer purchasing behavior on e-commerce platforms—what people buy, when they buy it, and how patterns differ across regions and customer groups. Using Amazon transaction and survey data, we explored purchasing trends across product categories and found the **Gift Card** category especially compelling due to its strong seasonality and marketing value.

<br>

## Group Members  
Armor Cao, Becky Song, Liujun Chen

<br>

## Research Questions  
RQ 1: When do consumers most frequently purchase gift cards, and is there a discernible time trend?

RQ 2: What are the regional patterns associated with gift card purchases? 

RQ 3: Do customers typically purchase gift cards together with other product categories, or do they usually buy them on their own? 

RQ 4: How often, how recently, and how much do consumers spend when purchasing gift cards? 

<br>

## Dataset  
This project analyzes e-commerce consumer behavior using data from the "Open e-commerce 1.0" dataset (Berke et al., 2023), sourced from the Harvard Dataverse. The dataset contains respondent' demographic information and Amazon spending behavior. Each observation represents an individual survey respondent with associated spending data. 

We will be using two datasets from the original study: the `amazon-purchase.csv` and the `survey.csv`. The transactional purchase dataset includes details of Survey ResponseID, order date, shipping state, unit price, quantity, product code, title, and category. The survey dataset provides corresponding demographic and spending habit information, also with the Survey ResponseID column. 

Data Citation: Alex Berke; Dan Calacci; Robert Mahari; Takahiro Yabe; Kent Larson; Sandy Pentland, 2023, "Open e-commerce 1.0: Five years of crowdsourced U.S. Amazon purchase histories with user demographics", Harvard Dataverse, V1, https://doi.org/10.7910/DVN/YGLYDY UNF:6:mV4isMgPXhqWeiQ3gZmmNQ==

<br>

## Data Cleaning
Before analysis, we applied two data-cleaning steps to improve accuracy:

First, we removed extreme outliers by excluding transactions above the 99th percentile of gift card quantity (e.g., unusually large bulk orders).

Second, we filtered out micro-value transactions (unit price < $1), which are likely balance adjustments or test purchases that inflate frequency and distort retention results.

<br>

## Results & Insights
### Time Series Analysis
The graph shows a strong seasonal pattern and an **overall upward trend** in Amazon gift card purchases from 2018 to 2022. Purchases consistently **spike in Q4** each year, reflecting holiday-driven demand, with occasional smaller increases in Q2–Q3. Notably, **after the onset of COVID-19 in 2020 Q1, sales rose sharply**, suggesting a shift toward digital and contactless gifting. Overall, the results indicate that gift cards are primarily a year-end holiday product, and that pandemic-driven behavior contributed to a structural increase in long-term demand.

<img width="400" height="400" alt="Screenshot 2026-02-15 at 4 17 12 PM" src="https://github.com/user-attachments/assets/d6ff5358-b851-4386-ad44-2db8a1403e82" />


### Regional Patterns
This map shows a clear geographic concentration of gift card purchases, with the highest volumes in large, economically strong states such as California (4,254), New York (3,253), and Texas (2,723). Demand closely tracks population size, urbanization, and disposable income, **with major metropolitan areas exhibiting stronger digital and retail engagement**. **Lower-population and more rural states show lighter volumes**, suggesting fewer transactions and different consumer or digital adoption patterns. Overall, population density, income, and urban retail participation appear to be key drivers of gift card purchasing behavior.

<img width="600" height="450" alt="Screenshot 2026-02-15 at 4 17 55 PM" src="https://github.com/user-attachments/assets/133c5bee-c48c-430f-925b-c8c5bf217833" />


### Combo Analysis
The combo analysis shows that the **majority of customers** (roughly 70% across all years) prefer to **purchase gift cards alone without selecting an envelope add-on**. While there is some year-to-year fluctuation (a higher share in 2018-2019, a slight dip in 2020-2021, and a rebound to 73% in 2023), the changes are relatively small, all within a 10-percentage-point range.

<img width="400" height="400" alt="Screenshot 2026-02-15 at 4 18 54 PM" src="https://github.com/user-attachments/assets/c044534b-408c-4aad-ae12-a6203132761f" />

### Retention Analysis
In this heatmap, the Frequency = 5 column consistently appears darker than all other frequency levels because customers in this group make dramatically more purchases, with an average frequency of 11 in 2022, which is much higher than any other group with frequency scores of 1-4. This exceptionally high purchase volume naturally leads to much higher total spending, which shows up as darker shading regardless of their recency score. Moreover, in this chart, the single darkest cell occurs at **Recency = 4 and Frequency = 5**, representing that **customers who buy both very frequently and relatively recently have the highest total spending**. This combination of high engagement and recent activity identifies the highest-value segment in the dataset, explaining why this segment has the strongest intensity on the heatmap.

<img width="400" height="400" alt="Screenshot 2026-02-15 at 4 20 00 PM" src="https://github.com/user-attachments/assets/fa2f7d87-13c4-4eff-a502-172babe6a9fc" />

<br>

## Business Strategy
**Exploit strong Q4 seasonality with precision targeting**: Concentrate acquisition, reactivation, and promotional spend in Q4, using Q3 warm-up campaigns and holiday-specific messaging to maximize conversion during peak gifting demand.

**Prioritize high-value customers using RFM segmentation**: Focus retention efforts on high-frequency, high-recency customers (R≥4, F=5) through loyalty perks, personalized offers, and early access, as this segment drives the highest total spend.

**Optimize upsell strategy by respecting customer preferences**: Keep “gift card only” as the default purchase flow, and selectively promote envelope add-ons during high-intent moments (e.g., holidays, first-time buyers) to increase attachment without harming conversion.

**Allocate marketing resources geographically for higher ROI**: Direct spend toward large, urban, high-income states where demand and digital engagement are strongest, while using lower-cost channels in lower-volume regions.
