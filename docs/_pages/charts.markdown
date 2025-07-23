---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
title: "Charts"
subtitle: "Like 2 visualize"
vega: true

header_type: hero #base, post, hero,image, splash
header_img: assets/images/general/Header.png
header_title: "Charts"
---
<br>

This section presents a series of interactive visualizations that explore user behavior and item listing dynamics on the platform of reference, with a specific focus on the Italian market.
 
Through geographic maps, seller classifications, and performance indicators, the charts provide insights into:
 
- **Regional activity levels**, adjusted for population differences;
 
- **Seller profiles**, from occasional users to structured high-volume sellers;
 
- **Key metrics** such as selling rate, engagement through likes, and listing effectiveness.
 
The visual tools are fully interactive: **hovering or selecting regions and seller classes** reveals detailed statistics, enabling an in-depth exploration of how the platform is used across different contexts.

<br>

<h2 style="width: 100%; text-align: center">
    Item publications across Italy
</h2>

<br>

This chart shows the geographic distribution of items published by Italian users, grouped by region and colored on a logarithmic scale to highlight large volume differences.\
**Hovering over a region** reveals stats such as number of users, items, and items sold.
Location data was inferred via reverse geocoding from scraped latitude and longitude coordinates. Some users couldn't be geolocated, so their items are not included.
**Campania, Lombardy, and Sicily** lead with over 30,000 items each, followed by Lazio, Puglia, and Tuscany. **Val d'Aosta, Molise, and Basilicata** show the lowest volumes.
These differences likely reflect both population size (covered in the next chart) and broader factors like digital access and cultural attitudes toward second-hand markets.

<br>

<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/1_map_ita.json" style="width: 100%; height: 100%"></vegachart>
</div>


<br>
<br>


<h2 style="width: 100%; text-align: center">
    Activity intensity by region
</h2>

<h6>
    Items per 1000 inhabitants, with % sold
</h6>

<br>

This chart shows the intensity of user activity on the platform, measured as the number of items published per 1,000 inhabitants in each Italian region. Next to each bar, the percentage of sold items is also displayed.
 
This chart offers a more refined view of regional behavior, filtering out demographic effects and highlighting both user engagement and sales effectiveness.
 
Indeed, this visualization normalizes item volumes by population size (ISTAT data, January 2025), offering a fairer comparison across regions.
 
**Campania** ranks highest in publication intensity, followed by **Sicily**, **Tuscany**, and **Lazio**. These regions stand out not only for their absolute numbers but also for their high engagement relative to population size.
 
Conversely, regions like **Molise**, **Val d'Aosta**, and **Basilicata** show a much lower rate of publication per capita, consistent with the patterns observed in the previous chart.
 
The percentage label on each bar indicates how many items were actually sold. In some regions (e.g. Sicily, Tuscany), high activity is matched by strong sales performance, while others show lower conversion rates.

<br>

<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/2_region_activity.json" style="width: 100%; height: 100%"></vegachart>
</div>

<br>
<br>
<br>


<h2 style="width: 100%; text-align: center">
    Seller distribution by class
</h2>

<br>

The distribution of items published per seller is highly skewed: **50% of users publish only 1 item**, and **75% no more than 2**, with an average just above 2. However, a small number of sellers post hundreds or even thousands of items, with a maximum of 3,702.
 
Given this imbalance, we grouped sellers into **four** **distinct classes** to better understand user behavior and distinguish casual users from more structured or professional ones:
 
- **Casual & Low Seller**: 1--5 items → the vast majority of users (95.8%);
 
- **Mid Seller**: 6--30 items → moderately active (3.9%);
 
- **Power Seller**: 31--250 items → structured sellers (0.21%);
 
- **Super Seller**: over 250 items → likely professional use (0.004%).
 
The interactive chart displays the **total number of items published** by each class. **Clicking on a bar** filters the data and updates the table on the right, which displays key statistics: number of users, items sold, selling rate, total likes, and average likes per sold item.  
 
This grouping helps reveal how each seller type contributes to the platform in terms of activity, conversions, and engagement. It also offers insights into user segmentation, sales performance, and behavioral patterns, helping differentiate casual from commercial use.

<br>

<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/3_seller_classes.json" style="width: 100%; height: 100%"></vegachart>
</div>

<br>
<br>
<br>


<h2 style="width: 100%; text-align: center">
  Item distribution by seller class
</h2>

<br>

This interactive chart links regional activity to seller types. **The map** shows the total number of items published per region; **clicking a region** filters the **bar chart** on the right, which displays how item volume is distributed across seller classes.

This tool **allows** users to:
- **Explore regional differences in seller composition**;
- **Understand whether high publication volumes are driven by many casual sellers or a few high-volume sellers**;
 

<br>

<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/4_smart_chart.json" style="width: 100%; height: 100%"></vegachart>
</div>

<br>
<br>
<br>


<h2 style="width: 100%; text-align: center">
    Likes per sale by class
</h2>
<br>

This chart shows the **average number of likes per item sold**, offering a view of **engagement quality** across seller classes. It should be read in combination with previous statistics, such as selling rate and total items listed.
 
**Super Sellers** receive the highest likes per sale, indicating strong visibility and well-presented listings. However, as seen earlier, their **selling rate is lower than that of Casual Sellers**, suggesting they may use the platform more as a **showcase** than a channel for effective selling.
 
**Power Sellers** also perform well, confirming an optimized selling approach. In contrast, **Casual Sellers**, despite higher conversion rates, receive the **least engagement per item sold**, likely due to limited presence in terms of time or listing quality.

<br>

<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/5_likes_chart.json" style="width: 100%; height: 100%"></vegachart>
</div>
