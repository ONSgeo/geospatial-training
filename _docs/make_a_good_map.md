---
title: How To Make A Good Map
description: Guidance to demonstrate good and bad practise in the creation of maps to visualise data.
---

# How To Make A Good Map

## Course Summary
### Introduction
This course introduces the most common types of maps used for the presentation of statistics, and provides guidance on what to think about when making a statistical map. 

### Estimated time for course
1 hour

### Audience
People who wish to make statistical maps

### Course Aims
This course covers:
* The most common types of statistical maps
* Fundamental map components:
  * choosing a suitable map type for your data
  * choosing a suitable type of statistical boundary for your map
  * choosing suitable bins/groups
  * choosing a good colour scheme and/or symbology for your map
* Additional map elements including:
  * base mapping
  * legends
  * labels
  * text
  * scales
* Exercise: map critique (with discussion answers)

---

## Introduction

A map is a visual representation of a physical area. A map can display data to help an audience understand the its location context better. Maps can also be helpful to tell a story about the data. Maps should serve a clear purpose, and there are many potential ways of making them depend on the underlying data and the purpose of the mapping.

This course will guide you through some of the <b>DOs</b> and <b>DO NOTs</b> of making a map. By the end you should have an understanding of:

* Different types of maps and their applications
* How to choose a colour scheme and symbology
* The importance of accessibility in maps
* The differences between boundary types and generalisation levels
* How map items can be used to describe and explain the data
* The general principles of what makes a 'good map' or a 'bad map'

---

## Map Types:

The map type you use will depend on the properties of your data and the target purpose of the visualisation. Some map types may be applicable to multiple types of data, and one type of data may be suitable for a number of map types.

### General Reference Maps

These maps mainly emphasise the locations of points of interest (POI) e.g:
* A postcode
* A route
* A city
* An airport

General reference maps are easy to read for most users as they are descriptive and visualise physical locations rather than abstracting from data. However a good general reference map will still feature a number of additional items to aid in describing what the map is displaying.

For example, the map below shows the locations of National Parks in Great Britain. Relevant features are labelled, and additional information is provided to enhance understanding of both the map itself and the National Park system.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/general_reference.PNG?raw=true" alt="A general reference map of National Parks in Great Britain">
</p>
<p align="center">
 <i>A general reference map of National Parks in Great Britain</i>
</p>

### Choropleth

A choropleth map relates data to a given area. This is achieved by colouring areas based on the values of the underlying data. Choropleths are probably the most common types of map used as they easily display aggregations of data with location context.

As the colouration is simply assigned to an entire area, the spatial distribution of the data can be misleading, or the aggregation could simply be a result of the boundary type used. To prevent this a choropleth should use normalised data e.g. people per sq. km, cases of a disease per N population, or a percentage. This normalisation makes different areas on a map more directly comparable.

This map shows a choropleth of the percentage of households below 60% of median income, after housing costs, in London MSOAs.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/choropleth.PNG?raw=true" alt="A choropleth of the percentage of households below 60% of median income, after housing costs, in London MSOA">
</p>
<p align="center">
 <i>A choropleth of the percentage of households below 60% of median income, after housing costs, in London MSOA</i>
</p>

### Graduated and Proportional Symbols

Graduated and Proportional Symbol maps are an alternative to choropleths for visualising quantities. These symbol maps vary the size of a point symbol depending on the underlying data.

A graduated symbol map does this by dividing the symbol sizes into bins, just like a choropleth does with colour, and thus displays symbols which scale from a minimum to a maximum size across these bins. Graduated symbols are the preferred type for mapping quantities as symbols as it is made clear in the legend what symbol size relates to what data range.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/graduated_symbol.PNG?raw=true" alt="A graduated symbol map of burglary rates in London MSOAs">
</p>
<p align="center">
 <i>A graduated symbol map of burglary rates in London MSOAs</i>
</p>
 

