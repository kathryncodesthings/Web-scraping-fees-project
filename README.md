# Data Projects

These projects showcase my technical data skills and my ability to solve real business problems. Each one starts with a practical question from stakeholders, uses data analysis to test assumptions, and ends with clear, actionable insights.

Where relevant, I include links to the full analysis and code.

---

## Web scraping and analysis of university fees

**Skills demonstrated:** stakeholder engagement; problem definition; Python (pandas, numpy, matplotlib, BeautifulSoup); web scraping; data cleaning and transformation; statistical analysis; outlier handling; data visualisation; communicating insights to non-technical audiences.

### Business question
UK universities are financially dependent on international students. In 2021/22, around 19% of sector-wide income came from overseas students, with a particularly high concentration from China and Hong Kong. Regulators have expressed concerns that this creates financial risk should student numbers from these countries decrease.

This project assesses:
* How concentrated international fee income is by country
* How exposed UCL is relative to similar universities
* Which institutions face the greatest financial risk from a drop in international students

The analysis focuses on UCL and 23 comparable institutions.

### Approach

#### Project overview
Given time and data constraints, I focused on UCL’s closest peer group rather than all 160+ UK universities. I selected the Russell Group, a set of research-intensive universities that compete for the same international students.

This ensured the analysis was:
* Relevant to stakeholders
* Comparable across institutions
* Deliverable within realistic constraints

The overall workflow was:
1. Define requirements with stakeholders
2. Obtain and combine multiple data sources
3. Clean and explore the data
4. Analyse and visualise results
5. Draw conclusions and communicate findings

#### Data

##### Web scraping
I scraped postgraduate fee data directly from 23 university websites using BeautifulSoup, extracting information from raw HTML.

This required:
* Navigating inconsistent page structures
* Handling missing and poorly formatted data
* Writing custom parsing logic to extract usable values

An example of this work is available here: [here](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Data%20Scraping%20-%20Bristol%20UG%20course%20data.ipynb). 

> Note that this code is from 2024: the university website has since been updated and the code will no longer work without modification.

##### Other data
I used public data  from HESA (the UK Higher Education Statistics Agency), which publishes statistics for UK universities:
* Student demographics
* University income

This allowed me to estimate fee income by country and by institution.

### Juptyer Notebooks
Samples from relevant notebooks are linked below.
* Web scraping fee data ([**example** code](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Data%20Scraping%20-%20Bristol%20UG%20course%20data.ipynb))
* Cleaning fee data and intitial visualisation of fee data ([sample code](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Fee%20data%20cleaning%2C%20exploration%20and%20visualisation%20part%201.ipynb))
* Visualising student demographic data from HESA ([sample code](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Visualise%20students%20by%20country.ipynb))
* combined and visualised data to show estimates of different universities' reliance on fees from overseas students ([sample code](https://github.com/kathryncodesthings/Web-scraping-fees-project/blob/main/Fee%20data%20cleaning%20and%20combination%20with%20income%20and%20student%20demographic%20data.ipynb))
  
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
The analysis shows that a small number of countries account for a disproportionate share of fee income, and a decline in students from those countries would have a material financial impact. Universities would likely face intense competition to recruit from a smaller international student pool.

I recommended that financial risk could be reduced by diversifying international recruitment, particularly in countries where they are currently underrepresented. I also suggested further segmentation to identify specific growth opportunities.

This project demonstrates my ability to:
* Combine messy, real-world data from multiple sources
* Make pragmatic assumptions and clearly communicate limitations
* Translate complex analysis into strategic, data-driven recommendations

### Possible improvemnts
#### Data refresh
This data relies on demographic and financial information from financial year 2021/2022. When I gathered this data it was the most recent information available. 

Refreshing the analysis with newer data would show whether exposure has increased or reduced in recent years.

#### Part-time fees
The fee information scraped on part-time courses (Mode of Study, PT/FT) was inconsistent due to the challenging structure of most university websites. The majority of course catalogues don't have separate pages for the part-time/full-time versions of their courses. For many programmes, the part-time fees were on the same page as the full-time fees, and in an inconsistent format, not available, or difficult to separate from the full-time course data.

Based on my sector knowledge, I know that almost all all part-time fees are 50% of the full-time fees. As a pragmatic estimate, I decided to remove any part-time lines from the data, and estimate the part-time fees as 50% of the full-time fee for all postgraduate courses. This might have reduced the accuracy of my data, which I communicated to stakeholders.

A future improvement would be to improve the web scraping to correctly extract part-time fees and improve the accuracy of the data.
