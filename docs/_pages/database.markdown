---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: "Database"
vega: true
header_type: hero #base, post, hero,image, splash
#header_img: assets/images/header.svg
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