A proportional symbol map is similar in application, however here the size of the symbols varies directly with the underlying data values i.e. it is not split up into discrete bins. Proportional symbols are less ideal as it can result in both a large number of symbol sizes and very small differences between similar values. This makes it hard to easily identify the general scale of the data and how it varies on average from place to place. In the map below, the legend is broken up in steps, however the symbols on the map have sizes which vary between these steps according to the source data. Labelling the symbols with their actual values might make it easier to read, but the same thing can be done for graduated symbols to increase accuracy.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/proportional_symbol.PNG?raw=true" alt="A proportional symbol map of burglary rates in London MSOAs">
</p>

Ideally you should use a graduated symbol map when displaying point data as different sized symbols. You should also consider the overall scale of the map and the density of points: If the symbols are very dense they can overlap and become unreadable, or they can cover up underlying geographies and thus hide their spatial context.

### Classification Maps

Other classification maps may not directly represent physical features, and therefore colouration must be abstracted and need not follow any actual geographic characteristics. The map below, for example, shows a demographic-based Output Area Classification for South-East England. Classes here may have generally agreed upon colour associations (green for rural, grey for urban), but some categories such as "Cosmopolitan" are not necessarily associated with a specific colour.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/classification_map.PNG?raw=true" alt="Output Area Classification of Southern Hampshire">
</p>

### Heatmap

Heatmaps use a colour scale to display a relationship between the density of points and a given data value. Heat maps make it easy to understand the relationships between the locations of the points and overall trends in the data.
 
The map below shows this for burglaries in London. Each burglary is represented as a single point. For a given radius around each point, the more points in that radius the more intense the 'heat' and the darker the colour. Additionally, we can specify an underlying value to add weight to the map e.g. the financial loss per burglary. This will adjust the colour scale to make it clearer where there are not only a large number of instances, but also which areas are the most impacted.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/heatmap.PNG?raw=true" alt="Heatmap of burglary incidents in London">
</p>

### Dot Density

Dot density maps display a distribution of points where each point represents a certain number of observances from underlying data. The randomised distribution of these dots within individual polygons, from which the dots get their values, creates an interesting visualisation showing how different the densities of records can be in different areas. The example below does this by visualising one point for every 500 votes cast for different parties in the 2019 UK General Election.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/dot_density.PNG?raw=true" alt="Dot density map of the results of the 2019 UK General Election">
</p>

### Specialised Maps

These maps are primarily used for more specialised purposes and may require a more advanced understanding of geography and data visualisation to be useful.

#### Bivariate Maps

Bivariate maps combine two variables in the data and plot them against each other across the same colour scale. There are multiple ways to make a bivariate map. One way is to use a specific plugin for some GIS software. This will automatically group data into a number of bins across two axis. For instance, the x and y axis may be split into 'high' and 'low' for each, thus there would be four categories: xlow:ylow, xhigh:ylow, xlow:yhigh, xhigh:yhigh. Given that this is essentially just a categorisation of the data, a bivariate map could also be made by first categorising the data according to manually set threshold for the data, and then using the same principles as for a categorical map but with a colour scheme which converges on both x and y variables. The map below demonstrates this by simultaneously plotting 

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/bivariate.PNG?raw=true" alt="Bivariate map of London MSOAs showing Burglary rates vs median household income">
</p>

#### Cartograms

Cartograms are a type of map whereby the size and shape of a geography is distorted from the real, physical reality. A number of cartograms are possible. The map below demonstrates a hexmap to represent data in Local Authorities.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hexmap_cartogram.PNG?raw=true" alt="Cartogram of the percentage of employees in a Local Authority District working in manufacturing in 2014">
</p>

Cartograms radically change the visual presentation of the data. Equal-area cartograms are useful to remove area effects where, for instance, boundaries do not necessarily correspond to almost constant densities of people (which Ouput Areas do).

---

## Colour Schemes and Symbology

Once a map type has been chosen, by far the most important property to consider is the colour scheme you will use. Different colour schemes can fundamentally change the way an audience may view and interpret a visualisation. Some colour schemes may raise an inherent bias, others may be unintuitive, and some may be unreadable for people with visual impairments such as colour blindness. Choosing the right colour scheme to counter these issues is vital. There is no absolute 'right' or 'wrong', but there are choices which offer the best looking, most impactful, and most accessible maps.

Along with colour, the overall symbology must be considered. This includes what types of symbols to use for point data, line thicknesses, and map effects for emphasis.

## Boundaries

