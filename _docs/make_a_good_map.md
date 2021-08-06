


## Map Design

Now that you've seen a variety of map types which can be used to visualise your data, we will now look at the specific choices to be made when designing your own maps. This section will cover boundary types, colour choices, feature symbology, additional map elements, map layouts, and what to consider in order to tell a story with a map.

### Boundaries

Boundaries refers to the area on which data is displayed e.g. an OA, LAD, County etc. These boundaries often come in different resolutions. The choice of boundary is important for both accuracy of the visualisation and for making it look good at the desired map scale.

Always make sure that the chosen boundaries are best suited to the data you wish to display. For example OAs may be more detailed than necessary or too disclosive and so MSOAs may be appropriate, or the data may be reported at a geography such as a LAD and may lose meaning if aggregated up further to Counties..

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/statistical_geography_hierarchy.png?raw=true" width="50%" alt="The same map of population density in London displayed at four different boundary aggregations.">
</p>

As shown above, the same data reported at different boundary levels can dramatically change the visual distribution of the data and therefore how it is interpreted.

#### Boundary Generalisation

Boundaries from the <a href="https://geoportal.statistics.gov.uk/" target="_blank">Open Geography Portal</a> usually come in a number of generalisations (resolutions). The image below shows what these generalisations do to the quality of the boundaries.

What generalisation you choose will depend on both what you want to visualise. A map which covers a large area with very little detail will not need a Full boundary such as BFE as this can be slow to handle in software and the detail could be distracting or hard to display. In this case, a Generalised boundary such as BGC may be better as it reduces unneeded details while preserving the overall geometry. Alternatively, there may be occasions when Super-generalised or ultra-generalised will get the job done just as well as BGC and cut out unwanted details completely.

This map shows how different boundary levels can change the amount of detail visible:

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Boundary_generalisation.png?raw=true" width="50%" alt="Visualisation of different boundary generalisations available from the geoportal.">
</p>

#### Mixing Boundaries

Sometimes it is useful to overlay one type of boundary on top of another. Care should be taken to not make the map too crowded or to cover up the most important boundaries or colours with the overlay. The map below, for example, shows data at MSOA level with LAD boundaries drawn on. It would be inappropriate, however, to draw MSOA boundaries over LAD level data as this might suggest detail at the MSOA level which is not actually present. Overlaying boundaries can also help give a sense of location if the primary boundaries are not commonly known by the target audience.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/Houses_below_60_percent_median_income_Choropleth_Mixing_Boundaries.PNG?raw=true" width="50%" alt="MSOA map with LAD boundaries on top">
</p>


### Colour Schemes and Symbology

Once a map type and boundaryu set has been chosen, the next most important property to consider is the colour scheme you will use. Different colour schemes can fundamentally change the way an audience may view and interpret a visualisation. Some colour schemes may raise an inherent bias, others may be unintuitive, and some may be unreadable for people with visual impairments like colour blindness. Choosing the right colour scheme to counter these issues is vital. There is no absolute 'right' or 'wrong', but there are choices which offer the best looking, most impactful, and most accessible maps.

Along with colour, the overall symbology must be considered. This includes what types of symbols to use for point data, line thicknesses, and map effects for emphasis.

#### Data Breaks/Classes

