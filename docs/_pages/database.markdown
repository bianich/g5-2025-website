---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: "Database"
vega: true
header_type: hero #base, post, hero,image, splash
header_img: assets/images/general/Header.png
header_title: "Database"

---

## Dataset Collection

We adopted a two-phase web scraping approach:

### Phase 1 (April 15 – June 30)
> Daily collection of new listings including product metadata

### Phase 2 (July 7)
> Status check for previously scraped items (sold, available or missing)

---

## Database Schema  

![DataBase Schema](assets/images/database/database-schema.jpeg)

---

## Exploratory Data Analysis

As of July 7, we had collected:

- **Over 700,000 instances of items**
- **560,770 unique items**  
- **Around 360,000 users**  
- **251,070 sold items** (~30% sold rate)

This dataset enabled us to estimate the **probability of sale** and analyze the influence of item features on the resale outcome.

## Features
 
The study aimed to decode the behavior of digital second-hand sellers. Using web scraping techniques, we collected data on:
 
- Price  
- Label  
- Size  
- Condition  
- Category  
- Description  
- Upload date  
- Number of likes  
- Seller’s location (when available)  
 
These features, obtained also through feature engineering, helped create a structured dataset that could reveal the hidden mechanics of resale success.

---

Database schema 

In building our database we addressed the problem of handling all the data we could gather from the platform. 

We decide to discard some metadata that was hard to handle/understand and was simply a boolean value. 

We noticed early that the same item could be recovered multiple times and therefore developed a database schema that accounted for this: 

A main table containing all the permanent attributes of the item (title, id, description, relative user, upload date etc)
A table for the user, which stores all their information that are relevant to the research (we discarded data that was found to be irrelevant and could pose a databreach issue)
A table for storing information about the main image of the item 
A table that contains the instance of the item with all the attributes that could change over time (price, number of likes etc)

In the analysis phase, we also checked how many items were recovered multiple times and if some changing features could be somehow relevant to our research, but these were a minority and had a small - albeit not entirely uselss - impact on the outcome of the classifier