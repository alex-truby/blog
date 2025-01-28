+++
date = '2025-01-28'
draft = false
description = "Where beach meets desert."
featured_image = "/images/baja_water/sandy_arroyo.jpg"
categories = ['water', 'tech']
categories_weight = 44
tags = ['earth-observation', 'water-resources']
tags_weight = 22
title = 'Water in Baja California Sur'
+++

The Baja California Peninsula is a dry, desolate, dusty, and beautiful desert. Driving the length of the peninsula spans just over a thousand miles from Tijuana to Cabo San Lucas (1,040 miles, to be exact). That’s almost the same distance as driving from San Diego to Portland, Oregon. Having driven both stretches in December 2024, I can tell you the variety in landscapes along each route differs drastically. From Oregon to San Diego, you feel as if you’re passing through three or four different countries—maybe even worlds. There’s the rugged Oregon coast, the towering redwoods of Northern California, the rolling hills of wine country, and the Mediterranean-like landscape of Southern California. Once you cross the border into Baja, however, most signs of moisture dissipate, and you’re left with a rugged, dry landscape for the rest of the drive. It doesn’t take long for your vehicle, clothing, and skin to take on the sandy color of the desert.

Parts of this desert landscape look like they came straight out of a Dr. Seuss book—or perhaps served as his inspiration. The landscape is dotted with plant species that require little to no water to thrive. The giants of the peninsula—the cardón cacti—are impossible to miss. The vine-like ocotillo stretch toward the sky, sometimes reaching the height of a two-story building. Elephant trees and desert brush gather in patches, creating fields of comparative green against the underlying, ever-present tan. Yet, as you make your way down Highway 1 toward Baja California Sur (BCS), one thing is notably absent: water.

Dry arroyos (seasonal riverbeds) weave across the landscape. BCS receives an average of just six inches of rainfall per year, compared to the 30 inches per year seen across the rest of Mexico [1].

Water scarcity defines the very character of BCS, a region where the interplay of its unique flora, arid landscapes, and scarce rainfall paints a vivid picture of life adapted to extremes.

This is what makes BCS so damn special. 

But understanding water availability—and the broader impacts of drought—requires more than what the eye can see. Ever since entering the climate tech space, I’ve been fascinated by the insights that Earth Observation (EO) datasets can provide. How incredible is it that we now have unified datasets, often covering the entire planet, at our fingertips? I wanted to use my curiosity about water stress in BCS as an opportunity to dabble a bit more in EO myself.

In the following sections, I’ll explore datasets from NASA, NOAA, and other resources available in Google Earth Engine (GEE) to tell the story of water stress in BCS over the past decade. Specifically, I’ll analyze the following indicators: **precipitation, groundwater storage, land surface temperature, vegetation health, and human activity through nighttime radiance**. When combined, these metrics can offer insights into the drivers of the well-documented water stress in BCS. Because I used global datasets available in GEE, the time period for analysis was limited by data availability for each metric. To accommodate this, my analysis covers the years 2013–2023.

This is not an exhaustive or deep-dive study into drought conditions in the region but rather a high-level overview of trends over the last ten years. It’s a snapshot of where we are now, where trends are heading, and what that might mean for development and tourism in Baja California Sur.



# TLDR
This analysis isn’t an academic study, but rather a personal exploration of water resources in Baja California Sur, a region where I’ve spent the last two months. Using only publically available tools (GEE and EO datasets) I analyzed precipitation trends, groundwater anomalies, land surface temperature, vegetation health, and urbanization to better understand water stress in this arid peninsula. While precipitation and groundwater trends point to increasing challenges, stable vegetation indices and the growing use of desalination plants offer some hope. One of the most pressing concerns for the peninsula might be the ever increasing *demand* for water, driven by the rapid growth in the southern most region near La Paz and Los Cabos. Ultimately, this project was an opportunity to expand my technical skills, dive deeper into a topic I’m passionate about, and share my findings with others interested in water systems and climate challenges in BCS.


