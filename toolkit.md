# My Analyst Toolkit — Day 1 Deliverable

## Tools

| Tool | Status | Notes |
|---|---|---|
| Excel | ✅ Installed | `Office16\EXCEL.EXE` found on this machine |
| Power BI Desktop | ✅ Installed | ready for Week 4 |
| SQL sandbox | ✅ Ready | using [DB Fiddle](https://www.db-fiddle.com/) (no signup) for Week 1-2; will move to DB Browser for SQLite on Day 15 |
| Git | ✅ Installed | via Git Bash |
| GitHub account | ✅ Have one | [github.com/Nishi-013](https://github.com/Nishi-013) |
| GitHub repo pushed | ✅ Live | [github.com/Nishi-013/data-analyst-30-day-log](https://github.com/Nishi-013/data-analyst-30-day-log) |

## The 7-step analyst loop — worked example

*Scenario: I run a small online store. Last month I ran a $500 Instagram ad campaign for a new product line.*

| Step | What I'd actually do |
|---|---|
| **1. Business question** | Did the Instagram campaign pay for itself — did it actually drive more orders than a normal month? |
| **2. Data inspection** | Pull order data for the campaign month and the month before; check what columns exist — order date, order value, and (if I'm lucky) a "traffic source" field showing which orders came from Instagram. |
| **3. Data cleaning** | Remove test/duplicate orders, fix any blank traffic-source values, make sure both months use the same currency and time zone. |
| **4. Analysis** | Compare total revenue and order count in the campaign month vs. the prior month; calculate revenue specifically tagged to Instagram traffic; work out cost per order (ad spend ÷ Instagram-driven orders). |
| **5. Visualization** | A simple bar chart: revenue by traffic source, campaign month vs. prior month, side by side. |
| **6. Insight** | Instagram-tagged orders brought in $650 in revenue against $500 in ad spend — a small net gain, but the cost per order ($41) is nearly double our normal cost per customer ($22). |
| **7. Recommendation** | Don't scale the campaign as-is — it's barely profitable. Test a lower-cost audience or a cheaper creative before increasing spend. |

## The 7-step analyst loop — my own example

*My scenario: one month of my own personal spending (see [week1/day1-sample-spending.csv](week1/day1-sample-spending.csv)), 20 transactions across 7 categories.*

| Step | What I actually did |
|---|---|
| **1. Business question** | Which spending category is large enough that trimming it would free up real money, without me noticing a difference in daily life? |
| **2. Data inspection** | Columns: Date, Category (the dimension), Description, Amount (the measure). Found 3 problems before trusting any total: inconsistent capitalization ("groceries" vs "Groceries"), one exact duplicate row (same date/description/amount), one blank Amount cell. |
| **3. Data cleaning** | Standardized capitalization on Category; deleted the duplicate row; imputed the one blank Amount (a Dining transaction) with an estimated value rather than leaving it blank or guessing a fake exact number silently. |
| **4. Analysis** | Summed Amount by Category. Result: Rent $650, Shopping $410, Groceries $238.32, Transit $120, Dining $130.22, Subscriptions $38.47, Entertainment $15. |
| **5. Visualization** | Built a horizontal bar chart in Excel (Category → Amount), sorted so the biggest categories stand out immediately. |
| **6. Insight** | My gut guess going in was "cut Dining" — the data proved that wrong. Dining is actually small. The two real levers are Shopping ($410, but a one-time headphone purchase, not a recurring habit) and Rent ($650, fixed, can't be cut). Dining ($130.22) is the only category that's both sizeable *and* made of 5 recurring, discretionary transactions — coffee, pizza, snacks — the kind of spending that's easy to trim without a lifestyle change. |
| **7. Recommendation** | Don't touch Rent (fixed) or treat the Shopping spike as a pattern (it's a one-off). Instead, set a monthly Dining cap — cutting 2 of the 5 dining-out occasions would save roughly $30-40/month without cutting groceries, transit, or rent. |

*Lesson to remember: my first instinct (Dining) was wrong until I actually ran the numbers. That gap between "what I assumed" and "what the data showed" is the entire reason this job exists.*

## Today's interview questions — starter answers (edit these in your own words before Day 30)

**Q: What does a Data Analyst do day to day?**
> Turns a business question nobody can answer just by looking ("did this work?", "where's my money/time actually going?") into a specific, defensible answer using real data — then recommends what to do about it. Not just building charts; the charts are just how the answer gets delivered.

**Q: Walk me through how you'd approach a dataset you've never seen before.**
> Start with the business question it needs to answer. Then inspect it: what are the columns, which are dimensions vs. measures, how many rows, what time range. Then check data quality — missing values, duplicates, inconsistent text, outliers — before trusting any number. Only then calculate anything, and I'd sanity-check first instincts against what the numbers actually show, because gut guesses are often wrong (mine was, on my own spending data).
