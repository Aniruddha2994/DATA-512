
## Data-512: Assignment 1

# Data Curation

### Contributors: 
[Aniruddha Dutta](https://github.com/aniruddha29)



### Description:
In this assignment, we collect monthly traffic data on English Wikipedia from January 1 2008 to August 30 2020. We then process the data and analyze the traffic trends for the desktop and mobile platforms for the collected timeperiod.

##### Contents:
1. Reading Data
2. Data Processing
3. Analysis: Timeseries Visualization

### Data:
We collect data from two different API endpoints:

1. The Legacy Pagecounts API provides access to desktop and mobile traffic data from Janunary 2008 through July 2016.       
[Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)  [Endpoint](https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end) 
2. The Pageviews API provides access to desktop, mobile web, and mobile app traffic data from July 2015 through last month.
[Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews)  [Endpoint](https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)

For this assignment, we need the traffic data from Jan 2008 to Aug 2020. The raw data is in json format.


### Data Curation and visualization:
The data from the two APIs is collected and stored in 5 json files, each corresponding to traffic on either desktop or mobile(app and web). This is then merged togetehr into one and stored in csv format for the analysis. 
The datasets are stored in the repository under the [data](https://github.com/Aniruddha2994/DATA-512/tree/main/data-512-a1/data) folder.

### Licenses:

This assignment is licensed under the terms of the [MIT license](https://github.com/Aniruddha2994/DATA-512/blob/main/LICENSE)
