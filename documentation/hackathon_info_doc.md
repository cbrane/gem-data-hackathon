**The Butler Institute GEM Data Hackathon 2025** 

**The challenge:** 

“Offer a comprehensive analysis of the diverse characteristics of American entrepreneurs, including aspects such as their backgrounds, co-founder dynamics, industry preferences, impact on employment, market selection strategies, ambitions, and factors influencing their decision to discontinue their ventures. Utilize all available variables from the Global Entrepreneurship Monitor (GEM) dataset and feel free to enhance your analysis by integrating it with additional relevant datasets.” 

**The Deliverable:** 

Create 3 slides that represent your findings.  

Slide 1 and 2: Your results 

Slide 3: Explanation of your methods 

Email the deliverable to butlerinstitute@babson.edu by 9 p.m. ET on Sunday, March 9, 2025\.  Send details of your team members (if you have any) – names and emails with your submission  

**Important Dates:** 

`o` The info session: **February 24, 2025, 5 p.m. ET (virtual)** 

`o` Submit your deliverable (3 slides) by **Sunday, March 9, 9 p.m. ET**  

`o` Presentation and Award Ceremony: **Tuesday, April 8** 

**Rules for Forming Teams:** 

Each team should have no more than four members. 

All team members must be Babson students. 

Teams can have a mix of undergraduate and graduate students or can comprise only  undergraduate or graduate students. 

**No Software Restrictions:** 

Teams are allowed to use any software package they want to clean, analyze, and visualize data.  They can also use any software package to create the infographic or write their statement.

1   
**The Data for This Hackathon:** 

The dataset for this hackathon is a compiled version of the United States of America Samples of the Global Entrepreneurship Monitor (GEM) Dataset, from 2015 through 2021 (seven years). 

The dataset is collected annually from a nationally representative random sample of individuals,  aged 18 to 64\. The individuals vary from one year to another, but (much of) the questionnaire  stays the same. With seven years of data, you have access to data of over 15,800 observations. 

**How to Access the Data and More:** 

This is the link to the data and accompanying files. 

The link directs you to SharePoint where you need to log in with your Babson credentials to  access a folder containing the data in CSV format as well as this handout in PDF. 

Practically any statistical software package or visualization tool can import CSV files, but if you  need the data in SPSS format, you can use the SPSS or Stata files. 

**The Variables in the Data:** 

**The Entrepreneurship and Established Business Variables:** 

GEM defines an entrepreneur as someone who is currently trying to start a business or has  started a business in the last 3.5 years and is paying wages. There is a binary variable in the  dataset, called TEA, that captures such people. When TEA \= 1, the respondent is an  entrepreneur according to the GEM definition, and when TEA \= 0, she/he is not an  entrepreneur. 

GEM defines an Established Business Owner-Manager as someone who owns and manages a  business that was started more than 3.5 years ago. The binary variable ESTBBUSO captures such  people. When ESTBBUSO \= 1, the respondent is an Established Business Owner-Manager, and  when it is zero, she/he is not an Established Business Owner-Manager. 

**The Weight Variables:** 

Each observation has weights in the data. You should always consider the weight of  observations when you do any statistical analysis, such as calculating the averages, etc. The weight variable is WEIGHT\_L.

2   
**Other Variables:**

