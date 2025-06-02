---
layout: post
tags: [powerbi]
title: Learning PowerBI
---

Plant Co. Performance Dashboard.  
An example dataset from a fake company that sells real plants.  
The dashboard is interactive, so please click through to satisfy your curiosity (tip: the embedded dashboard can be resized to fit your full screen in the lower right corner).  

<iframe 
    title="Plant Co Performance Report" 
    width="788" height="505" 
    src="https://app.powerbi.com/view?r=eyJrIjoiOWJmMTRmMjgtNWNiNC00ODkxLWJjMTItMDEyYjc0YzNlOTRlIiwidCI6ImQxMjE2YWM4LWFiOGQtNDg0ZC1hOTg2LTlmMGRmMmMxMjBmMCIsImMiOjJ9&pageName=2195c7825b6c3b144e2f" 
    frameborder="0" 
    allowFullScreen="true">
</iframe>

<br>

*Example Analysis:*
<h2 style="margin-top: 0" > October 2023 was less profitable than 2022 by $0.15M:</h2>
Focusing on the Gross Profit Year to Date (YTD) vs Prior Year to Date (PYTD) Waterfall Chart for 2023.  
It looks like October was our worst performing month relative to last year - we want to know why so we can make decisions to increase profitability next year.  

First, hover over and then click on the "Click to turn on Drill down" arrow (1). Then click on the red bar for October (2).  
<img src="/assets/images/learning-powerbi/1_DrillDown.png" >

This waterfall chart has drill down information about country and product - when clicking on October, the first layer of detail shows us a list of all countries and their relative gross profit between 2023 and 2022. Here we can see 79k of the $148.41k less profit in 2023 came from accounts in China. This is reflected across all visuals in the dashboard as well and hovering over will show you more information.
<img src="/assets/images/learning-powerbi/2_Countries.png">

Drilling further down by clicking on china we get a grouping by product category: Indoor, Landscape, and Outdoor.  
It looks like in 2023 we lost money on Outdoor and Landscape products but making small returns on Indoor products vs 2022. Remember, at this point we are drilled down on "Gross Profit YTD (2023) vs PYTD (2022) for October 2023, from China."
<img src="/assets/images/learning-powerbi/3_ProductGroup.png">

Focusing in further on Outdoor we can get an idea of which specific plants are experiencing lower gross profits in 2023. For example, 4 of these products had $9-10k less gross profits in 2023 than 2022 - something definitely worth looking into more. (and we would repeat this for Landscape).
<img src="/assets/images/learning-powerbi/4_Products.png">

To get a final list of the products we can just request a table view by right clicking on the graph. Tip: Use portrait or landscape view to  (because, yeah, reading long names from angled bar titles isn't great) 
<img src="/assets/images/learning-powerbi/5_Tabled.png">


Remember - this does not mean the products LOST money, it just means relative to last year they made less. So, maybe the products are falling out of favor in china, or maybe in 2022 there was an issue with these. It could also mean that the products are more perrenial, and in 2022 companies bought all the needed. So, when thinking about the next year we could update the catalog to offer products that are in more demand and produce less of the products out of demand for the chinese market.  
We could also look deeper at the account profitability segments, and try to advertize to the accounts related that are low value YTD, but high GP% (bottom right figure of the dashboard).

<br>  


*How this was made:*
<h2 style="margin-top: 0" > Project Introduction </h2>
This project was created following Mo Chen's Power BI [Tutorial][1].  

Data sources:  
- Excel Workbook with 3 Sheets:
    1. 

Power Query:  
- Data was imported into Power Query for Transformation.
- Column names were cleaned and deduplication was run on any primary keys.
- Table names were cleaned and identified as FACT or DIM tables

DAX:  
- Slicers:  
- Measures

Visualizations:  
- Area Chart
- Waterfall
- Stacked Bar with Line
- Scatterplot with segmentation

Analysis

[1]: https://www.youtube.com/watch?v=BLxW9ZSuuVI&t=92s