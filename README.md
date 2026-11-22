# Quick-Commerce Delivery-Delay Root-Cause Analysis

## Business problem
A quick-commerce company wants to understand why deliveries are delayed in certain zones and identify the highest-impact operational improvements.

## Business questions
1. What is the overall on-time delivery rate and average delivery delay?
2. Which zones, time slots, and order types have the worst delay performance?
3. Are delays driven by rider assignment, kitchen preparation time, distance, weather, or peak-hour congestion?
4. Which interventions are likely to improve on-time delivery the most?

## Dataset
`data/orders.csv` is a synthetic but realistic dataset with 5,000 orders.

Columns:
- order_id
- order_datetime
- zone
- restaurant_id
- rider_id
- items_count
- order_value
- promised_delivery_minutes
- prep_time_minutes
- pickup_delay_minutes
- travel_time_minutes
- actual_delivery_minutes
- delivery_status: On time / Delayed
- delay_minutes
- weather: Clear / Rain / Fog
- traffic_level: Low / Medium / High
- rider_experience: Junior / Mid / Senior
- is_peak_hour
- customer_rating

## Repository structure
```
quickcommerce-delay-project/
├── README.md
├── data/
│   └── orders.csv
├── sql/
│   └── delay_analysis.sql
├── python/
│   └── delay_analysis.py
├── powerbi/
│   └── dashboard_design.md
└── outputs/
    └── delay_analysis_summary.csv
```

## How to run
1. Install requirements: `pip install pandas numpy matplotlib seaborn`
2. Run Python analysis: `python python/delay_analysis.py`
3. Open `outputs/delay_analysis_summary.csv` for the generated metrics.
4. Import `data/orders.csv` into Power BI and follow `powerbi/dashboard_design.md`.

## Dashboard pages
1. **Executive overview:** on-time rate, average delay, delayed orders, revenue at risk.
2. **Zone performance:** delay rate, average delay, order volume, and delay contribution by zone.
3. **Root-cause analysis:** prep time, pickup delay, travel time, traffic, weather, rider experience.
4. **Action plan:** top delay drivers, affected zones, and recommended interventions.

## Expected insights
- Peak-hour orders and high-traffic zones generally show higher delay rates.
- High pickup delay and long kitchen preparation time are major controllable delay drivers.
- Rain and fog increase travel time and delay probability.
- Junior riders may have higher pickup delays, indicating a training or allocation issue.
- The final recommendation should prioritize zones and time slots with high delay volume and high revenue impact.
