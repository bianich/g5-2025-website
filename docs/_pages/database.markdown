---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: "Database"
vega: true
header_type: hero #base, post, hero,image, splash
header_img: assets/images/general/Header.png
header_title: "Database"
subtitle: "Like 2 collect"


---
<br>
## Dataset Collection
<br>
We adopted a two-phase web scraping approach:

- **Phase 1 (April 15 – June 30)**:
<br>
Daily collection of new listings including product metadata.

- **Phase 2 (July 7)**:
<br>
Status check for previously scraped items (sold, available or missing).

<br>
<br>

## Database Schema  
<br>

In building our database we addressed the problem of handling all the data we could gather from the platform. 

We decide to discard some metadata that was hard to handle/understand and was simply a boolean value. 

We noticed early that the same item could be recovered multiple times and therefore developed a database schema that accounted for this:

<br>

![DataBase Schema](assets/images/database/database-schema.jpeg)

<br>

A main table containing all the permanent attributes of the item: title, id, description, relative user, upload date etc.
A table for the user, which stores all their information that are relevant to the research, discarding data that was found to be irrelevant and could pose a data breach issue.
A table for storing information about the main image of the item, in the smallest size available.
A table that contains the instance of the item with all the attributes that could change over time, such as price and number of likes.

Concerning the last table, in the analysis phase we checked how many items were recovered multiple times and if some changing features could be somehow relevant to our research, but these were a minority and had a small, albeit not entirely useless, impact on the outcome of the classifier.

<br>
<br>

## Exploratory Data Analysis

<br>

As of July 7, we had collected:

- **789,850 instances of items**
- **560,770 unique items**  
- **301,562 users**  
- **251,070 sold items** (~44% sold rate)

This dataset enabled us to estimate the **probability of sale** and analyze the influence of item features on the resale outcome.

<br>

## Features

<br>
 
The study aimed to decode the behavior of digital second-hand sellers through meaningful data features. Using web scraping techniques, the main features collected were:
 
- Price  
- Label  
- Size  
- Condition  
- Category  
- Description  
- Upload date  
- Number of likes  
- Seller’s location (when available)  
 
These features, which were later refined by means of feature engineering, helped create a structured dataset that could reveal the hidden mechanics of resale success.

<br>
<br>