The way number and distribution of colours on your map will depend on the type of 'classes', from breaking the data up into ranges from one value to another, used. A number of break styles can be chosen and applied automatically in most types of GIS software. By looking at the distribution of values within your data you can assess what breaks might be appropriate. It is possible to set your break values manually, which can be useful in instances where natural breaks are perhaps too precise or not intuitive e.g. if they have too much decimal precision where rounding would be appropriate. In instances where the data contains clusters of values, Jenks (natural breaks) might be appropriate as it can automatically separate these clusters into different bins (depending on the number of classes specified. Other styles, like quantiles and equal interval, will split the data evenly and produce uniformly wide classes.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/break_types.png?raw=true" width="50%" alt="Types of data breaks/bins on Wales Median House Price data">
</p>

More advanced breaks, such as Standard Deviation, are more niche and are mainly appropriate in specific circumstances as they are not easily interpreted by non-experts.

The number of classes chosen will greatly impact a visualisation. Too few and you risk missing out data patterns; too many and you'll add complexity but no additional value to the map. Generally 4-7 classes is appropriate for a map as this offers a good compromise between the detail visible and obvious separation of classes

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/breaks_n_classes.png?raw=true" width="50%" alt="Effect of changing number of classes on Wales Median House Price data">
</p>

### Feature Symbology

#### Continuous vs Discrete Palettes

A continuous colour palette is also known as a 'ramp': it changes from one shade or hue to another by a gradient. The ramp used depends on the data being displayed. In most cases, contrinuous data which range sfrom a minimum to a maximum should be displayed with a single colour, but across different shades, as this creates a clear visual representation of 'minimum' and 'maximum' values. 


#### Relative vs General

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

Line features should follow a clear visual hierarchy. Due to their relatively limited thicknesses, differences in line colour might not be as obvious and differences in fill colour. It is for this reason that lines are usually also differentiated by <b>thickness</b> and <i>stroke</i> style e.g. full, dashed, dotted. Think of how a roadmap will demonstrate the difference between road types; motorways will be thick and bold to stand out as the 'hihgest level' of linme features, whereas  small residential streets will be thinner, usually with a less contrast-y colour, and path features like footpaths might appear as dashed lines. This creates a visual hierarchy which is easy to identify at a glance.

### Point Symbology

Most GIS software visualises points very similarly to polygons as filled-in shapes, but unlike polygons are usually scaled to be the same visual size at any map scale. Points can be differentiated by colour, size, and shape depending on the purpose of the map. a graduated symbol map will differiate by size and sometimes colour. In a general reference map points may be styled to look like boats of planes as per the infrastrcutrue locations they represent. A good rule of thumb for points is that they should be clearly visible at most scales without much overlap while contrasting against other features.


---

## Map Elements

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

A compass shows the direction of North relative to the map. A compass is a lesser-used feature in most data visualisations as it's often clear that maps default to 'up' as north. However, there are times when this may not be the case such as when the map is rotated, or the map may be taken in isolation away from the context which would otherwise signify signify. If the area shown in the map is unfamiliar to the viewer, they may also wish to have a reference to north.

While many will think of a fancy compass rose such as on old-fashioned globes which show north-east-south-west, it is perfectly acceptable to use a compass which only shows north. In the example below this is represented with a simple arrow pointing up. If the displayed map was actually offset at a certain angle from north, the arrow would also be rotated to this angle.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/compass.PNG?raw=true" width="50%" alt="Compass added to Hartlepool">
</p>

### Graticules

Graticules are lines and/or dashes within and along the edge of a map which display X and Y coordinates. Graticules are commonly seen on military maps where a combination of distance grid and decimal degrees longitude and latitude are shown.

Graticules are rarely used in basic visualisations however they are particularly important in some situations. For example, some large-scale maps such as those of entire continents can often be enhanced with the use of graticules: either as dashes on the edge of the map or lines going across it. Similarly, the mapping of any data which is known to vary with latitude and longitude can use a graticule to make this explicit. 

The graticules should be unintrusive however, so try not to use thick or bold lines and instead use thin lines with a colour which blends well with the rest of the map.

### Text

Text is very important for mapping. It provides a description of what the map represents and can be expanded into a number of areas to improve the quality of the map.

### Labels

Labels are pieces of text placed on the map itself to identify individual features or groups of features. Labels can be placed in a number of ways:

* Alongside the feature
* Around the feature
* Entirely within the feature
* Across the feature matching its shape

Which label to use depends on several factors. A dense map may only fit a few labels before becoming messy. Labels for a geography which does not easily fit the label might need the text to move along the feature. When following the geometry of a feature, labels should flow left to right, bottom to top (see map below which contains multiple label types). This ensures the label is legible. Additionally, labels should not cross over the boundary of the parent feature into another as this could suggest it belongs to multiple.

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

Insets are smaller maps within the layout of a large map used to show details which may otherwise be hard to see in the main map. These are often used to show dense urban areas e.g. Greater London, in detail, or to include features geographically separated from the main features of the map by positioning them closer e.g. the Shetland Isles which are far from Great Britain and would result in a bad map scale if shown in their actual position.

Multiple insets can be used on the same map to show off different areas of interest in greater detail. However, this can become cluttered and consideration should be taken as to if an entirely new page/map should be used for the inset feature instead.

<p align="left">
 <img src="https://github.com/ONSgeo/geospatial-training/blob/master/_docs/mapping/hartlepool_imd_map_8.jpg?raw=true" width="50%" alt="England IMD LSOA map with insets for Greater London, Hartlepool, and Isles of Scilly">
</p>


## General Map Design

This section will cover some other, more general aspects of map design, particularly arranging the layout of a map and some underlying considerations towards the purpose of the map.

### Layout

The layout of a map, that is the layout of all items on a page or image from the map itself to text and peripherals, is important for both the aesthetics of the map and ease of use.

When arranging items, it's important to consider a few things: What items are PART of the map and what items DESCRIBE the map. As a general rule, items which are actually a part of the map should clearly stand out. Boundaries should be obvious, colours clear, symbols highly visible.

#### Arranging items

When arranging items around the map, be sure to keep the focus on the map itself. Generally the map should take up the most area with other features like text, legend, scale being placed arond or on the map without covering data. For items placed outside of the main map area, these should be placed such that they follow the 'reading order': look at the map, then refer to descriptions and other items after. Items placed in the map area need to be unintrusive but clear for example a scale should be place such that it's on the map for direct reference but is not intruding upon key map features like coloured areas or labels.


## Exercise: Improving a Bad Map

This section will showcase two maps, each of which is presented as "bad" and "good". The "Bad" maps go against the guidance given in this module. Try to work out what's wrong with them before revealing the answers and the 'good' version. Both maps were created specifically for these examples and are not representations of official maps.

### Example 1
