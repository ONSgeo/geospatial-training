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

One of the best things you can do with geographic data is visualise it by making a map. A map can display data to help an audience understand the  location context better and can also be helpful to tell a story about the data.

Map makers face a range of choices when designing a map; these choices should be driven by the purpose of the map. Throughout this course will guide you through the best practice of making a statistical map and some common pitfalls to avoid. By the end you'll be confident identifying the most common statistical map types, know about the main elements of a map and know how to put them together to make a well designed output.


## Map Types

There are many different types of map which can be used in a statistical context. The type of map you use will depend on the properties of your data and the purpose of the visualisation. Some map types may be applicable to multiple types of data, and one type of data may be suitable for a number of map types. In this section we will introduce some of the most common statistical map types and outline the best contexts for their use. By the end of the section you should be able to think about your data and pick a suitable map type to display it. 

As we mentioned, there may be multiple map types which are suitable choices for your data. If this is the case then it's up to you to pick the map which most clearly illustrates the data and the point you are illustrating with it.


### Choropleth

Choropleth maps are frequently used to display statistical data by colouring defined geographic areas to represent the statistial value for that area. Choropleth maps are good at illustrating spatial distributions and patterns in an easily understandable and intuative way. These maps are the most commonly used statistical map so it's likely your audience will be familiar with them. 

Choropleths can display data when it's:
* standardised as a rate or ratio (but *never* as raw counts)
* a continuous dataset
* attached to a standard set of areas, for example, a statistical geography provided by ONS.

The main pitfall you can make with choropleth maps is plotting raw counts on your map. Plotting counts on a choropleth is misleading as it fails to account for the different sizes of the geograpic areas you are plotting, which makes comparisons between the areas unfair. By plotting standardised data you overcome this problem. You can standardise data in a number of ways, for example, instances per km^2, instances per 10000 of population, or as a percentage. If plotting raw counts is important for your visualisation you should consider using a different type of map, such as a graduated or proportional symbol map.

The image below is an example of a choropleth, which shows of the percentage of households below 60% of median income, after housing costs, in London MSOAs.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/choropleth.png?raw=true" width="50%" alt="A choropleth of the percentage of households below 60% of median income, after housing costs, in London MSOA">
</p>

### Graduated and Proportional Symbols

Graduated and Proportional Symbol maps are a good alternative to choropleths for visualising quantities or raw counts. These maps represent the data through a series of differently sized circles, which vary in sized based on the underlying data. While graduated and proportional symbol maps look very similar, the method used for calculating the circle size differs between the two map styles. 

Graduated symbol maps divide the underlying data into classes, just like a choropleth does; each class is assigned to a circular symbol of a specific size which represents the class. Graduated symbol maps provide a clear indication of which sized circle relates to which data value and so, can be easier to interpret than proportoinal symbol maps. Below is an example of a graduated symbol map.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/graduated_symbol.png?raw=true" width="50%" alt="A graduated symbol map of burglary rates in London MSOAs">
</p>

Proportional symbol maps do not categorise the underlying data into classes. Instead, each data value is represented by a circle which has an area proportional to its corresponding data value. Because of this, proportional symbol maps can have a wide range of different circle symbols which can be hard for the user to interpret properly. Also, if your dataset has extreme values they will tend to have very large circles which can take over the map easily. The map below is an example of a proportional symbol map - it uses the same data as the graduated symbol map above, so you can compare the two styles. 


<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/proportional_symbol.png?raw=true" width="50%" alt="A proportional symbol map of burglary rates in London MSOAs">
</p>

With both of these maps types you should consider the overall scale of the map and the density of points: if the symbols are very dense they can overlap and become unreadable, or they can cover up underlying geographies and thus hide their spatial context. Sometimes you can overcome this by using design features like making your circular symbols slightly transparent or, if this is not appropriate, by selecting a different style of map.

### Heatmaps

A heatmap is created by using point data to make an interpolated surface which represent the density of data points across a geographic area; this surface can also be weighted by an attribute of the underlying data. The surface is coloured with a continuous colour ramp. Heatmaps make it easy to understand the overall trends in point data, including by highlighting areas of particularly high or low density. However, through the creation of an interpolated surface, error can be introduced into your analysis. So, this is a better style of map to visualise data for overall trends, rather than for accurate numerical analysis.
 
