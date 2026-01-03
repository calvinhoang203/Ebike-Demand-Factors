# Understanding What Drives E-Bike Demand: A Statistical Look at Yulu's Data

So Yulu's been seeing some pretty big dips in revenue lately. They need to figure out what's actually driving demand for their electric bikes - that's where this analysis comes in.

## What's This About?

Yulu operates shared electric bikes across India. Like most bike-sharing services, demand goes up and down based on weather, time of day, whether it's a holiday, etc. The question is: which of these factors *actually matter*, and by how much?

This project digs into their hourly rental data to answer those questions using proper statistical methods (not just eyeballing graphs).

## The Questions We're Trying to Answer

1. What factors significantly predict how many bikes people rent?
2. How strong are these relationships? Like, does rain *really* kill demand or just put a small dent in it?

## About the Data

We're working with hourly bike rental records that include:
- When bikes were rented (date/time)
- Seasonal info (spring, summer, fall, winter)
- Whether it was a holiday or working day  
- Weather conditions (clear, misty, light rain, heavy rain)
- Temperature (actual and "feels like")
- Humidity and wind speed
- Number of rentals by casual users vs. registered members
- Total rental count

The dataset has about 10,000 records covering different hours across multiple months.

## How I'm Approaching This

### Why Non-Parametric Tests?

Bike rental data doesn't follow a nice bell curve. Peak hours create weird distributions, weather has non-linear effects, etc. So instead of assuming normality (which the data violates), I'm using:

- **Mann-Whitney U test** - comparing two groups (like workday vs. weekend)
- **Kruskal-Wallis test** - comparing multiple groups (like all four seasons)
- **Spearman correlation** - finding relationships between variables

These tests work with the actual data ranks instead of assuming a specific distribution.

### Effect Sizes Matter

A p-value tells you *if* something matters. Effect size tells you *how much* it matters.

For example: Rain might statistically reduce demand (p < 0.05), but if the effect size is tiny, who cares? We need both pieces.

I'll be calculating:
- Cohen's d for standardized differences
- Rank-biserial correlation for Mann-Whitney results  
- Epsilon-squared for Kruskal-Wallis results

## What We're Looking For

By the end of this, we should know:

- Does weather actually matter? (Spoiler: probably yes, but let's prove it)
- Are weekdays vs. weekends really that different?
- How much does temperature affect things compared to, say, humidity?
- Is there a time-of-day pattern?
- Do holidays help or hurt demand?

## Current Status

🚧 Work in progress - starting with basic exploration

---

**Last updated:** January 2026
