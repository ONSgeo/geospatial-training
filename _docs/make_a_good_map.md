---
title: How To Make A Good Map
description: Guidance to demonstrate good and bad practise in the creation of maps to visualise data.
---

# How To Make A Good Map

## Intro

A map is a visual representation of a physical area. A map can display data to help an audience understand the its location context better. Maps can also be helpful to tell a story about the data. Maps should serve a clear purpose, and there are many potential ways of making them depending on the underlying data and the purpose of the mapping.

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

For example, the map below clearly shows the locations of various international transit hubs in the UK. This is made clear through the effective use of colour, symbols, text, and a legend. The colours of the map make it clear that the green areas are simply there for background to give location context for the symbols. The symbols used are directly related to the place they describe e.g. a boat for a port. There is also extensive text annotation and labelling which can help identify individual locations and is also used to describe te purpose of the map. Finally, the legend clearly displays what each symbol means and thus makes it easy to refer back to the map and see what each point represents.

In additoon, there is a 'zoomed in' inset view of the South East coast. This is especially useful as the density of symbols in that area is much higher than elsewhere, and so a more detailed view can make this area more legible at a glance.

### Choropleth

A choropleth map relates data to a given area. This is achieve by colouring areas based on the valuees of the underlying data. Choropleths are probably the most common types of map used as they easily display aggregations of data with location context.

As the colouration is simply assigned to an entire area, the spatial distribution of the data can be misleading or the aggregation could simply be a result of the boundary type used. To prevent this a choropleth should use normalised data e.g. people per sq. km, cases of a disease per N population. This normalisation makes different areas directly comparable on the same colour scale.

This map demonstrates crime rates in London. The data is normalised per 100k population and is visualised at the Local Authority level.

### Graduated and Proportional Symbols

Graduated and Proportional Symbol maps are an alternative to choropleths for visualising quantities. These symbol maps vary the size of a point symbol depending on the underlying data.

A graduated symbol map does this by dividing the symbol sizes into bins, just like a choropleth does with colour, and thus displays symbols which scale from a minimum to a maximum size across these bins. Graduated symbols are the preferred type for mapping quantities as symbols as it is made clear in the legend what symbol size relates to what data range.

A proportional symbol map is similar in application, however here the size of the symbols varies directly with the underlying data values i.e. it is not split up into discrete bins. Proportional symbols are less ideal as it can result in both a large number of symbol sizes and very small differences between similar values. This makes it hard to easily identify the general scale of the data and how it varies on average from place to place.

Ideally you should use a graduated symbol map when displaying point data as different sized symbols. You should also consider the overall scale of the map and the density of points: If the symbols are very dense they can overlap and become unreadable, or they can cover up underlying geographies and thus hide their spatial context.

### Land Cover Map

### Heatmap

Heatmaps use a colour scale to display a relationship between the density of points and a given data value. Heat maps make it easy to understand the relationships between the locations of the points and overall trends in the data.
 
The map below shows this for burglaries in London. Each burglary is represented as a single point. For a given radius around each point, the more points in that radius the more intense the 'heat' and the darker the colour. Additionally, we can specify an underlying value to add weight to the map e.g. the financial loss per burglary. This will adjust the colour scale to make it clearer where there are not only a large number of instances but also which areas are the most impaceted.

### Specialised Maps

These maps are primarily used for more specialised purposes and may require a more advanced understanding of geography and data visualisation to be useful.

#### Dasymmetric Maps

A dasymmetric map is effectively a merging of the principles of a choropleth and a land cover map into one. These maps use the physical properties of an area to change the extent of the visualisation. For example, below is a map showing the density of trees per MSOA on the Isle of Wight. However, the physical reality of the area is that the trees cannot grow in certain places like on rivers, or on top of buildings. To compensate for this we can clip the boundaries of these features from the MSOA boundary.

The resulting map is a better representation of the PHYSICAL reality of the data: areas where the data CANNOT physically apply are masked out. This could for example also be applied to population maps to remove areas where nobody lives. It does, however, come at the cost of changing statistically standardised areas and therefore is only useful as either a standalone map or against maps made with the exact same methods.

#### Cartograms

Cartograms are a type of map whereby the size and shape of a geography is distorted from the real, physical reality. A number of cartograms are possible. The map below shows how a map of Wales can be changed from a normal choropleth (top left), to proportional area (top right), to an equal-area hexmap (bottom right), or a diagrammatic (Dorling) cartogram (bottom left). 

Each cartogram radically changes the visual presentation of the data and thus the ease of interpretation.

Proportional area results in highly distorted boundaries. While this adds additional weight to the differences between areas it also detracts from the spatial context.