| Variable Name  | Description  | What the discrete values mean |
| :---- | ----- | ----- |
| yrsurv  | Year of the survey  | 2015 through 2021 |
| gender  | What is your gender? | 1 is for male  2 is for female |
| age9c  | Age range | 2 is for people aged 18-24  3 is for people aged 25-34  4 is for people aged 35-44  5 is for people aged 45-54  6 is for people aged 55-64  7 is for people aged 65-74 |
| hhsize | How many members make up your  permanent household, including you? | \-2 is for “Refused”  \-1 isfor “Don’t know”   1-44 |
| ushhinc  | Household income bracket | 1 is for Under $15,000   2 is for $15,000 to under $25,000  3 is for $25,000 to under $35,000  4 is for $35,000 to under $50,000  5 is for $50,000 to under $75,000  6 is for $75,000 to under $100,000   7 is for $100,000 to under $150,000  8 is for $150,000 to under $200,000  9 is for Over $200,000 |
| usreduc | What is the highest level of education  you have completed? | 1 is for None/Less than High School  2 is for Some High School   3 is for Completed High School  4 is for Some College/University  5 is for Completed College/University  6 is for Degree Graduate (Master's or  PhD) |

3 

| race  | Primary Race | \-2 Refused  \-1 Don’t know  1 White  2 Black  3 Hispanic  4 Other |
| :---- | :---- | :---- |
| region  | US regions based on FEMA regions  (https://www.fema.gov/about/organizat ion/regions)  | 1 New England   2 New York \-New Jersey   3 Mid-Atlantic   4 Southeast   5 Great Lakes   6 South   7 Central Midwest   8 Mountain and Plains  9 Pacific Southwest   10 Pacific Northwest |
| knowent | Do you know someone personally who  started a business in the past 2 years? | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |
| opport | In the next six months, will there be  good opportunities for starting a  business in the area where you live? | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |
| suskill | Do you have the knowledge, skill and  experience required to start a new  business? | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |
| fearfail | Would fear of failure prevent you from  starting a business? | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |
| nbgoodc | In the U.S., most people consider  starting a new business a desirable  career choice. (Not collected in 2015\) | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |
| nbstatus | In the U.S., those successful at starting  a new business have a high level of  status and respect. (Not collected in  2015\) | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |

4

| nbmedia | In the U.S., you will often see stories in  the public media and/or internet about  successful new businesses. (Not  collected in 2015\) | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |
| :---- | :---- | :---- |
| TEA | Involved in Total early-stage   Entrepreneurial Activity (this is the  most important measure of  entrepreneurship in the GEM data) | \-2 Refused  \-1 Don’t know  0 is No  is Yes |
| ESTBBUSO | Owner-Manager of an Established  Business (A business older than 3.5  years) | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |
| TEAOWNER | Number of owners of the early-stage business | NULL when value does not exist. |
| EB\_OWNER | Number of owners of Established Business | NULL when value does not exist. |
| TEAJOBNOW | Current Number of Employees for those TEA Businesses | NULL when value does not exist. |
| EB\_JOBNOW | Current Number of Employees for Established Businesses | NULL when value does not exist. |
| TEAJOBGR | Expected job growth (persons) in 5 years for TEA businesses | NULL when value does not exist. |
| EB\_JOBGR | Expected job growth (persons) in 5 years for Established Businesses | NULL when value does not exist. |

5

| TEANEWPR | Do all or some of your potential  customers consider this product or  service new and unfamiliar (TEA  Business)? (Only in 2015-2018) | \-2 Refused  \-1 Don’t know  1 Yes  2 No |
| :---- | :---- | :---- |
| TEANEWPROD | Are any of your products or services  new to people in the area where you  live, or new to people in your country,  or new to the world (TEA Business)?  (Only in 2020 & 2021\) | \-2 Refused  \-1 Don’t know   1 No, not new product or service   2 New to people in the area where you  live    3 New to people in your country   4 New to the world |
| TEAEXP4C | What percentage of your annual sales  revenues usually come from customers  living outside your country? Is it more  than 90%, more than 75%, more than  50%, more than 25%, more than 10%,  or 10% or less (TEA Business)? | \-2 Refused  \-1 Don’t know  1 More than 75%  2 25 to 75%  3 Under 25%  4 None   NULL when value does not exist. |
| EB\_EXP4C | What percentage of your annual sales  revenues usually come from customers  living outside your country? Is it more  than 90%, more than 75%, more than  50%, more than 25%, more than 10%,  or 10% or less (Established Business)? | \-2 Refused  \-1 Don’t know  5 More than 75%  6 25 to 75%  7 Under 25%  8 None   NULL when value does not exist. |
| TEAISIC4\_1D  | The industry of the TEA business | \-2 NOT CLASSIFIED/MISSING   1 AGRICULTURE,FORESTRY,FISHING  2 MINING,CONSTRUCTION   3 MANUFACTURING   4 UTILISATION, TRANSPORT, STORAGE  5 WHOLESALE TRADE   6 RETAIL TRADE, HOTELS &   RESTAURANTS   7 INFORMATION AND   COMMUNICATION 8 FINANCIAL  INTERMEDIATION, REAL ESTATE  9 PROFESSIONAL SERVICES   10 ADMINISTRATIVE SERVICES   11 GOVERNMENT, HEALTH,   EDUCATION, SOCIAL SERVICES   12 PERSONAL/CONSUMER SERVICE  ACTIVITIES |

6

| EB\_ISIC4\_1D  | The industry of the TEA business | \-2 NOT CLASSIFIED/MISSING   1 AGRICULTURE, FORESTRY, FISHING  2 MINING, CONSTRUCTION   3 MANUFACTURING   4 UTILISATION, TRANSPORT, STORAGE  5 WHOLESALE TRADE   6 RETAIL TRADE, HOTELS &   RESTAURANTS   7 INFORMATION AND   COMMUNICATION 8 FINANCIAL  INTERMEDIATION, REAL ESTATE  9 PROFESSIONAL SERVICES   10 ADMINISTRATIVE SERVICES   11 GOVERNMENT, HEALTH,   EDUCATION, SOCIAL SERVICES   12 PERSONAL/CONSUMER SERVICE  ACTIVITIES |
| :---- | :---- | :---- |
| futsup | Are you, alone or with others,   expecting to start a new business,  including any type of self-employment, within the next three years? | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |
| discent | Have you, in the past 12 months, sold,  shut down, discontinued or quit a  business you owned and managed, any  form of self-employment, or selling goods or services to anyone? | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes  NULL when value does not exist. |
| exbuscon | Did the business continue its business  activities after you quit? | \-2 Refused  \-1 Don’t know  1 is Yes  2 is No  3 is Business continued but activities  changed  NULL when value does not exist. |
| busang | Have you, in the past three years,  personally provided funds for a new  business started by someone else,  excluding any purchases of stocks or mutual funds? | \-2 Refused  \-1 Don’t know  0 is No  1 is Yes |
| bafund | Approximately how much, in total,  have you personally provided to these  business start-ups in the past three  years, not counting any investments in  | \-3 Have not provided funds  \-2 Refused  \-1 Don’t know |

7

|  | publicly traded stocks or mutual funds? | NULL when value does not exist. |
| :---- | :---- | :---- |
| barel  | What was your relationship with the  person that received your most recent  personal investment? Was this a... | \-2 Refused  \-1 Don’t know  1 Close family member, such as a  spouse, brother, child, parent, or  grandchild  2 Some other relative, kin, or blood  relation  3 A work colleague  4 A friend or neighbor, or  5 A stranger with a good business idea 6 Other  NULL when value does not exist. |
| WEIGHT\_L  | Observation Weights |  |

8