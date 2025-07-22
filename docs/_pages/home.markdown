---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: "Home"
vega: true
header_type: hero #base, post, hero,image, splash
header_img: assets/images/header.svg
header_title: "Like to Resell"

---

# Like 2 Resell  

---

## Abstract

The rise of the second-hand online market in a world increasingly focused on sustainability and circular fashion, specialized platforms are reshaping the way we buy and sell clothes.

Our research shows a **clear result**:  
**Likes are a crucial predictor of whether an item will be sold.**

To investigate this, we collected over **560,000 product listings** and data on **more than 360,000 users**, focusing on the men’s and women’s clothing and footwear categories. This project was born to understand the dynamics of the second-hand market, identify selling strategies, pricing trends, and the spatial-temporal distribution of used items.

---

## Our story

“Men go for brands,” Simone Buccioni told us — known online as @Majinbux, a reseller of streetwear labels like Stüssy and Carhartt WIP. The implicit message is: brands matter! Guided by that claim, we went looking for confirmation. But what we found - on the basis of the data at our disposal- told us a different story.
Brand a poor predictor of sales, probably because it's often victim of typos: topping the list of most-used "brands" is UOMO — simply the Italian word for “man.”
What seems to matter more are the social-related features, such as user engagement and visibility on the platform, rather than item-related characteristics like the presence of a brand logo. These patterns suggest that how an item circulates within the community may influence its chances of selling more than its intrinsic features.
So: perhaps less focus on (mistytiped) logos, and more on social dynamics.
Words matter too. Text analysis of product descriptions shows that buyers prefer listings that say “never worn” or “in excellent condition.” Buyers are after the least-used secondhand — something that feels almost new.
The brand alone isn’t enough. What you need is visibility, approval— and not a wrinkle in sight.

---

## Project Overview

With this project, the aim is to explore the behavior of users selling second-hand items online. Using web scraping techniques, we gathered information on:

- Price  
- Label  
- Size  
- Condition  
- Category  
- Description  
- Upload date  
- Number of likes  
- Seller’s location (when available)

Our goal was to create a clean, structured dataset to analyze patterns of interaction and predict factors contributing to successful resale.

---

## Dataset Collection

We adopted a two-phase web scraping approach:

### Phase 1 (April 15 – June 30)
> Daily collection of new listings including product metadata

### Phase 2 (July 7)
> Status check for previously scraped items (sold, available or missing)

---

## Database Schema  

![b](/workspaces/g5-2025-website/docs/assets/images/Logo_SoBigData_ITA_560_X_100.png)

---

## Exploratory Data Analysis

As of July 7, we had collected:

- **Over 700,000 instances of items**
- **560,770 unique items**  
- **Around 360,000 users**  
- **251,070 sold items** (~30% sold rate)

This dataset enabled us to estimate the **probability of sale** and analyze the influence of item features on the resale outcome.


