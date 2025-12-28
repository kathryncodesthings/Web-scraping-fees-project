# Data Projects

These projects showcase my technical data skills and my ability to solve real business problems. Each one starts with a practical question from stakeholders, uses data analysis to test assumptions, and ends with clear, actionable insights.

Where relevant, I include links to the full analysis and code.

---

## Web scraping university fees and fee analysis

**Skills demonstrated:** stakeholder engagement; problem definition; Python (pandas, numpy, matplotlib, beautifulsoup); web scraping; data cleaning and transformation; statistical analysis; outlier handling; data visualisation; communicating insights to non-technical audiences.

### Business question
The UK higher education sector is financially dependent on international students, particularly from China and Hong Kong (HK). 19% of the sector’s income is from overseas students (2021/22), and there is regulatory concern that it is exposed to financial risks if there is a drop in overseas students. (See ["International students in UK higher education"](https://researchbriefings.files.parliament.uk/documents/CBP-7976/CBP-7976.pdf) parliamentary research briefing, 28/05/2024.)

This project assesses the extent of this dependency and evaluates how UCL compared to 24 similar universities.

### Approach

#### Project overview
*outline of the project steps and outputs*

I prioritised tasks based on available time and data. Instead of analysing 160+ UK universities, I focused on UCL’s closest competitors, the [Russell Group](https://www.russellgroup.ac.uk/), which is an alliance of universities known for high-quality research and attracting international students.

* Established requirements (see above)
* Obtained data
* Cleaned and initial investigation of data
* Combined and visualised data
* Investigated further
* Drew concolusions
* Presented results

#### Data

##### Web scraping
I scraped fee data from 24 university websites (i.e. from the HTML source code) using BeautifulSoup. It required complex processing to extract meaningful information. An example is provided [here](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Data%20Scraping%20-%20Bristol%20UG%20course%20data.ipynb). Note that this code is from 2024: the university website has since been updated and the code will no longer work.

##### Other data
I used public data  from HESA (the UK Higher Education Statistics Agency), which publishes statistics for UK universities:
* Student demographics
* University income

### Juptyer Notebooks
Samples from relevant notebooks are linked below.
* Web scraping fee data ([**example** code](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Data%20Scraping%20-%20Bristol%20UG%20course%20data.ipynb))
* Cleaning fee data and intitial visualisation of fee data ([sample of code](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Fee%20data%20cleaning%2C%20exploration%20and%20visualisation%20part%201.ipynb))
* Visualising student demographic data from HESA ([sample of code](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Visualise%20students%20by%20country.ipynb))
* combined and visualised data to show estimates of different universities' reliance on fees from overseas students ([code](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Fee%20data%20cleaning%20and%20combination%20with%20income%20and%20student%20demographic%20data.ipynb)
* investigated further
  
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
