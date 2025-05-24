# ConstructionTimeStudy
How accurate can your quotes on time be for each construction project? 
## Motivation 
Time is money; this adage is well-understood in industry. Your clients want quotes and, if the project is big enough, the locals want to know how long they'll have to deal with these traffic lights. Using the free dataset found at https://www.kaggle.com/datasets/claytonmiller/construction-and-project-management-example-data/data, I'm setting out to explore what factors contribute to the longest construction time frames. If the data structure is there, I may be able to create a better formula for calculating construction time, to help project managers and consultants present better quotes. And of course, this comes with the caveat of data distribution: there may be a central tendency to the data (e.g. "on average, it takes X project type Y weeks to complete."), but there is also, always, a variance (e.g. "Y is the average, but X project type hits a range of 50% less or 50% more than Y). If the variance is large, there may be an argument for each of the following two approaches to price quoting: 
* Quote them the average, but charge them what the project actually costs at the end of the day
* Quote and charge them the average, on the expectation that for some projects you'll lose money, and for others, you'll gain.

... but that decision is another project entirely. :) 

## Exploratory Data Analysis 1: Looking at someone else's summary 
There's really no point in me making my own initial reports on the structure and distribution of the data, since many people on kaggle have already put together intial analytics displays. For example, I'm using the PowerBI display here (https://app.powerbi.com/view?r=eyJrIjoiOTZkN2M5MzItNmNkZi00MTdmLThhMTgtMDAxY2Y3MGI4MjI5IiwidCI6IjMyNTNmZjdjLTI0NmMtNGFjNi05ZTE5LTEyYzc4ZGZjM2NjMSIsImMiOjl9) to get a sense of what data fields look like; thanks to Jason Rymer's Power BI report, I can see the data contains: 
* The construction tasks all appear to take place within the British Iles, with many in the Republic of Ireland. 
* Various project types: Civil, Data Centre, Defence, Hospital, Industrial, Pharmaceutical, Residential, Retail
* Various categories of tasks and forms (this is administrative project data, rather than live, physical data), namely: Design, Project Management, Quality Assurance, Health and Safety, Site Management, and Subcontractor
* As my focus is not on individual tasks, but on project time, I'm keen to note that projects in the PowerBI Exploratory Data Analysis report are helpfully named and numbered, e.g. "Civil Project 1," although this may have been data cleaning Jason Rymer produced and I will have to replicate for myself.
* By filtering, I can see how many tasks were filed against each project, as well as against each category of project. For instance, Hospital projects had 189 tasks associated with their design team, and 1134 tasks associated with Health and Safety.
* I can also see the dates provided in the PowerBI report run from January 2020 to October 2021, and are split between dates when forms were created, and dates when tasks were created. In the interest of my reporting question, I need to hope this data also provides some indication of overall project start and completion dates, even if that is something to extrapolate.

## Exploratory Data Analysis 2: Examining the backing data for myself. 
