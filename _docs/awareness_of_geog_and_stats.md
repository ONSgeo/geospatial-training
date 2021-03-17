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

![The seven pillars of the GSS Geography Policy](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/geography_policy.png?raw=true)

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
Locating geographic data means providing it with an X and Y coordinate which references a position on a coordinate reference system (CRS). Very simply put, a coordinate reference system is a way to represent positions on a 3D sphere, on a flat, 2D object. In this case we are representing points on the Earth on a 2D map. 

There are lots of different coordinate reference systems which are designed for use across different areas of the world. In the Great Britain the CRS we use is British National Grid, which is produced and maintained by <a href="https://www.ordnancesurvey.co.uk/" target="_blank">Ordnance Survey</a>, Great Britain's Mapping Agency. If you've ever used an Ordnance Survey map for walking, cycling or perhaps back in geography class at school, you'll have used British National Grid, perhaps without even knowing it!

Sometimes the data we use is provided in a different CRS than British National Grid. This isn't a problem as there are transformations we can use to convert between the two. GIS systems are also very good at doing this transformation on the fly, so you if you're just looking at data you don't need to worry about the CRS. However, there are some common mistakes that can be made by analysing data which is in different coordinate reference systems, so be careful! You can find out more if you complete the Practical Geography for Statstics course we offer, and don't forget the Geospatial team are on hand to help if needed, so please get in touch.

This is a very brief overview of locating geospatial data. In reality, geodesy is an incredibly complex field, which thankfully, you do not need to know too much more about at the moment!

![A map showing the British National Grid 10km cells overlaid on the outline of the UK.](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/bng.png?raw=true)

*British National Grid: 10 km cells*

### GSS Names and Codes
On 1st January 2011 GSS codes were introduced. GSS codes are a type of uniform resource indicator (URI) which provide a way to identify unique items. GSS codes identify individual geographic objects, for example, Local Authority Districts. 

GSS codes are comprised of two codes: a three character entity code which describes what type of statistical geography the object is, and a six digit number which refers to the unique instance of the object. 

![The structure of a GSS code showing the Portsmouth Unitary Authority as an example: E06000044.](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/entity_code.PNG?raw=true)

GSS codes can be used to look up specific areas on the <a href="http://statistics.data.gov.uk/home" target="_blank">ONS Geography Linked Data Portal</a>. This website provides a useful insight into the relationships between statistical geographies across the UK.

The <a href="https://geoportal.statistics.gov.uk/datasets/register-of-geographic-codes-april-2020-for-the-united-kingdom" target="_blank">Register of Geographic Codes</a> is the definitive list of all codes in use for UK statistical geographies. It should be used in conjunction with the <a href="https://geoportal.statistics.gov.uk/datasets/code-history-database-december-2020-for-the-united-kingdom-version-2" target="_blank">Code History Database</a> which charts historic changes in codes, which can be useful when understanding how statistical geographies have changed over time.

### Referencing Areas Correctly
Referencing areas correctly is challenging, for example, there are several Newports across the country and hundreds of High Streets so, identifying one by name alone can be fraught with error. Even when you think you are referring to one clear location you could be describing different areas, for example, towns, wards and parishes may share a common name but cover completely different areas. 

Using GSS codes to accurately refer to areas avoids problem. This is why **referencing** is one of the key pillars of the GSS Geography policy. Referencing by GSS codes also makes your life much easier as it simplifies joining statistics to areas.

## Geographic Products from ONS
ONS produce a range of geographical products for use across a number of organisations and applications. UK geographies can be very complex as they accommodate this range of uses and applications. Administrative boundaries in the UK also change frequently which results in changing and updating boundary datasets. When producing statistics we must be conscious of this to avoid errors. 

The *Heirarchical Representation of UK Statistical Geographies* provides a detailed overview of the different boundaries available and how they are associated with each other. This is a useful resource to refer back to - you can find it on the <a href="https://geoportal.statistics.gov.uk/search?collection=Document&sort=name&tags=all(DOC_HRSG%2CDEC_2020)" target="_blank">ONS Geoportal</a>

![The Hierarchical Representation of UK Statistical Geographies diagram](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/uk_geographies.PNG?raw=true)

We'll now run through some of the more frequently used geographies to be aware of.

### Administrative Geographies

**Regions**
* 9 regions in England
* No regions in Scotland, Wales or Northern Ireland.
* For UK wide representation, often England's regions are shown with the country boarders for Scotland, Wales and Northern Ireland.
* Local Authority Districts (also known as Lower Tier Local Authorities) nest within regions.

![Map showing regions in the England](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/regions.png?raw=true)

**Local Authorities**
* The Local Government structure in England is a two tier system which creates some complexity. The other UK nations have a single tier system.
* The two tier system means there are two different boundary sets for Local Authorities. Here is how they are made up in 2020:
  * Upper Tier Local Authorities (UTLA)
    * England: 151
    * Wales: 22
    * Scotland: 32
    * Northern Ireland: 11
    * **Total: 216**
  * Lower Tier Local Authorities (LTLA)
    * England:314
    * Wales: 22
    * Scotland: 32
    * Northern Ireland: 11
    * **Total: 379**
* Lower Tier Local Authorities (LTLAs) are also known as Local Authority Districts (LADs).
* Local Authority boundaries change frequently so ensure you use the correct year to avoid errors. 

![Maps showing Local Authorities in the UK](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/local_authorities.PNG?raw=true)

### Census Geographies

