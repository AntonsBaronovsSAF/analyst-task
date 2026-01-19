# Growth Data Analyst Take-Home Exercise: E-commerce Funnel Analysis

## Notes

1. You are provided with **pseudo-data** that is completely self-contained. While it tries to imitate real life it has no direct analogues in the campaigns Aranet have previously ran, so browsing Aranet's ad history or traffic estimates will not bring you any additional context, but will only drive you further from it.

2. You can use AI tools to perform this task, as long as you are able to explain and vouch for the code you delivered. If used, pelase share with us what tools you have used for the task.  

## Background

You are a Data Analyst at Aranet's B2C division. The marketing team has been running digital advertising campaigns on Meta (Facebook/Instagram) and Google to drive traffic and sales.

In December 2025, the team ran a special **Sale Promotion** campaign from December 10-17 alongside their ongoing **Remarketing** campaigns. Colleague of yours has dumped data from Meta Ads, Google Ads and Google Analytics APIs endpoints into a collection of csv files. Your task is to analyze the performance of these campaigns, build an e-commerce funnel analysis, and provide actionable insights.

## Dataset Overview

You have been provided with 4 CSV files that simulate data dumps from Meta Ads API, Google Ads API, and Google Analytics API. These files contain 30 days of data (December 1-30, 2025).

### Files Provided

**For detailed field descriptions**, see [DATA_DICTIONARY.md](DATA_DICTIONARY.md).

1. **meta_ads_campaigns_daily.csv** - Meta Ads campaign-level daily metrics (traffic-optimized)
   - *API Reference:* [Meta Marketing API - Campaign Insights](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights/)

2. **google_ads_campaigns_daily.csv** - Google Ads campaign-level daily metrics (click-optimized)
   - *API Reference:* [Google Ads API - Campaign Performance Report](https://developers.google.com/google-ads/api/fields/v16/campaign)

3. **ga_sessions_daily.csv** - Google Analytics session data by traffic source (post-click behavior)
   - *API Reference:* [Google Analytics Data API (GA4)](https://developers.google.com/analytics/devguides/reporting/data/v1)

4. **ga_ecommerce_daily.csv** - Google Analytics e-commerce funnel metrics (post-click conversions)
   - *API Reference:* [Google Analytics Data API - E-commerce Metrics](https://developers.google.com/analytics/devguides/reporting/data/v1/api-schema#metrics)
   - *Contains:* Complete conversion funnel and revenue data



## Your Task

Build a complete e-commerce funnel by combining ad platform and Google Analytics data. To answer questions:

### 1. Campaign Performance Analysis
- Which campaign delivered the best ROAS? 
- Which platform/campaign drives the highest quality traffic?
- Is cheaper traffic worth it if conversion rates are lower?
- What does the post-Dec 17 data tell you about user behavior and tracking?

### 2. E-commerce Funnel Analysis
- Where is the biggest drop-off in the funnel?
- Does the Sale campaign drive lower-quality or higher-quality traffic compared to Remarketing?
- What's the overall conversion rate from click to purchase?


## Deliverables

Please submit:

1. **Summary** that answer the questions in the task
2. **Visualizations** that support your conclusions
3. **Analysis Code/Queries** - SQL queries, Python/R scripts, Excel sheets, etc. - used to build out analysis


## Time Expectation

This exercise should take approximately 3-4 hours to complete.

Good luck! We look forward to seeing your analysis.


## Contact

If you have any questions about the task, please contact us!
