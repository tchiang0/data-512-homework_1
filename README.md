# data-512-homework_1
Data 512 Homework 1: Professionalism &amp; Reproducibility
## Goal
Construct, analyze, and publish a dataset of monthly article traffic for a select set of pages from English Wikipedia from July 1, 2015 through September 30, 2024
## License
Source Data: Wikimedia/Wikipedia \
[rare-disease_cleaned.AUG.2024.csv](rare-disease_cleaned.AUG.2024.csv)

[Creative Commons Attribution-ShareAlike 4.0 International License ("CC BY-SA 4.0")](https://creativecommons.org/licenses/by-sa/4.0/deed.en), and
[GNU Free Documentation License ("GFDL")](https://www.gnu.org/copyleft/fdl.html) (unversioned, with no invariant sections, front-cover texts, or back-cover texts).

 According to the ToU, all content contributed to or derived from Wikimedia Projects, including usage data like pageviews, is shared freely under a Creative Commons Attribution-ShareAlike license (CC BY-SA). This means my datasets, which includes publicly available pageview data, must also be freely accessible and properly attributed, ensuring that any reuse or modification of the dataset remains open and shared under the same or compatible terms.

## Pageviews API Documentation
[Documentation](https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html)

## Output Files
1. [rare-disease_monthy_desktop_201507-202409.json](rare-disease_monthly_desktop_201507-202409.json):
Time series of monthly pageview activity using desktop access from July 1st, 2015 to September 30th, 2024

2. [rare-disease_monthy_mobile_201507-202409.json](rare-disease_monthly_mobile_201507-202409.json): Time series of monthly pageview activity using mobile access (mobile-web and mobile-app) from July 1st, 2015 to September 30th, 2024

3. [rare-disease_monthly_cumulative_201507-202409.json](rare-disease_monthly_cumulative_201507-202409.json): Time series of monthly pageview activity using both access methods (desktop and mobile) from July 1st, 2015 to September 30th, 2024

**Schema** for all three files:
```
    "article_title": {
      "type": "array",
      "items": [
        {
          "type": "object",
          "properties": {
            "project": {
              "type": "string"
            },
            "article": {
              "type": "string"
            },
            "granularity": {
              "type": "string"
            },
            "timestamp": {
              "type": "string"
            },
            "agent": {
              "type": "string"
            },
            "views": {
              "type": "integer"
            }
          },...}
      ], ...
    }
```

4. [max_avg_and_min_avg.png](img/max_avg_and_min_avg.png): contains time series for the articles that have the highest average page requets and the lowest average page requests for desktop access and mobile access over the entire time series.

5. [log_transformed_max_avg_and_min_avg.png](img/log_transformed_max_avg_and_min_avg.png): log transformed of page reviews; contains time series for the articles that have the highest average page requets and the lowest average page requests for desktop access and mobile access over the entire time series.

6. [top_10_peak_pageviews.png](img/top_10_peak_pageviews.png): contains time series for the top 10 article pages by largest (peak) page views over the entire time series for desktop access and mobile access.

7. [log_transformed_top_10_peak_pageviews](img/log_tranformed_top_10_peak_pageviews.png): log transformed page reviews; contains time series for the top 10 article pages by largest (peak) page views over the entire time series for desktop access and mobile access.

8. [fewest_months_of_data](img/fewest_months_of_data.png): contains time series of articles that have the fewest months of available data via desktop and mobile access; 10 from desktop and 10 from mobile.

## Data Issues
- Not all rare diseases have data that spans the entire specified time period. For example, from July 1, 2015, through September 30, 2024, the *Black Death* page has 111 months of data, while *Filippi Syndrome* has only 34 months. 
- Additionally, the number of pageviews varies significantly between different rare diseases. For instance, the *Black Death* page saw a peak of 823,649 pageviews for desktop access, whereas *Filippi Syndrome* peaked at just 46 pageviews on desktop access.