Boundaries refers to the area on which data is displayed e.g. an OA, LAD, County etc. These boundaries often come in different resolutions. The choice of boundary is important for both accuracy of the visualisation and for making it look good. 

Always make sure that the chosen boundaries are best suited to the data you wish to display. For example OAs may be more detailed than necessary or too disclosive and so MSOAs may be appropriate, or the data may be reported at a geography such as a LAD and may lose meaning if aggregated up further to Counties..

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/statistical_geography_hierarchy.PNG?raw=true" alt="The same map of population density in London displayed at four different boundary aggregations.">
</p>
<p align="center">
 <i>The same map aggregated at four different levels of geography: Output Area (OA), Super Output Areas (LSOA and MSOA), and Local Authority (LAD).</i>
</p>

### Boundary Generalisation

Boundaries from the <a href="https://geoportal.statistics.gov.uk/" target="_blank">Open Geography Portal</a> usually come in a number of generalisations (resolutions). The image below shows what these generalisations do to the quality of the boundaries.

What generalisation you choose will depend on both what you want to visualise. A map which covers a large area with very little detail will not need a Full boundary such as BFE as this can be slow to handle in software and the detail could be distracting or hard to display. In this case, a Generalised boundary such as BGC may be better as it reduces unneeded details while preserving the overall geometry. Alternatively, there may be occasions when Super-generalised or ultra-generalised will get the job done just as well as BGC and cut out unwanted details completely.

This map shows how different boundary levels can change the amount of detail visible:

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Boundary_generalisation.PNG?raw=true" alt="Visualisation of different boundary generalisations available from the geoportal.">
</p>

### Mixing Boundaries

Sometimes it is useful to overlay one type of boundary on top of another. Care should be taken to not make the map too crowded or to cover up the most important boundaries or colours with the overlay. The map below, for example, shows data at MSOA level with LAD boundaries drawn on. It would be inappropriate, however, to draw MSOA boundaries over LAD level data as this might suggest detail at the MSOA level which is not actually present. Overlaying boundaries can also help give a sense of location if the primary boundaries are not commonly known by the target audience.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Houses_below_60_percent_median_income_Choropleth_Mixing_Boundaries.PNG?raw=true" alt="MSOA map with LAD boundaries on top">
</p>

### Palettes and Data

The ideal colour palette for a map depends on both the map type and the underlying data. Many different colour palettes can be used for any given map, however some may be more appropriate than others. The following subsections, taken together, describe how an appropriate palette can be chosen.

#### Continuous vs Discrete

One of the first considerations is whether the data mapped is made up of continuous or discrete variables.

For continuous variables, the colour palette will be a continuous 'ramp': it will vary along a gradient between different colours. This type of palette is most suitable for numeric or ordered variables where there is a clear minimum and maximum value with a range between these. A number of 'ramps (see: Colour Ramps) can be used for this data depending on it's properties.

Discrete data can also represented via a ramp if it is ordered. If, however, each feature represents a distinct class then a different type of palette may be suitable. In these cases it is often a good idea to start with a colour ramp and aply this. Then, the colours can be adjusted to be distinct across variables. For example, a choropleth for the Rural-Urban classification of LSOAs has 'rural' and 'urban' classes divided into subclasses. It would be useful to choose a different colour entirely for urban and rural classes, but to choose different shades of those colours to distinguish subclass features within the urban and rural classes e.g. shades of green for rural and shades of grey for urban. As data can often contain far more classes than distinct colours, it is not always beneficial to display all at once. Sometimes it is acceptable to create a new map for each class to show them off in more detail.

#### Colour Ramps

Colour ramps are a continuous scale of colours starting from one colour then shifting to another. In some ramps this is simply a change from a start to an end colour, in others there could be multiple colour changes along the way. When applied to data which is split into classes, the ramp is divided out across those classes. 

A continuous scale would use one colour and simply change shade between light and dark. This type of ramp is useful when the data is on a continuous scale e.g. a range of temperatures or population density where there is an obvious increase from a low to a high.

A diverging ramp as there has different start and end colours, but with those blending to form a distinct central region. This ramp is very effective to show data which diverges about a fixed value e.g. percentage increase or decrease in disease cases. These will diverge around a certain number but may not necessarily be symmetrical around it i.e. the change will always be positive or negative, so '0' would be the centre point about which the data varies.

