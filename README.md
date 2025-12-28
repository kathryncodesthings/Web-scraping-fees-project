# Data Projects

These projects showcase my technical data skills and my ability to solve real business problems. Each one starts with a practical question from stakeholders, uses data analysis to test assumptions, and ends with clear, actionable insights.

Where relevant, I include links to the full analysis and code.

---

## Web scraping university fees and fee analysis

**Skills demonstrated:** stakeholder engagement; problem definition; Python (pandas, numpy, matplotlib, beautifulsoup); web scraping; data cleaning and transformation; statistical analysis; outlier handling; data visualisation; communicating insights to non-technical audiences.

### Business question
The UK higher education sector is financially dependent on international students, particularly from China and Hong Kong (HK). 19% of the sector’s income is from overseas students (2021/22), and there is regulatory concern that it is exposed to financial risks if there is a drop in overseas students. (See ["International students in UK higher education"](https://researchbriefings.files.parliament.uk/documents/CBP-7976/CBP-7976.pdf) parliamentary research briefing, 28/05/2024.)

This project assesses the extent of this dependency and evaluates how UCL compared to 24 similar universities known as the 'Russell Group'.

### Approach

#### Project overview
*outline of the project steps and outputs*

I prioritised tasks based on available time and data. Instead of analysing 160+ UK universities, I focused on UCL’s closest competitors, the [Russell Group](https://www.russellgroup.ac.uk/), which is an alliance of universities known for high-quality research and attracting international students.

#### Web scraping
I scraped fee data from 24 university websites (i.e. from the HTML source code) using BeautifulSoup. It required complex processing to extract meaningful information. An example is provided here. Note that this code is from 2024: the university website has since been updated and the code will no longer work.

#### Other data
I used public data  from HESA (the UK Higher Education Statistics Agency), which publishes statistics for UK universities:
* Student demographics
* University income

#### Summary
* Cleaned and standardised the dataset
* Identified and handled outliers
* Analysed the relationship between:
  - Surplus/(deficit) as a percentage of income
  - Net cash generated from operations as a percentage of income
* Visualised the results to support clear communication with stakeholders

![Scatterplot of Net cash vs. Surplus/deficit for UK HEIs, 2015-2024](https://github.com/kathryncodesthings/python-data-projects/blob/main/HESA_data_scatterplot.png "Scatterplot of Net cash vs. Surplus/deficit for UK HEIs, 2015-2024")

### Juptyer Notebook
The complete code I produced is here: [HESA KFI Analysis Python code](https://github.com/kathryncodesthings/python-data-projects/blob/main/HESA%20data%20analysis.ipynb)
* step 1: link1
* step 2: link 2

### Conclusions
The key finding is that UCL has the most income in £ terms from international students among RG universities, primarily from China. UCL has fewer students from India, indicating growth potential. King's and Manchester also have higher international fee income, mainly from China. 

Some universities, like LSE and Imperial, show varied intakes but still concentrated around a few countries. This dependence on specific countries poses financial risks. 
In case of a drop in international students, intense competition would arise to recruit from the smaller pool of international students, given the financial impact of losing this income.

### Impact

### Possible improvemnts
#### Data refresh
This data relies on demographic and financial information from financial year 2021/2022. When I gathered this data it was the most recent information available. 

A refresh of this data would allow us to see how the situation has changed and potentially provide new insights.

#### Part-time fees
The fee information scraped on part-time courses (Mode of Study, PT/FT) was inconsistent due to the challenging structure of most university websites. The majority of course catalogues don't have separate pages for the part-time/full-time versions of their courses. For many programmes, the part-time fees were on the same page as the full-time fees, and in an inconsistent format, not available, or difficult to separate from the full-time course data.

Based on my sector knowledge, I know that almost all all part-time fees are 50% of the full-time fees. As a pragmatic estimate, I decided to remove any part-time lines from the data, and estimate the part-time fees as 50% of the full-time fee for all postgraduate courses. This might have reduced the accuracy of my data, which I communicated to stakeholders.

A future improvement would be to improve the web scraping step to correctly extract part-time fees and improve the accuracy of the data.