If you want to dig into the code used for this analysis, you can visit my github repo [here](https://github.com/alex-truby/gee-water). 

# Analysis (Deep Dive)

## Precipitation
It’s no surprise that precipitation plays a critical role in determining water availability. Rainfall directly feeds surface water stores, replenishes soil moisture, and drives groundwater recharge. Because of this, tracking rainfall patterns is crucial for identifying regions grappling with water deficits or enjoying surpluses.

For this analysis, I wanted to explore precipitation trends across BCS at the basin level. There are many ways to define basin boundaries; I chose to use the WWF HydroSHEDS dataset available on GEE. For this analysis, I used the Level 9 watersheds. This level of granularity allowed me to capture both regional dynamics and localized impacts across BCS, striking a balance between losing the detail with larger basins (like Level 1) and zooming into overly localized scales (like Level 12). 

To assess precipitation trends, I relied on the ‘UCSB-CHG/CHIRPS/DAILY’ dataset from GEE. CHIRPS (Climate Hazards Group InfraRed Precipitation with Station data) provides daily global precipitation estimates at a 5.5 km resolution, spanning from 1981 to the present. Its combination of high spatial resolution and multi-decade temporal coverage makes it a go-to dataset for researchers and practitioners in the EO community.

Using CHIRPS data, I calculated the annual average rate of change in precipitation across BCS from 2013 to 2023 by fitting a linear trend to the time series data. The results are sobering: every hydroshed in BCS shows a decline in precipitation over this period. The most pronounced decreases are found near Cabo San Lucas, one of the peninsula’s fastest-growing municipalities fueled by a booming tourism industry.

<iframe src="/charts/baja_water/basin_precip_map.html" style="width: 100%; height: 400px; border: none;"> </iframe>

This trend is particularly alarming as the region’s aquifers are already under pressure to support rapid growth. A decline in surface water recharge could worsen water stress, compounding challenges for communities and ecosystems alike.

## Groundwater Anomalies
Groundwater is a lifeline for arid regions like BCS. However, coastal aquifers face growing threats from over-extraction and seawater intrusion—a significant concern for communities relying on these critical water sources. To explore groundwater trends in BCS, I analyzed data from NASA's Gravity Recovery and Climate Experiment (GRACE) satellite mission.

Launched in 2002, GRACE detects subtle variations in Earth's gravity field caused by changes in mass distribution. These measurements allow us to track anomalies in terrestrial water storage, including groundwater, soil moisture, surface water, and snow. The data is reported as anomalies—changes in water storage measured in centimeters of equivalent water height relative to a baseline (2004–2009). This approach provides a clearer picture of deviations from typical conditions, highlighting trends and regions under stress.

Since GRACE measures total water mass rather than groundwater directly, I isolated groundwater anomalies by subtracting soil moisture anomalies from the total water anomaly. To estimate soil moisture anomalies, I used data from the GLDAS (Global Land Data Assimilation System) model available in GEE. This process involved calculating soil moisture baselines across multiple depth layers (e.g., 0–10 cm, 10–40 cm) for the baseline period (2004–2009) and comparing them to annual soil moisture during the study period (2013–2023). These anomalies represent changes in soil water content that must be accounted for when interpreting GRACE data. Normally, surface water and snowpack contributions would also be subtracted to isolate groundwater changes. However, in this desert peninsula, both surface water and snowmelt have negligible impact and can be safely disregarded.

<iframe src="/charts/baja_water/basin_gwa_map.html" style="width: 100%; height: 400px; border: none;"> </iframe>

The results of this analysis show that groundwater anomalies in BCS exhibited minimal deviation from the baseline, in contrast to the steady decline observed in precipitation trends. Interestingly, the southernmost, more populated regions of BCS displayed a slight upward trend in groundwater recharge. While this trend was unexpected, I found a few potential causes for this in my research:

1. The baseline period (2004–2009) may have coincided with unusually low groundwater levels, which could exaggerate the apparent improvement.
2. Seawater intrusion into coastal aquifers—a known issue in this region—could be adding mass to the system, partially explaining the trend.
3. Conservation measures and the expansion of desalination infrastructure may be contributing to local improvements. 

For example around 30 desalination plants had been put in place in the Cabo area by 2013, with many more likely having been built over the last decade [1]. Desalination plants alongside conservation measures may be resulting in improvements to the La Paz aquifer and others in the region. 

While some trends are apparent, the interplay of natural and human factors influencing groundwater in this region remains complex and warrants further investigation.

## Land Surface Temperature (LST)
Land surface temperature (LST) is a key indicator of water availability and the broader water cycle, as it directly influences evaporation rates, soil moisture, and vegetation health. Higher LST accelerates evaporation, potentially depleting soil moisture and reducing water availability for plants and surface water bodies. In arid regions like BCS, where water resources are already scarce, monitoring LST trends helps identify areas under increased environmental stress, highlighting potential hotspots of concern for water management and ecological health.

LST is derived from the thermal infrared bands of satellite sensors and is corrected for emissivity, which varies depending on the surface type (e.g., water, vegetation, or bare soil). For this analysis, I used LST data converted from Kelvin to Celsius (°C) to provide a more intuitive understanding of the temperature variations across BCS.

<iframe src="/charts/baja_water/basin_lst_map.html" style="width: 100%; height: 400px; border: none;"> </iframe>

One striking feature of the analysis is the elevated land surface temperatures in the central region of BCS, just north of Ciudad Constitución. While I haven’t conducted a detailed investigation into the specific drivers of this phenomenon, there are several factors that could contribute to this localized heat. This area sits in a broad agricultural valley surrounded by arid mountains, where limited vegetation cover and extensive bare soil can amplify temperatures. The region's geography, combined with intense solar radiation, likely contributes to higher heat retention and radiation from the land surface. Additionally, agricultural activities, such as large-scale irrigation, can alter the microclimate by increasing evapotranspiration, while the lack of significant tree cover provides little natural cooling. Anecdotally, having camped in this area, it certainly feels noticeably hotter and dustier compared to other regions of BCS, underscoring the unique climate conditions in the area.

## Vegetation Indices (NDVI & SAVI)

Vegetation indices such as NDVI and SAVI provide valuable insights into vegetation health, productivity, and drought impacts. By measuring how plants reflect near-infrared (NIR) light and absorb red light, these indices help us understand how well vegetation is functioning in response to environmental stressors like water availability.

### NDVI: A Measure of Vegetation Health

The Normalized Difference Vegetation Index (NDVI) is widely used to assess vegetation health and density. Healthy vegetation reflects more NIR light and absorbs more visible red light, while stressed or sparse vegetation reflects less NIR and absorbs less red light. NDVI is calculated as:

$$
\{NDVI} = \frac{\{NIR} - \{Red}}{\{NIR} + {Red}}
$$

Where: 
* NIR = Near-infrared reflectance
* Red = red reflectance 

NDVI is a dimensionless index that ranges from -1 to 1:

* Values close to 1 indicate dense, healthy vegetation.
* Values near 0 suggest sparse vegetation or bare soil.
* Negative values typically correspond to water or non-vegetative surfaces.

For BCS, NDVI trends from 2013 to 2023 showed a slight negative trend (-0.006), though this change is not statistically significant. This suggests that vegetation health and density have remained relatively stable over the decade, with a slight indication of decline, potentially linked to reduced precipitation trends during the same period.

### SAVI: Accounting for Bare Soil

In regions like BCS, where vegetation is sparse, and exposed rock and sand dominate the landscape, however, NDVI may be less reliable. This is because NDVI values can be skewed by the brightness of bare soil or other non-vegetated surfaces. To address this, I incorporated the Soil-Adjusted Vegetation Index (SAVI) into the analysis:

$$
\text{SAVI} = \frac{(\text{NIR} - \text{Red})(1 + L)}{\text{NIR} + \text{Red} + L}
$$

Here, L is a soil brightness correction factor, ranging from 0 to 1:
* Lower L values (e.g., 0.1) are suitable for areas with dense vegetation.
* Higher L values (e.g., 1) are better for areas with sparse vegetation, like deserts.

For this analysis, I used L = 0.8, to reflect the sandy and rocky terrain of BCS. SAVI essentially minimizes the influence of soil reflectance, making it a more reliable indicator of vegetation health in sparsely vegetated areas.

### Comparing NDVI and SAVI Trends
While the NDVI trend from 2013 to 2023 is slightly negative, the SAVI trend is essentially constant. The difference between the two trends highlights the role of bare soil and non-vegetative surfaces in influencing NDVI values. In arid regions like BCS, where vegetation is patchy, NDVI may overestimate changes in vegetation health because of its sensitivity to soil reflectance. SAVI, on the other hand, provides a more stable measure by accounting for the influence of soil, which explains why its trend remains unchanged.

<iframe 
    src="/charts/baja_water/navi_trend_chart.html" 
    style="width: 100%; height: 600px; border: none;">
</iframe>

<iframe 
    src="/charts/baja_water/savi_trend_chart.html" 
    style="width: 100%; height: 600px; border: none;">
</iframe>

The lack of a statistically significant rate of change in NDVI or SAVI suggests that vegetation health in BCS has been relatively resilient over the past decade, despite decreasing precipitation trends. This stability may be due to the adaptive nature of desert vegetation, which is well-suited to survive under water-scarce conditions. However, the slight negative trend in NDVI could signal early signs of vegetation stress, potentially linked to more prolonged drought conditions or localized pressures like land use changes.

By incorporating both NDVI and SAVI into this analysis, we gain a more nuanced understanding of vegetation health in BCS, where sparse vegetation and soil reflectance can otherwise obscure the true picture of ecological resilience.


## Human Development (via Nighttime Radiance)
Population growth and urbanization in BCS are key drivers of rising water demand. Nighttime radiance, captured by the VIIRS (Visible Infrared Imaging Radiometer Suite) sensor, serves as a proxy for human activity and development. Measured in nanowatts per square centimeter per steradian (nW/cm²/sr), this data highlights urban expansion, which often correlates with increased water use.

Using the ‘NOAA/VIIRS/DNB/MONTHLY_V1/VCMCFG’ dataset, I analyzed changes in nighttime radiance across BCS. The region between La Paz, Cabo San Lucas, and Todos Santos showed significant growth between 2010 and 2020 [2]:

* La Paz's population grew by 15%.
* The Los Cabos area experienced a 50% population increase.
* The state of BCS as a whole saw an average population increase of 25%.

This rapid growth, combined with increased tourism and rising expectations for modern infrastructure, has led to greater pressure on water resources. Nighttime radiance trends mirror this growth, particularly in Cabo San Lucas, where tourism-driven urbanization has intensified.

<iframe src="/charts/baja_water/map_comparison.html" style="width: 100%; height: 600px; border: none;"> </iframe>

While desalination plants and conservation efforts are helping to address water demand, the scale of urban and economic growth makes ongoing water management critical. Whether visiting or living in BCS, practicing water conservation is essential in this water-scarce region.



# Conclusion

This blog post isn’t meant to be a hydrologic or climatic research thesis. Instead, it’s a personal exploration of water resources in Baja California Sur—an area I’ve come to know well after spending the last two months here. The project allowed me to combine my curiosity about water systems with a hands-on approach to using GEE and EO datasets, tools I've been wanting to work more with. Along the way, I even got GEE nicely integrated into my VSCode environment and used this as the catalyzer to finally build this website! All of the code used in this analysis is published on my github [here](https://github.com/alex-truby/gee-water). 

Living in a van, you become hyper-aware of your water usage. My partner and I have been living off two 8-liter plastic tanks and a 5-gallon jug we picked up in La Paz. This experience has made me acutely aware of how critical water is and how much effort it takes to manage such a limited resource—insights that only deepened as I explored the data behind water availability in BCS.

This analysis highlighted some troubling trends, like declining precipitation and groundwater anomalies, particularly in areas like Cabo San Lucas, where population growth and tourism are driving increased water demand. Land surface temperatures underscore the challenges of water loss through evaporation, while vegetation indices provide a small reassurance of stability in the region’s ecosystems. Nighttime radiance data shows how urbanization is expanding, putting even more pressure on finite water resources.

This journey has been both a learning experience and a passion project, blending technical exploration with personal reflections on the challenges facing water resources in this unique and beautiful region. Whether you’re a coder, a hydrologist, or just someone curious about Baja’s water systems, I hope this post sparks your own curiosity and perhaps inspires you to think more deeply about how we interact with and conserve water in our daily lives.

# Sources
1. Jáuregui, B. (2013, October 24). Water pressure in Baja California Sur. Todos Santos Eco Adventures. Retrieved from https://tosea.net/water-pressure-in-baja-california-sur/
2. City Population. (n.d.). City population - Baja California Sur. Retrieved from https://www.citypopulation.de/en/mexico/bajacaliforniasur/