The map below is an example of a heatmap for burglaries in London which has been wieghted by financial loss per burglary. Across the map you can see areas with higher density, shown in a darker colour. These represent areas where there have been a high number of burglaries or where there has been a high financial loss. 

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/heatmap.png?raw=true" width="50%" alt="Heatmap of burglary incidents in London">
</p>


### Dot Density
Dot density maps use dot symbols to represent observations. Each dot is of identical size and represents the same number of observations as each other dot on the same map - either one-to-one (where one dot is one observation) or one-to-many (where one dot represents a number of observations, eg, one dot equals 500 people). The position of the dots can be assigned either randomly within an associated polygon (eg. an Output Area) or in the actual location of the observation. A colour palette can also be use for categorical data to represent the distribution of the different categories. For example, the map below uses colour to show votes cast for different parties in the 2019 UK General Election, across London, where one point represents 500 votes.


Dot density maps are good for highlighting patterns and distributions in data. They can be used well in place of proportional or graduated symbol maps, and also when you're tempted to break the rules and plot a choropleth with raw counts! When plotting dot density maps you should take care to ensure that the one-to-many value you use is appropriate for the data so it illustrates spatial distributions and data distributions within categorical data without being misleading. The one big disadvantage of dot density maps is they are incredibly frustrating to extract values from, so, if you need people to read values from your map, consider using labels or a different map style altogether.


<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/dot_density.png?raw=true" width="50%" alt="Dot density map of the results of the 2019 UK General Election">
</p>


### Bivariate Maps

Bivariate maps are a type of choropleth which allow two variables to be plotted. Bivariate maps are best placed to show two variables which are related (either through a positive or negative correlation) but unlike your standard choropleth, bivariate maps tend to show broad classes and trends rather than more specific values. If you look at the map below you'll see the legend is laid out like a plot with an x and y axis - each axis represents one variable and data is classified and coloured by which class it falls in on this plot. As bivariate maps show broad correlations it's best to keep you number of classes to either 4 (2x2), 9 (3x3) or 16 (4x4) which is why bivariate maps are better at showing correlations and broad trends rather than more exact values - any more classes and it becomes too difficult to differentiate between them. As with a standard choropleth map, values on a bivariate map should be standardised rather than raw counts.

Bivariate colour schemes are difficult to get right; making sure they are accessible and easily distinguishable is tricky. Tools like ColourBrewer have colour pallets and we recommend you use them rather than making your own.


<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/bivariate.png?raw=true" width="50%" alt="Bivariate map of London MSOAs showing Burglary rates vs median household income">
</p>

### Cartograms

Cartograms are a type of map where the size and shape of the areas on the map are distorted from the real, physical reality. There are a number of different cartograms styles available so don't be too confused by this! In a statistical context you will often see areas (for example, Local Authorities) represented as a series of coloured hexagons, we call these maps hexmaps and they are one style of cartogram commonly used when the real size and location of areas doesn't matter too much or where the actual areas wouldn't be recognisable by those looking at the map. In hexmaps the hexagons are laid out in a way which roughly represents the geographic location of the hexagons, this makes it easy for the viewer to understand the general trends in the data. Colour scales can be chosen to be appropriate for categorical data (more on this below) or for continuous data where values are binned like on a choropleth. 


<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hexmap_cartogram.png?raw=true" width="50%" alt="Cartogram of the percentage of employees in a Local Authority District working in manufacturing in 2014">
</p>



### Mapping Categorical Data

The maps outlined above deal with continuous data which is most common in a statistical context. However, you may sometimes come across categorical data which requires mapping. When mapping categorical data it is best to choose colours for each cateogry which represent that category best. For example, when mapping land cover it's common to use green for rural areas and greys for urban areas because they most closely match the colours of those land uses in real life. Alternatively, some colours have a commonly recognised symbology in society, such as red for Labour and blue for Conservatives, which should be used to avoid confusion. When picking colour schemes for categorical data it is important to ensure each cateogry has enough contrast when mapped against another, to make sure that the colour scheme is complementary and asthetically pleasing, and to ensure no one category visually jumps out more than another by accident. 

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/classification_map.png?raw=true" width="50%" alt="Output Area Classification of Southern Hampshire">
</p>


### General Reference Maps

General reference maps are not a type of thematic map but they can augment reports and aid the readers' understanding. 

General reference mainly emphasise the locations of points of interest (POI) e.g:
* A postcode
* A route
* A city
* An airport

