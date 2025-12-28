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
I prioritised tasks based on available time and data. Instead of analysing 160+ UK universities, I focused on UCL’s closest competitors, the [Russell Group](https://www.russellgroup.ac.uk/), which is an alliance of universities known for high-quality research and attracting international students.

* Established requirements (see above)
* Obtained data
* Cleaned and initial exploration of data
* Combined and visualised data
* Drew conclusions
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
* combined and visualised data to show estimates of different universities' reliance on fees from overseas students ([sample code](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Fee%20data%20cleaning%20and%20combination%20with%20income%20and%20student%20demographic%20data.ipynb))
* summarised and presented findings
  
### Conclusions
To understand the financial impacts of losing students and the relative positions of the Russell Group universities, I began by visualising average PG fees. This shows that fees are generally around the £30-20k range, with a few universities charging more.

To understand the estimated financial risks, I visualised the average fee, multiplied by students from each country for 21/22. The largest amount of income by far comes from China and HK (£6.8bn).

![Average fee, multiplied by students from each country for 21/22](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Financial%20exposure%20by%20country.png "Average fee, multiplied by students from each country for 21/22")

Next, I visualised this on a university-by-university basis, showing the estimated revenue by country for each university. UCL has the highest international fee income, particularly from China, as do KCL, Manchester, Glasgow and Edinburgh.  Some universities, like LSE and Imperial, show varied intakes but still concentrated around a few countries. This dependence on specific countries poses financial risks. 

![Estimated revenue for each country by university](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/university%20income%20exposure%20by%20country.png "Estimated revenue for each country by university")

I also calculated the estimated income from Chinese student fees as a percentage of income. The visualisation shows Glasgow, Manchester, Sheffield, Southampton and UCL are more reliant on income from these students. 

![Estimaged revenue from Chinese student fees as a % of income](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Est%20income%20percent%20from%20Chinese%20students.png "Estimated income from Chinese student fees as a percentage of income")

In the case of a drop in international students, intense competition would arise to recruit from the smaller pool of international students, given the huge financial impact of losing this income.

### Impact
I reported that the data shows universities could mitigate risks by diversifying recruitment, especially in countries where they are underrepresented. Opportunities could exist in other markets, and I recommended further investigation of the data.

In case of a significant drop in international students, intense competition from other Russell universities is expected. From the data I have provided, it shows that this could be a substantial impact on income. Developing a data-driven recruitment strategy targeting specific student groups would be beneficial. 

### Possible improvemnts
#### Data refresh
This data relies on demographic and financial information from financial year 2021/2022. When I gathered this data it was the most recent information available. 

A refresh of this data would allow us to see how the situation has changed and potentially provide new insights.

#### Part-time fees
The fee information scraped on part-time courses (Mode of Study, PT/FT) was inconsistent due to the challenging structure of most university websites. The majority of course catalogues don't have separate pages for the part-time/full-time versions of their courses. For many programmes, the part-time fees were on the same page as the full-time fees, and in an inconsistent format, not available, or difficult to separate from the full-time course data.

Based on my sector knowledge, I know that almost all all part-time fees are 50% of the full-time fees. As a pragmatic estimate, I decided to remove any part-time lines from the data, and estimate the part-time fees as 50% of the full-time fee for all postgraduate courses. This might have reduced the accuracy of my data, which I communicated to stakeholders.

A future improvement would be to improve the web scraping step to correctly extract part-time fees and improve the accuracy of the data.