Categorised or random colour ramps assign unique colours to different classes with no respect to minimum or maximum values. This was demonstrated previously with land cover and classification maps. It is also sometimes ok to assign random colours to a map if, for instance, one wanted to simply differentiate between areas without reference to underlying data. This can, in fact, be achieved with only four colours according to the <a href="https://en.wikipedia.org/wiki/Four_color_theorem" target="_blank">four colour theorem</a>.

#### Relative vs General

A point must also be considered about how people may have a bias towards a certain colour: red is 'bad', blue is 'good'; green is 'natural', grey is 'artificial'. These preconceptions can colour the interpretation of a map.

It is therefore generally advisable to choose a palette which is not strongly associated with these biases when presenting data for which there is no clear trend towards these conclusions e.g. a map of population density which ranges from blue (low) to red  (high) might suggest the higher density is 'worse' than lower density. A more neutral palette, such as viridis, might not hold these preconceptions but is still effective at differentiating the extremes.

However there are plenty of cases where it is logical to make a map based on existing associations with a colour such as a previous example of choosing green for rural areas and grey for urban: this is clearly linked to the physical appearance of the areas and therefore makes the distributions easier to interpret. Similarly, land cover maps may be more effective if the polygons are coloured to match the 'expected' colour the land cover type.

### Aesthetics and Accessibility

A good map will be aesthetically pleasing as well as informative; the colours chosen won't clash, there will be a clear unifying theme to the symbology, and the overall design will lend itself to being both easy and enjoyable to view. Still, the aesthetics should not compromise the <i>accessibility</i> of a map.

#### Colour and Accesibility

 <a href="https://colorbrewer2.org/#type=sequential&scheme=BuGn&n=3" target="_blank">ColorBrewer</a> is a web which allows you to choose a number of aesthetically pleasing palettes based on a number of criteria including the order of the data (sequential, diverging etc.), print or copy friendly, and colour-blind friendliness. Browsing through these palettes and selecting different criteria, you can see how different each palette is. Most of the palettes offer distinct and easily identifiable schemes which offer an unambiguous scale.
 
Accessibility is very important when making any visualisation. In maps this means choosing colour-blind friendly palettes and clearly legible and easy to comprehend text. The maps below demonstrate how colour blindness can make it difficult to differentiate between different parts of a colour scale. The first map is how someone with normal colour vision would see the map. This red-green scale is particularly infamous for being inaccessible. Instead, the blue-red scale is clearly differentiated across the most common form of colour-blindness.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/colour_accessibility.PNG?raw=true" alt="Visualisation of how colour-blindness can affect readability of a map">
</p>

### Fills, textures, and strokes

As a general rule, the fills for polygons should be solid colours. Texture or pattern fills often add unnecessary visual complexity to maps. In cases where a fill could be used to display physical features, like grassland with grass symbols, a colour or a basemap already showing that would suffice.

The 'strokes', outlines of polygons and points or line features, should be thin enough to not cover other features while still being clearly visible. With line features, stroke width is a useful way to denote a hierarchy of features or differentiate between them as colour is not always obvious at some stroke widths.

### Labels

Labels are pieces of text placed on the map itself to identify individual features or groups of features. Labels can be placed in a number of ways:

* Alongside the feature
* Around the feature
* Entirely within the feature
* Across the feature matching its shape

Which label to use depends on several factors. A densely visualised map may only be able to fit in a few labels before becoming messy. Labels for a geography which does not easily fit the label might need the text to move along the feature. When following the geometry of a feature, labels should flow left to right, bottom to top (see map below which contains multiple label types). This ensures the label is legible. Additionally, labels should not cross over the boundary of the parent feature into another as this could suggest it belongs to multiple.


---

## Peripherals

In addition to the main attribute of the map (palette, breaks, boundaries), other items can be arranged alongside to provide more information and context. Not all of these peripherals are always necessary but are contextual depending on both the type of visualisation and the intended audience.

### Basemaps