**Output Areas**
* Census geographies are stable, small area geographies created for non-disclosive census releases.
* These areas represent the nighttime residential population.
* They were introduced in 2001 and revised in 2011 to reflect population changes and better align with administrative units. They will be revised again in 2021.
* The geographies are built from clusters of postcodes which are aggregated to be as socially homogenous as possible, based on a range of factors.
* Each level of geograhpy has a relatively consistent population size.
* Mixtures of urban and rural areas are avoided wherever possible.
* The Census geographies are hierarchical and nest within each other, as shown in the image below.

![The hierarchy of Census geographies](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/census.PNG?raw=true)

**Workplace Zones**
* Workplace Zones are used to publish workplace related statistics
* They are a representation of the workplace population (ie. day time population distribution)

### Postcodes, UPRNs and Addresses

**Postcodes** 
ONS produce two postcode directories. Both directories provide information about which area the postcode lies in for a range of different boundary products. However, the directories have subtle differences so make sure you select the correct one based on what you're using it for.

*ONS Postcode Directory (ONSPD)*
* Postcodes are assigned to areas via direct point-in-polygon assignment (ie. overlaying postcode points on geographical boundaries to show which area the postcode lies within)
* This method provides a more accurate locational assignment.
* This directory should be used for operational purposes where an accurate postcode location is important.

*National Statistics Postcode Lookup (NSPL)*
* Postcodes are assigned to Output Areas (OAs) by point-in-polygon assignment. Then, OAs are assigned to other statistical areas by 'best-fit' method (more on this later in the course.)
* The best fit assignment can mean the postcode appears to be in the wrong place (but it isn't).
* This directory should be used for statistical production, where it is important to ensure data is assigned to the correct area within the relevant geographical hierarchy.
* It's worth noting here that 'best-fit' isn't used for certain geographies, for example, National Parks. If you want to know more about this have a look at <a href="https://geoportal.statistics.gov.uk/search?collection=Document&sort=name&tags=all(DOC_UG_BFIT)" target="_blank">'An overview of best-fitting'</a>.

**Unique Property Reference Numbers - UPRNs**
UPRNs are 12 digit reference numbers which are assigned to every addressable location in Great Britain. Addressable locations include buildings and objects like bus shelters and electricity substations. 

UPRNs are authoritative codes and can be used for data linage. At ONS, UPRNs form one of the five frames within the Reference Data Management Framework (RDMF), which enables accurate data linkage.

**UPRN Directories**
ONS produces two UPRN directories, which are similar to the postcode directories. The UPRN directories provide statistical geogrpahy information for each UPRN.

*ONS UPRN Directory (ONSUD)*
* Created by point-in-polygon assignment of UPRNs to geogrpahic boundaries.
* Provides a more exact location assignment.
* Use for operational purposes.

*National Statistics UPRN Lookup (NSUL)*
* UPRNs are assigned to output areas via point-in-polygon assignment, and then linked to other statistical geographies by best-fitting.
* URPNs can appear to be in the wrong place, but they aren't.
* Use this directory for statistical production.

## Standard Area Measurements
Standard area measurements are official measures for the area of geographic entities. They should be used whenever you are doing a calculation which uses area as a factor (eg. calculating population density). 

There are a number of types of standard area measurement which reflect different measures of the coastline and inland water. AREALHECT is the measure that is most often required, and is recommended for use when calculating statistics like population density, but you may find that the other measures are appropriate for other applications. Their definitions are available below and more information is available in the <a href="https://geoportal.statistics.gov.uk/search?collection=Document&sort=name&tags=all(DOC_UG_SAM)", target="_blank">User Guide</a>.

*Types of Standard Area Measurement*

Measure | Definition
--------| ----------
AREAEHECT | Area measurement to extent of the realm boundaries (mean low water mark) in hectares.
AREACHECT | Area measurement to coastline feature boundaries (mean high water mark) in hectares.
AREAIHECT | Area measurement of inland water features larger than 1km<sup>2</sup>.
AREALHECT | Area measurement of land area only (to coastline features and excluding inland water features larger than 1km<sup>2</sup>).


![Map illustrating the four different standard area measurements](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/sam.png?raw=true)

## Rural-Urban
There are multiple methods for defining "urban" and "rural". Two of the most common are the **Rural Urban Classification (RUC)** and **Built-up Areas (BUAs)**. 

**Built-up Areas** are defined geospatially using a 50m x 50m grid which covers the country. Each cell is classified using Ordnance Survey's MasterMap topography data; the cell is built up if over a certain proportion is covered by man-made features. When a large enough area of contiguous built-up cells is reached, that area is defined as a built-up area. Built-up areas are not strictly urban but rather developed.

**Rural Urban Classification** has a common demographic definition. Urban is defined as an area where >50% of the population belong to a built-up area with a population >10,000. This classification also includes categories such as sparse and non-sparse, according to the population density profile of an area.

**Other methods** of defining rural-urban are often adjusted versions of BUAs which comply with different boundary types (for example. major towns and cities).

## Area Classifications
Area classifications are an analysis of people by where they live. Areas can be classified by the characteristics and attitudes of those who live in them. This is based on the concept that similar people with similar characteristics are more likely to live wihtin the same locality. These area types will be distributed in different geographical space.

The Output Area Classification (OAC) is a commonly used area classification derived from Census data. You can investigate the 2011 OAC via <a href="https://oac.datashine.org.uk/#datalayer=oac11_s&layers=BTTT&zoom=12&lon=-0.1500&lat=51.5200" target="_blank>this interactive map</a>.

![A map showing an example of the OAC for Southampton and Portsmouth ](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/awareness_of_geog_and_stats/oac.png?raw=true)


# Where to get data



    



