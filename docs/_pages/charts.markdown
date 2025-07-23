---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
title: "Charts"
vega: true

header_type: hero #base, post, hero,image, splash
#header_img: assets/images/altair-gallery.png
header_title: "Charts"
---
## INTRODUZIONE

<h2 style="width: 100%; text-align: center">
  Geographical distribution of item publications on platform of reference (Italy)
</h2>
<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/1_map_ita.json" style="width: 100%; height: 100%"></vegachart>
</div>

<h2 style="width: 100%; text-align: center">
  Regional activity intensity on platform of reference (items per 1000 inhabitants, with % sold)
</h2>
<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/2_region_activity.json" style="width: 100%; height: 100%"></vegachart>
</div>

<h2 style="width: 100%; text-align: center">
  Seller distribution in Italy by class
</h2>
<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/3_seller_classes.json" style="width: 100%; height: 100%"></vegachart>
</div>

<div class="full-width-wrapper">
    <h2 style="width: 100%; text-align: center">
      Item distribution by seller class in selected region
    </h2>
</div>

<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/4_smart_chart.json" style="width: 100%; height: 100%"></vegachart>
</div>

<h2 style="width: 100%; text-align: center">
  Average likes per sold item by seller class
</h2>
<div style="width: 100%">
<vegachart schema-url="{{site.baseurl}}/assets/charts/5_likes_chart.json" style="width: 100%; height: 100%"></vegachart>
</div>