Equal areas eliminate the common problem of choropleths misrepresenting the spatial distribution of the data within an area by removing variation between areas entirely. This is commonly seen in constituency maps as it more clearly shows how the results of an election in a given area relate to a single seat in parliament while also showing as much detail in dense urban constuencies as in larger rural ones.

---

## Colour Schemes and Symbology

Once a map type has been chosen, by far the most important property to consider is the colour scheme you will use. Different colour schemes can fundamntally change the way an audience may view and interpret a visualisation. Some colour schemes may raise an inherent bias, others may be unintuitive, and some may be unreadable for people with visual impairments such as colour blindness. Choosing the right colour scheme to counter these issues is vital. There is no absolute 'right' or 'wrong', but there are choices which offer the best looking, most impactiful, and most accessible maps.

Along with colour, the overall symbology must be considered. This includes what types of symbols to use for point data, line thicknesses, and map effects for emphasis.

### Palettes and Data

The ideal colour palette for a map depends on both the map type and the underlying data. Many different colour palettes can be used for any given map, however some may be more appropriate than others. The following subsections, taken together, describe how an appropriate palette can be chosen.

#### Conitnuous vs Discrete

One of the first considerations is whether the data mapped is made up of continuous or discrete variables.

For continuous variables, the colour palette will be a continuous 'ramp': it will vary along a gradient between different colours. This type of palette is most suitable for numeric or ordered variables where there is a clear minimum and maximum value with a range between these. A number of 'ramps (see: Colour Ramps) can be used for this data depending on it's properties.

Discrete data can also represented via a ramp if it is ordered. If, however, each feature represents a distinct class then a different type of palette may be suitable. In these cases it is often a good idea to start with a colour ramp and aply this. Then, the colours can be adjusted to be distinct across variables. For example, a choropleth for the Rural-Urban classification of LSOAs has 'rural' and 'urban' classes divided into subclasses. It would be useful to choose a different colour entirely for urban and rural classes, but to choose different shades of those colours to distinguish subclass features within the urban and rural classes e.g. shades of green for rural and shades of grey for urban. As data can often contain far more classes than distinct colours, it is not always beneficial to display all at once. Sometimes it is acceptable to create a new map for each class to show them off in more detail.

#### Colour Ramps

Colour ramps are a continuous scale of colours startring from one colour then shifting to another. In some ramps this is simplay a change from a start to an end colour, in others there could be multiple colour changes along the way. When applied to data which is split into classes, the ramp is divided out across those classes. The map below shows a choroleth with the same data represented by different ramps.

The first ramp is simply a continuous scale from a starting colour to an end colour. This type of ramp is useful when the data is on a continuous scale e.g. a range of temperatures or population density.

The secondramp uses three colours. This is a diverging ramp as there is a start and end colour, but with those beldning to form a distinct central region. This ramp is very effective to show data which diverges about a fixed value e.g. percentage increase or decrease in disease cases. These will diverge around a certain number, but may not necessarily be symmtrical around it i.e. the change will always be positive or negative, so '0' would be the centrepoint about which the data varies.

The third ramp has a random colour distribution. These ramps are useful for applying to discrete data with many classes as a starting point for further refinement. They can also be used if continuous data shows many clustered points. Caution should be taken to make sure this ramp does not become too detailed or overwhelming, and that it remains accessible.

#### Relative vs General

A point must also be considered about how people may have a bias towards a certain colour: red is 'bad', blue is 'good'; green is 'natural', grey is 'artificial'. These preconceptions can colour the interpretation of a map.

It is therefore generally advisable to choose a palette which is not strongly associated with these biases when presenting data for which there is no clear trend towards these conclusions e.g. a map of population density which ranges from blue (low) to red  (high) might suggest the higher density is 'worse' than lower density. A more neutral palette, such as viridis, might not hold these preconceptions but is still effective at differentiating the extremes.

However there are plenty of cases where it is logical to make a map based on existing associations with a colour such as a previous example of choosing green for rural areas and grey for urban: this is clearly linked to the physical appearance of the areas and therefore makes thhe distributions easier to interpret. Similarly, land cover maps may be more effective if the polygons are coloured to match the 'expected' colour the land cover type.

### Aesthetics and Accessibility

#### Ideal Palettes

#### Fills, Textures, Strokes

#### Accessibility

---

## Boundaries

### Boundaries and Data

### Mixing Boundaries

---

## Peripherals

### Legend

### Scale 

### Compass 

### Graticules

---

## Text

### Descriptive Text

#### Title

#### Accompanying Text

### Labels

---

## Basemaps

### Sources

### Styles

---

## General Map Design

### Layout

#### Insets

#### Arranging items

### Telling a Story

## Showcase: Bad and Good Maps

### Bad Map 1

### Good Map 1

### Bad Map 2

### Good Map 2