General reference maps are easy to read for most users as they are descriptive and visualise physical locations. The map below shows the locations of National Parks in Great Britain. Relevant features are labelled, and additional information is provided to enhance understanding of both the map itself and the National Park system.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/general_reference.png?raw=true" width="70%" alt="A general reference map of National Parks in Great Britain">
</p>



## Colour Schemes and Symbology

Once a map type has been chosen, by far the most important property to consider is the colour scheme you will use. Different colour schemes can fundamentally change the way an audience may view and interpret a visualisation. Some colour schemes may raise an inherent bias, others may be unintuitive, and some may be unreadable for people with visual impairments such as colour blindness. Choosing the right colour scheme to counter these issues is vital. There is no absolute 'right' or 'wrong', but there are choices which offer the best looking, most impactful, and most accessible maps.

Along with colour, the overall symbology must be considered. This includes what types of symbols to use for point data, line thicknesses, and map effects for emphasis.

## Boundaries

Boundaries refers to the area on which data is displayed e.g. an OA, LAD, County etc. These boundaries often come in different resolutions. The choice of boundary is important for both accuracy of the visualisation and for making it look good. 

Always make sure that the chosen boundaries are best suited to the data you wish to display. For example OAs may be more detailed than necessary or too disclosive and so MSOAs may be appropriate, or the data may be reported at a geography such as a LAD and may lose meaning if aggregated up further to Counties..

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/statistical_geography_hierarchy.png?raw=true" width="50%" alt="The same map of population density in London displayed at four different boundary aggregations.">
</p>

### Boundary Generalisation

Boundaries from the <a href="https://geoportal.statistics.gov.uk/" target="_blank">Open Geography Portal</a> usually come in a number of generalisations (resolutions). The image below shows what these generalisations do to the quality of the boundaries.

What generalisation you choose will depend on both what you want to visualise. A map which covers a large area with very little detail will not need a Full boundary such as BFE as this can be slow to handle in software and the detail could be distracting or hard to display. In this case, a Generalised boundary such as BGC may be better as it reduces unneeded details while preserving the overall geometry. Alternatively, there may be occasions when Super-generalised or ultra-generalised will get the job done just as well as BGC and cut out unwanted details completely.

This map shows how different boundary levels can change the amount of detail visible:

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Boundary_generalisation.png?raw=true" width="50%" alt="Visualisation of different boundary generalisations available from the geoportal.">
</p>

### Mixing Boundaries

Sometimes it is useful to overlay one type of boundary on top of another. Care should be taken to not make the map too crowded or to cover up the most important boundaries or colours with the overlay. The map below, for example, shows data at MSOA level with LAD boundaries drawn on. It would be inappropriate, however, to draw MSOA boundaries over LAD level data as this might suggest detail at the MSOA level which is not actually present. Overlaying boundaries can also help give a sense of location if the primary boundaries are not commonly known by the target audience.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Houses_below_60_percent_median_income_Choropleth_Mixing_Boundaries.PNG?raw=true" width="50%" alt="MSOA map with LAD boundaries on top">
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

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/colour_accessibility.png?raw=true" width="50%" alt="Visualisation of how colour-blindness can affect readability of a map">
</p>

### Fills, textures, and strokes

As a general rule, the fills for polygons should be solid colours. Texture or pattern fills often add unnecessary visual complexity to maps. In cases where a fill could be used to display physical features, like grassland with grass symbols, a colour or a basemap already showing that would suffice.

The 'strokes', outlines of polygons and points or line features, should be thin enough to not cover other features while still being clearly visible. With line features, stroke width is a useful way to denote a hierarchy of features or differentiate between them as colour is not always obvious at some stroke widths.

### Line Symbology

### Point Symbology

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

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_2.jpg?raw=true" width="50%" alt="Basemap added to Hartlepool">
</p>

#### Sources

While a number of basemap API sources are available, we would recommend using <a href="https://osdatahub.os.uk/" target="_blank">OS Open Data</a>, as the PSMA gives us civil servants access to their basemaps. To sign up for this:

* instructions

Vector and raster tiles are available from here and these come in a number of styles (a few shown below), making them useful for a number of applications.

### Legend

A legend, or key, displays the different symbology (including colour scales) used on the map and their respective description.

Legends are generally a necessity as without them it can be difficult to determine what each symbol on the map means. Legends do not have to describe EVERY time on the map e.g. a basemap may not need an legend entry nor would a background layer used just as a fill. For a choropleth the legend would include the colour scale used for the areas and the associated values or value ranges. A General Feature map (like the one at the start of this course) would have the symbols for places shown in the legend and what they represent.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_3.jpg?raw=true" width="50%" alt="Legend added to Hartlepool">
</p>

