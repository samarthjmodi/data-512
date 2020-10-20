

# DATA 512 Assignment A1: Data Curation

## Goal
The goal of this assignment is to construct, analyze, and publish a dataset of monthly traffic on English Wikipedia from January 1, 2008 through August 30, 2020.

## Data Source
In order to measure Wikipedia traffic from 2008-2020, you will need to collect data from two different API endpoints, the Legacy Pagecounts API and the Pageviews API.

1.  The Legacy Pagecounts API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts), [endpoint](https://wikimedia.org/api/rest_v1/#!/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end)) provides access to desktop and mobile traffic data from December 2007 through July 2016.
2.  The Pageviews API ([documentation ](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews), [endpoint](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)) provides access to desktop, mobile web, and mobile app traffic data from July 2015 through last month.

Please find Wikimedia Foundation REST API terms of use [here].(https://www.mediawiki.org/wiki/Wikimedia_REST_API#Terms_and_conditions)

## Deliveriables in this repository

- 5 source data files in JSON format 
	1. *pagecounts_desktop-site_200801-201607.json*
	2. *pagecounts_mobile-site_200801-201607.json*
	3. *pageviews_desktop-site_201507-202008.json*
	4. *pageviews_mobile-web_201507-202008.json*
	5. *pageviews_mobile-app_201507-202008.json*

- Final data file in CSV format: *en-wikipedia_traffic_200712-202008.csv*
- Jupyter notebook containing all code and information necessary to understand each programming step: *data-512-a1.ipynb*
- LICENSE file with *MIT LICENSE* for my code
- Image for my visualization: *PageViews_on_English_Wikipedia.png*

## Final data file
The final data file, "en-wikipedia_traffic_200712-202008.csv", has 153 rows corresponding to data for 153 months over 13 years, from year 2007 till 2020. The datafile has 8 columns, all of :

1. *year* (int64): Year of traffic data 
2. *month* (int64): Month of traffic data 
3. *pagecount_all_views* (float64): Total traffic observed from Pagecounts API
4. *pagecount_desktop_views* (float64): Desktop traffic observed from Pagecounts API
5. *pagecount_mobile_views* (float64): Mobile traffic observed from Pagecounts API
6. *pageview_all_views* (float64): Total traffic observed from Pageviews API
7. *pageview_desktop_views* (float64): Desktop traffic observed from Pageviews API
8. *pageview_mobile_views* (float64): Mobile traffic observed from Pageviews API

## Special Considerations
1. Pageview API excludes spiders/crawlers, while data from the Pagecounts API does not.
2. All values of pagecount_mobile_views for months before October 2014 is 0, because mobile traffic data is not available before that month.


