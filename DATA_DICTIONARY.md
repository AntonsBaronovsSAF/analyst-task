# Data Dictionary

## 1. meta_ads_campaigns_daily.csv

**Description:** Daily campaign-level metrics from Meta Ads API (Facebook/Instagram).

**API Reference:** [Meta Marketing API - Campaign Insights](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights/)

**Endpoint Simulated:** `GET /{campaign-id}/insights` with campaign-level breakdowns

| Field | Type | Description |
|-------|------|-------------|
| date | DATE | Date of the metrics (YYYY-MM-DD) |
| campaign_id | INTEGER | Unique Meta campaign identifier |
| campaign_name | STRING | Name of the campaign |
| campaign_status | STRING | Campaign status (ACTIVE, PAUSED) |
| objective | STRING | Campaign objective (OUTCOME_TRAFFIC) |
| optimization_goal | STRING | What the campaign optimizes for (LINK_CLICKS) |
| bid_strategy | STRING | Bidding strategy (LOWEST_COST_WITHOUT_CAP) |
| daily_budget | FLOAT | Daily budget in USD |
| impressions | INTEGER | Number of times ads were shown |
| reach | INTEGER | Number of unique users who saw ads |
| frequency | FLOAT | Average impressions per user (impressions/reach) |
| clicks | INTEGER | Total clicks on ads |
| link_clicks | INTEGER | Clicks on links in ads |
| outbound_clicks | INTEGER | Clicks to external websites |
| cpc | FLOAT | Cost per click (USD) |
| cpm | FLOAT | Cost per 1000 impressions (USD) |
| cpp | FLOAT | Cost per 1000 people reached (USD) |
| ctr | FLOAT | Click-through rate (%) |
| link_ctr | FLOAT | Link click-through rate (%) |
| outbound_ctr | FLOAT | Outbound click-through rate (%) |
| spend | FLOAT | Amount spent in USD |
| video_views | INTEGER | Video ad views (noise metric) |
| video_avg_time_watched | FLOAT | Average video watch time in seconds (noise) |
| video_p25_watched | INTEGER | Videos watched to 25% (noise) |
| video_p50_watched | INTEGER | Videos watched to 50% (noise) |
| video_p75_watched | INTEGER | Videos watched to 75% (noise) |
| video_p100_watched | INTEGER | Videos watched to 100% (noise) |
| post_engagements | INTEGER | Total post engagements (noise) |
| post_reactions | INTEGER | Reactions on posts (noise) |
| post_comments | INTEGER | Comments on posts (noise) |
| post_shares | INTEGER | Shares of posts (noise) |
| page_likes | INTEGER | Page likes from ads (noise) |

**Note:** Video and post engagement metrics are included as "noise" to simulate real API data dumps but are not relevant for this traffic-focused campaign.


## 2. google_ads_campaigns_daily.csv

**Description:** Daily campaign-level metrics from Google Ads API.

**API Reference:** [Google Ads API - Campaign Performance Report](https://developers.google.com/google-ads/api/fields/v16/campaign)

**Endpoint Simulated:** `GoogleAdsService.SearchStream` querying the `campaign` resource with metrics

| Field | Type | Description |
|-------|------|-------------|
| date | DATE | Date of the metrics |
| customer_id | INTEGER | Google Ads customer account ID |
| campaign_id | INTEGER | Unique Google Ads campaign identifier |
| campaign_name | STRING | Name of the campaign |
| campaign_status | STRING | Campaign status (ENABLED, PAUSED) |
| advertising_channel_type | STRING | Channel type (SEARCH, DISPLAY) |
| bidding_strategy_type | STRING | Bidding strategy (MAXIMIZE_CLICKS) |
| budget_amount_micros | INTEGER | Daily budget in micros (divide by 1,000,000 for USD) |
| budget_explicitly_shared | BOOLEAN | Whether budget is shared across campaigns |
| impressions | INTEGER | Number of ad impressions |
| clicks | INTEGER | Number of clicks |
| interactions | INTEGER | Total interactions |
| cost_micros | INTEGER | Cost in micros (divide by 1,000,000 for USD) |
| average_cpc | FLOAT | Average cost per click (USD) |
| average_cpm | FLOAT | Average cost per 1000 impressions (USD) |
| ctr | FLOAT | Click-through rate (%) |
| interaction_rate | FLOAT | Interaction rate (%) |
| quality_score_avg | FLOAT | Average quality score (1-10, only for Search, 0 for Display) |
| search_impression_share | FLOAT | Search impression share (Search only, 0-1) |
| search_rank_lost_impression_share | FLOAT | Lost impression share due to ad rank |
| search_budget_lost_impression_share | FLOAT | Lost impression share due to budget |

**Important:** The `cost_micros` and `budget_amount_micros` fields must be divided by 1,000,000 to convert to USD.


## 3. ga_sessions_daily.csv

**Description:** Google Analytics session data by traffic source/medium/campaign.

**API Reference:** [Google Analytics Data API (GA4)](https://developers.google.com/analytics/devguides/reporting/data/v1)

**Endpoint Simulated:** `POST /v1beta/properties/{propertyId}:runReport` with session metrics and source/medium dimensions

| Field | Type | Description |
|-------|------|-------------|
| date | DATE | Date of the sessions |
| source | STRING | Traffic source (facebook, google, direct) |
| medium | STRING | Traffic medium (cpc, organic, (none)) |
| campaign | STRING | Campaign name from UTM parameters |
| device_category | STRING | Device type (desktop, mobile, tablet) |
| sessions | INTEGER | Number of sessions |
| users | INTEGER | Number of users |
| new_users | INTEGER | Number of new users |
| pageviews | INTEGER | Total pageviews |
| pages_per_session | FLOAT | Average pages viewed per session |
| avg_session_duration_seconds | FLOAT | Average session duration in seconds |
| bounce_rate | FLOAT | Bounce rate (0-1, where 0.45 = 45%) |
| entrances | INTEGER | Number of entrances |
| landing_page | STRING | Landing page URL |


## 4. ga_ecommerce_daily.csv

**Description:** Google Analytics e-commerce funnel metrics by traffic source.

**API Reference:** [Google Analytics Data API - E-commerce Metrics](https://developers.google.com/analytics/devguides/reporting/data/v1/api-schema#metrics)

**Endpoint Simulated:** `POST /v1beta/properties/{propertyId}:runReport` with e-commerce event metrics

| Field | Type | Description |
|-------|------|-------------|
| date | DATE | Date of the metrics |
| source | STRING | Traffic source |
| medium | STRING | Traffic medium |
| campaign | STRING | Campaign name |
| product_detail_views | INTEGER | Number of product detail page views |
| add_to_cart_events | INTEGER | Number of add-to-cart events |
| checkout_initiations | INTEGER | Number of checkout starts |
| transactions | INTEGER | Number of completed transactions |
| revenue | FLOAT | Total revenue (USD) |
| avg_order_value | FLOAT | Average order value (USD) |
| cart_to_detail_rate | FLOAT | Add-to-cart rate (add_to_cart/product_views) |
| checkout_to_cart_rate | FLOAT | Checkout rate (checkouts/add_to_cart) |
| purchase_to_checkout_rate | FLOAT | Purchase rate (transactions/checkouts) |
| items_purchased | INTEGER | Total items purchased |