Basemaps are pre-made maps which can be used to form the 'base' of a visualisation. These basemaps come in a number of forms ranging from standard topographical maps such a street maps or leisure maps, to aerial imagery or hybrids (think Google Maps), to possibly even heavily stylised maps useful for aesthetically pleasing backdrops.

Importantly backdrops can provide additional location detail and context which is not visible in the main data. The basemap below uses n OS Grey Raster tile to show an area with the main data overlayed.

As an ONS employee you will have access to basemaps from the Ordnance Survey Data Hub as part of the Public Sector Geospatial Agreement (PSGA). To gain access to these basemaps you simply need to sign up with a Public Sector Account at the <a href="https://osdatahub.os.uk/" target="_blank">data hub</a>. Your application will have to be processed by an administrator to verify your employment, but this shouldn't take long. Before verification, however, you will still have access to open data APIs for use as basemaps.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_2.jpg?raw=true" alt="Basemap added to Hartlepool">
</p>

#### Sources

While a number of basemap API sources are available, we would recommend using <a href="https://osdatahub.os.uk/" target="_blank">OS Open Data</a>, as the PSMA gives us civil servants access to their basemaps. To sign up for this:

* instructions

Vector and raster tiles are available from here and these come in a number of styles (a few shown below), making them useful for a number of applications.

### Legend

A legend, or key, displays the different symbology (including colour scales) used on the map and their respective description.

Legends are generally a necessity as without them it can be difficult to determine what each symbol on the map means. Legends do not have to describe EVERY time on the map e.g. a basemap may not need an legend entry nor would a background layer used just as a fill. For a choropleth the legend would include the colour scale used for the areas and the associated values or value ranges. A General Feature map (like the one at the start of this course) would have the symbols for places shown in the legend and what they represent.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_3.jpg?raw=true" alt="Legend added to Hartlepool">
</p>

### Scale 

A scale is used to assist the viewer in determining distances on the map which may not be easy to understand without context. This is usually the case when e.g. no basemap is used or for maps where distances are not easily worked out from the relative sizes of objects on the map. A number of methods are used to visualise scales. Generally, the scale bar is broken up into alternating blocks, with each block representing a given distance. The map below shows a scale with a left and right side: The left side shows divisions of a KM, while the right side shows the extent of a whole KM.

In this example map a scale was necessary for two reasons: 

* There are no contextual clues in the map to give a sense of scale
* The data shown is based on a measure of distance

The latter reason is an important consideration as it can give much-needed additional context to the distribution of the data.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_4.jpg?raw=true" alt="Scale added to Hartlepool">
</p>

### Compass 

A compass shows the direction of the cardinal directions. A compass is a lesser-used feature in most data visualisations as it's often clear that maps default to 'up' as north. However, there are times when this may not be the case such as when the map is rotated, or the map may be taken in isolation away from the text which would otherwise signify 'up'. If the area shown in the map is unfamiliar to the viewer, they may also wish to have a reference to north.

While many will think of a fancy compass rose such as on old-fashioned globes which show NWSE and interstitial directions, it is perfectly acceptable to use a compass which only shows north. In the example below this is represented with a simple arrow pointing up. If the displayed map was actually offset at a certain angle from North, the arrow would also be rotated to this angle.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_5.jpg?raw=true" alt="Compass added to Hartlepool">
</p>

### Graticules

Graticules are lines and/or dashes within and along the edge of a map which display X and Y coordinates. Graticules are commonly seen on military maps where a combination of distance grid and decimal degrees longitude and latitude are shown.

Graticules are rarely used in basic visualisations however they are particularly important in some situations. For example, some large-scale maps such as those of entire continents can often be enhanced with the use of graticules: either as dashes on the edge of the map or lines going across it. Similarly, the mapping of any data which is known to vary with latitude and longitude can use a graticule to make this explicit. 

The graticules should be unintrusive however, so try not to use thick or bold lines and instead use thin lines with a colour which blends well with the rest of the map.

---

## Text

Text is very important for mapping. It provides a description of what the map represents and can be expanded into a number of areas to improve the quality of the map.

### Title

