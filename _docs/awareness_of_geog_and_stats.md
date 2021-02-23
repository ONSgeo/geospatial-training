---
title: Awareness of Geography and Statistics
description: An introduction to geography for statistics. Helping you understand why geography matters.
---

# Awareness of Geography and Statistics

## Course Summary
### Introduction
This short course provides an overview of why geography matters for statistics.

It will give an introduction to what you need to know to unlock the geography in your data and where to get help if you get stuck.

### Estimated time for course
1 hour

### Audience
Those managing work which incorporates aspects of geography

### Course Aims
This course covers:
* Why geography matters for statistics
* How to use geography correctly
* Understanding geographic data 
* Introducing Geographic Information Systems (GIS) and geospatial techniques 


---

## Location Matters

### Introduction

*Everything happens somewhere*

Every time we receive a response to a survey, knock on a door or receive data from a supplier there is location associated with that data.
In some cases the data is for single address or businesses – in others it relates to a Postcode, a Ward or a Local Authority or one of a whole range of other geographies that we will cover later.

Most times when we produce statistics they are also about places – sometimes the whole country but often for Local Authorities, health areas or much smaller geographies such as Wards or the Output Areas associated with Census.


### Three key reasons that geography matters

1. Geography is fundamental to the way we produce statistics - if we don’t get the geography right there is real risk that we will damage the quality of our statistics.
2. As we pull more data together in ONS , geography provides a great way to integrate between topics and across themes – often location will be the only element that disparate datasets hold in common.
3. Spatial relationships matter and there are a wealth of well established and emerging spatial tools available to help us lever more information out of our data.

### The importance of Geography in Statistics

Getting the geography right is critical throughout the statistical production journey.

Datasets from Ordnance Survey or other data providers help form the address or postcode frames used to run surveys or spines of reference data used to link and locate administrative sources. 

At ONS, geography experts in Data Architecture maintain key reference data sets such as the Address and Business indexes, look-up tables between geographies and names and code lists used to reference our outputs. By linking the data  we collect to these frames and cutting the data using look-ups and boundary sets it is possible to produce statistics.

Geographic tools allow this production, as well as helping us analyse the data and provide access via the website. Get any of this wrong and the statistics will be wrong.

### The great integrator
Location is a great way of integrating disparate datasets  – it is universal and common to almost all ONS and public sector data. The location in our data therefore provides a powerful way of integrating across topics – social, economic and environmental themes for example.

As we add more administrative data, big-data and other sources to our data stores location can form an invaluable frame, bringing topics together for the first time.

> [Spatial data is] “the connective tissue of open data” 
*Sir Nigel Shadbolt*

### Spatial tools – GIS and Geospatial analysis
Mapping and visualisation of spatial data, both for analysis to enhance our products on the web, can greatly improve understanding and accessibility to our statistics. The use of GIS (Geographic Information Systems – see later) allow us to manage and analyse our data. Analysis of spatial patterns over time and potentially in real-time can unlock new understanding and new views on the data we have never had before.

Spatial tools and linkage also opens opportunities for the analysis of data far beyond what we are used to working with now. Data and big-data from smart cars, roads and buildings, as well as the ‘Internet of Things’ all have a geospatial dimension and this will be increasingly important in describing and understanding the economy, the environment and society in future. Geographic tools will enable us to manage and make use of these sources.


## Geography Policy

### GSS Geography Policy
The [Government Statistical Service (GSS) Geography Policy](https://gss.civilservice.gov.uk/wp-content/uploads/2018/03/GSS-Geography-Policy-6.pdf) underpins the approach to geography across ONS and the GSS. 

The policy outlines seven key pillars which underpin the best practice around using geography with statistics.

![The seven pillars of the GSS Geography](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/geography_policy.png?raw=true)

### Key Geography Policies

As a user of geographic data from ONS, you should be particularly aware of the policies outlined below, which will directly impact your work.

**Referencing** Reference data, at source, at the lowest possible geographic level and using a standard identifier.

**Naming and coding** There are official codes and an approach for introducing new codes for all standard geographies. Use the official codes and avoid making up your own codes for geographic areas. Using official codes will cause less confusion and it will be easier to share data.

**Presentation order** When publishing lists of statistics for areas there are defined GSS guidelines outlining the order of areas. Generally, when entities are presented in groupings (e.g. districts within county, wards within district), the order of presentation at each level of the grouping hierarchy is alphabetic.

**Standard area measurement** For official statistics there are official areas calculated in hectares which should be used. When you want to include the area of a particular geographic area – say a Ward or District (for example if you want to calculate the population density) - use the standard area measurement, rather than the value calculated by your GIS.

**Classifications** There are a number of geographic classifications agreed for use across the GSS (and for the constituent nations of the UK) covering Urban/rural classification, area classifications, Workplace Zones etc. Use those rather than reinventing the wheel.


## Geographic Data

### Types of Geographic Data

Geographic data comes in two fundamental formats: vector and raster. Using these two formats we can represent any data with a location associated to it.

### Vector Data

Vector data comes in three types:

* **Points** Individual locations which are represented by an X and Y coordinate. Eg.addresses, the centre of a postcodes, locations obtained from GPS. 
* **Lines** A series of two or more connected points. Eg. road network, rivers.
* **Polygons** A series of connected points which enclose a homogeneous area. Eg. ONS boundary products like LSOAs or Local Authorities.

![Geographic data types: vectors - points, lines and polygons](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/vectors.gif?raw=true)

*Image from [Esri](https://desktop.arcgis.com/en/arcmap/10.3/manage-data/geodatabases/feature-class-basics.htm)*

In the statistical domain you will most often deal with vector data and within that, most commonly point or polygon types. Much of the data that ONS collects or uses is linked to a location, most commonly via a postcode or address, unique property reference number (UPRN) or GSS geography code. This allows us to link data together easily and accurately, and then produce statistics. We can think of postcodes, addresses and UPRNs as point data (pairs of XY coordinates); GSS geography codes allow us to link to the associated geographical boundaries, or polygons.


### Rasters

Raster data is represented by a grid or equal sized cells, with a value for each cell. The most common example of raster data is an image and in the geographical context, this is often data collected by satellites, aerial imaging or data collected by drone (all often referred to as Earth observation data). Raster data is often large, and can need specialist tools to analyse properly. 

![Geographic data types: rasters](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/raster.png?raw=true)

Many types of environmental data are collected in raster format. In the statistical realm you are less likely to come across raster data, although there are applications for it, for example in work undertaken by Natural Capital and for the Sustainable Development Goals.


### Look-ups and Code Lists

Look-ups and code lists provide the links between the different geographies that ONS produce, and the codes that relate to each geographic area. By allocating the correct codes to the data we collect it is possible to use look-ups to aggregate data to a huge range of different geographies.

The most commonly used look-ups at ONS link postcode or address to administrative areas (such as Wards, Parishes or Local Authorities). Other look-ups  link between different types of areas (for example, between Output Areas and Parliamentary Constituencies or health areas). Some look-ups define how different units nest or relate to each other in a hierarchy.

Make sure you use the official codes wherever possible (rather than the names of areas) and link to the tables for the right date to avoid errors.

## Working with Geographic Data

### Locating Data




### GSS Names and Codes