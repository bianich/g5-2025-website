---
layout: default
title: "Classifier"
header_title: "Classifier"
header_type: hero #base, post, hero,image, splash
header_img: assets/images/markdown_t.webp
---

# Classifier
## Objectives

The main purpose of this project was to find hidden patterns and within the dataset. To achieve that regarding the sales, we built a dataset with many features that we tought could have an impact on the sale: data about the user, such as their location, about the item, such as its price, category, upload date, number of "likes" and about the sale - that is, whether it would be sold or not.

After a phase of data cleaning, several models were tested to achieve reliable performance. Initially, Decision Tree Classifiers (DTC) and Random Forests yielded an accuracy slightly above 70% with minimal parameter tuning. These models also provide valuable insight into feature importance: in the case of DTCs, the structure of the tree itself highlights the most influential feature, while Random Forests aggregate importance across al trees - for example, using mean decrease in impurity. 
Both models showed taht the number of likes an item receives is a key predictive factor, while other variables had a more limited impact. 

![Feature Importance](assets/images/Feature_Importance_RF.png)

The most accurate model was CatBoost, which reached an accuracy over 78%. The fact that it can natively process categorical variables made it particularly effective for this dataset, which includes fields such as city, region, brand and size which cannot be properly translated into numeric variables. 

![Feature Importance](assets/images/Feature_Importance_CatBoost.png)

CatBoost also offers built-in tools for feature importance analysis, allowing for the generation of visual explanations. Results show that the most relevant numerical features are the publication date and the item category - fitting with the idea that different items follow different trends and that the more an item stays online, the more likely it is to be sold or removed - followed by the number of likes.


---

{% include slider.html data="sliders" %}