### Scale 

A scale is used to assist the viewer in determining distances on the map which may not be easy to understand without context. This is usually the case when e.g. no basemap is used or for maps where distances are not easily worked out from the relative sizes of objects on the map. A number of methods are used to visualise scales. Generally, the scale bar is broken up into alternating blocks, with each block representing a given distance. The map below shows a scale with a left and right side: The left side shows divisions of a KM, while the right side shows the extent of a whole KM.

In this example map a scale was necessary for two reasons: 

* There are no contextual clues in the map to give a sense of scale
* The data shown is based on a measure of distance

The latter reason is an important consideration as it can give much-needed additional context to the distribution of the data.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/scale_bar.PNG?raw=true" width="50%" alt="Scale added to Hartlepool">
</p>

### Compass 

A compass shows the direction of the cardinal directions. A compass is a lesser-used feature in most data visualisations as it's often clear that maps default to 'up' as north. However, there are times when this may not be the case such as when the map is rotated, or the map may be taken in isolation away from the text which would otherwise signify 'up'. If the area shown in the map is unfamiliar to the viewer, they may also wish to have a reference to north.

While many will think of a fancy compass rose such as on old-fashioned globes which show NWSE and interstitial directions, it is perfectly acceptable to use a compass which only shows north. In the example below this is represented with a simple arrow pointing up. If the displayed map was actually offset at a certain angle from North, the arrow would also be rotated to this angle.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/compass.PNG?raw=true" width="50%" alt="Compass added to Hartlepool">
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

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_6.jpg?raw=true" width="50%" alt="Title added to Hartlepool">
</p>

### Descriptive Text

As the title cannot be used to describe EVERYTHING about a map, some accompanying descriptive text could be useful. This should be placed alongside the map and should give additional details about specific points of the visualisation. For example, a descriptive text box could be used to briefly explain the distribution of the data in a choropleth, or multiple boxes could be added with lines pointing to clusters of points, or it could simply give additional context for the purpose of the map.

Regardless of how the text is used, it should be clear and relate directly to the map.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_7.jpg?raw=true" width="50%" alt="Credits added to Hartlepool">
</p>


#### Insets

Insets are smaller maps within the layout of a large map used to show details which may otherwise be hard to see in the main map. These are often used to show dense urban areas e.g. Greater London in detail, or to include features geographically separated from the main features of map by positioning them closer e.g. the Shetland Isles which may otherwise be too far from Great Britain that the overall scale of the map would not be appropriate.

Multiple insets can be used on the same map to show off different areas of interest in greater detail. However, this can become cluttered and consideration should be taken as to if an entirely new page/map should be used for the inset feature instead.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_8.jpg?raw=true" width="50%" alt="England IMD LSOA map with insets for Greater London, Hartlepool, and Isles of Scilly">
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

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Badmap_Goodmap1.png?raw=true" width="50%" alt="The bad version of a London house price map">
</p>

<details><summary><b>Answer</b></summary>

 <ul>
  <li>The colour scheme is a random palette and not accessible. It should be a continuous scale and colour-blind friendly</li>
  <li>The borders of the MSOAs are too thick so the denser areas become impossible to see</li>
  <li>The legend is poorly titled and there are to many breaks</li>
  <li>The title does not properly describe what the map shows</li>
 </ul> 
  
 <p>Below is what the map <i>could</i> look like if it were to follow the guidance:</p>
 
 <p align="left">
  <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Badmap_Goodmap1_2.png?raw=true" width="50%" alt="The good version of a London house price map">
 </p>
</details>

### Example 2:
 
 <p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Badmap_Goodmap2.png?raw=true" width="50%" alt="The bad version of a London burglaries heatmap">
</p>

<details><summary><b>Answer</b></summary>

<ul>
 <li>The overlayed Ward boundaries are too detailed and don't provide any additionally useful context</li>
 <li>The basemap is far too detailed and clashes/distracts from the heatmap itself</li>
 <li>The credits text does not comply with the necessary copyright statements and is not easily identified against the basemap</li>
 <li>The overall layout and clarity of individual elements is extremely poor
</ul>
 
 <p>Below is what the map <i>could</i> look like if it were to follow the guidance:</p>
 
 <p align="left">
  <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Badmap_Goodmap2_2.png?raw=true" width="50%" alt="The good version of a London burglaries heatmap">
 </p>
</details>
