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

### Palettes and Data

#### Converging vs Diverging

#### Conitnuous vs Discrete

#### Relative vs General

### Aesthetics and Accessibility

#### Ideal Palettes

#### Fills, Textures, Strokes

#### Colour-blindness

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