The title is the most important single piece of text on a map. A title should stand out and be clearly visible at the top. The title should be descriptive enough that a viewer can clearly glean the purpose of the map from what it says. Conversely, the title is not in and of itself a piece of descriptive text and so should be made concise so a viewer could read and understand it quickly. The map below gives a good example of a title: Highly descriptive but concise and to the point.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_6.jpg?raw=true" alt="Title added to Hartlepool">
</p>

### Descriptive Text

As the title cannot be used to describe EVERYTHING about a map, some accompanying descriptive text could be useful. This should be placed alongside the map and should give additional details about specific points of the visualisation. For example, a descriptive text box could be used to briefly explain the distribution of the data in a choropleth, or multiple boxes could be added with lines pointing to clusters of points, or it could simply give additional context for the purpose of the map.

Regardless of how the text is used, it should be clear and relate directly to the map.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_7.jpg?raw=true" alt="Credits added to Hartlepool">
</p>


#### Insets

Insets are smaller maps within the layout of a large map used to show details which may otherwise be hard to see in the main map. These are often used to show dense urban areas e.g. Greater London in detail, or to include features geographically separated from the main features of map by positioning them closer e.g. the Shetland Isles which may otherwise be too far from Great Britain that the overall scale of the map would not be appropriate.

Multiple insets can be used on the same map to show off different areas of interest in greater detail. However, this can become cluttered and consideration should be taken as to if an entirely new page/map should be used for the inset feature instead.

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_8.jpg?raw=true" alt="England IMD LSOA map with insets for Greater London, Hartlepool, and Isles of Scilly">
</p>

---

## General Map Design

This section will cover some other, more general aspects of map design, particularly arranging the layout of a map and some underlying considerations towards the purpose of the map.

### Layout

The layout of a map, that is the layout of all items on a page or image from the map itself to text and peripherals, is important for both the aesthetics of the map and ease of use.

When arranging items, it's important to consider a few things: What items are PART of the map and what items DESCRIBE the map. As a general rule, items which are actually a part of the map should clearly stand out. Boundaries should be obvious, colours clear, symbols highly visible.

#### Arranging items

When arranging items around the map, be sure to keep the focus on the map itself. Generally the map should take up the most area with other features like text, legend, scale being placed arond or on the map without covering data. For items placed outside of the main map area, these should be placed such that they follow the 'reading order': look at the map, then refer to descriptions and other items after. Items placed in the map area need to be unintrusive but clear for example a scale should be place such that it's on the map for direct reference but is not intruding upon key map features like coloured areas or labels.


## Showcase: Bad and Good Maps

This section will showcase two maps, each of which is presented as "bad" and "good". The "Bad" maps go against the guidance given in this module. Try to work out what's wrong with them before revealing the answers and the 'good' version. Both maps were created specifically for these examples and are not representations of official maps.

### Example 1

<p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Badmap_Goodmap1.png?raw=true" alt="The bad version of a London house price map">
</p>

<details><summary><b>Answer</b></summary>

 <ul>
  <li>The colour scheme is a random palette and not accessible. It should be a continuous scale and colour-blind friendly</li>
  <li>The borders of the MSOAs are too thick so the denser areas become impossible to see</li>
  <li>The legend is poorly titled and there are to many breaks</li>
  <li>The title does not properly describe what the map shows</li>
 </ul> 
  
 <p>Below is what the map <i>could</i> look like if it were to follow the guidance:</p>
 
 <p align="center">
  <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Badmap_Goodmap1_2.png?raw=true" alt="The good version of a London house price map">
 </p>
</details>

### Example 2:
 
 <p align="center">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Badmap_Goodmap2.png?raw=true" alt="The bad version of a London burglaries heatmap">
</p>

<details><summary><b>Answer</b></summary>

<ul>
 <li>The overlayed Ward boundaries are too detailed and don't provide any additionally useful context</li>
 <li>The basemap is far too detailed and clashes/distracts from the heatmap itself</li>
 <li>The credits text does not comply with the necessary copyright statements and is not easily identified against the basemap</li>
 <li>The overall layout and clarity of individual elements is extremely poor
</ul>
 
 <p>Below is what the map <i>could</i> look like if it were to follow the guidance:</p>
 
 <p align="center">
  <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Badmap_Goodmap2_2.png?raw=true" alt="The good version of a London burglaries heatmap">
 </p>
</details>
