# USSD 2021
*Track: Dam Safety or Public Safety or Other Complimentary Issues*

# The National Structure Inventory

## Abstract
Structure inventories are an important component of risk analyses, but the United States has lacked a comprehensive, accurate, and publicly available national inventory of structures that includes vulnerability attributes required for risk assessment.  The USACE in partnership with others has sought to fill this gap. Starting in 2011 USACE began developing the first National Structure Inventory (NSI), developed for use by USACE to drive dam safety modeling, levee safety modeling, and real time consequences through the Corps Water Management System (CWMS) National Implementation. The original NSI was created by translating Census-based block-level data from FEMA’s Hazus, a public domain source, into a format where points represented individual structures.  Accurate point-feature structures increase the precision, performance, and resolution or risk analysis when combined with detailed hazard data. USACE and FEMA subsequently improved the location of vulnerable structures and daytime population assignments in the NSI. In 2019, a more systematic update was undertaken to improve the quality of the data: NSI 2.0 leverages commercially available parcel attributes related to vulnerability and Microsoft Bing footprints to offer a marked improvement in structure location. The use of commercial attribute data came at the cost of restricting access to NSI 2.0 data to federal-use-only. Moving forward, the NSI team is exploring open attribute sources to allow access to NSI 2.0 for state, local, tribal, and territorial governments in the short run and full public access in the long run. This paper will outline our journey, discuss the quality of the data, describe current and future applications, and propose a path to a fully open dataset.

## Introduction/Background
Describe what NSI is, how it has been used.
The National Structure Inventory is a database that stores structure inventories. It includes an inventory built from consistent resources that covers the entire nation. The structure inventory is a point based feature for each structure placed as close to the center of the building and representing our best ability to describe the attributes of the structure. The attributes are structure category, occypancy type, construction type, foundation type, foundation height, structure value and population characteristics. The database has been avaialble since 2011, and has had three national datasets constructed across its lifespan. The initial datasets were statistical pseudo inventories, but with the latest NSI 2.0 our characterization of structure attributes and locations have greatly improved.

![](/media/Structure_ZoomedIn_Picture.png "NSI 2.0 Structures")

The flooding on the Misouri River in 2011 required a team to develop after action reviews of the flood, which needed consistently developed structure inventories for the Missouri River and Mississippi River all the way to the coast. After that study, the approach was generalized to create an inventory for the entire Nation. This was driven by the Corps Water Management Systems (CWMS) National Implementation to drive down costs of developing consequence estimation models for the nation.



Through the development of this inventory relationships between the developers and the FEMA HAZUS team have grown through the years, resulting in multiple interagency collaborations. Each collaboration collectively improved the capabilities of each agency. This paper outlines our next collaborative effort.

### Purpose
In the field of public saftey a discription of the impacts of the natural disaster is necessary to understand the significance of the diaster. This is also true in portfolio risk management to support the evaluation of priorities for the portfolio. In the case of disaster managment, the most expediant analysis is necessary. For portfolio management the analysis must be consistent.
### Historic Versions
In the United States structures are demolished and built continuously, in order to produce a database that reasonably reflects current conditions we update the inventory as frequently as we can. Decreasing the time between development requires streamlining automated processes and developing input data pipelines. Various inputs are updated at different intervals, which complicates some of these processes. Additionally, supporting portfolio management at a national scope requires stability of the inventory (or access to a stable version of the inventory) across time. These design decisions cannot be taken lightly and must be considered carefully to support the various stakeholders in this product. Here is a list of the historic NSI inventories, and some of the changes that have occured across the development time frame.

Original NSI in 2011
- HAZUS database converted to points. (Did we use the dysmetric approach in 2011? i dont think we did)
- Used Hazus Earthquake Manual to define Nighttime population
- Found many quality issues with the HAZUS data because we ran the entire nation algorithmically.

NSI 2015
- Incorporated Dysmetric Approach using NLCD urbanized data
- Incorporated 2010 census population using LEHD data
- Nighttime population assumptions based on LEHD data
- Partnered with FEMA to produce Dysmetric HAZUS databases

NSI 2019 "NSI 2.0"
- Incorperated other sources of data
  - Parcel Data from Corelogic
  - Buisness data
  - Schools data
- Restricted ability to share due to source data

The NSI was last updated in February of 2019; this version of the NSI used many data sources to improve estimates of structure locations. Structures are first generated by one of four sources. Most residential structures are generated from county parcel data, and structures are first located at the centroids of those parcels. Most non-residential structures are generated from ESRI Business Layer data and structures are first located at the available georeferenced locations, which is often a street address. Most schools are generated based on data from the National Center for Education Statistics. Finally, in census block where previous Census/HAZUS based inventories had data for structures, but no data was generated from the previously mentioned sources, this older data was brought in as a backup.
The initial structure placements are modified from their source locations based on parcel and building footprint data. In 2018, Microsoft made estimates of more than 100 million building footprints available to the general public. USACE paired these footprints with county parcel data so that instead of using the parcel centroid structures could instead assume the building footprint centroid as their X/Y location. Furthermore, many structures use the footprint’s square footage to help estimate the square footage of the structure. 
Structure values are assigned by multiplying the estimated square footage by price per square foot that varies by Occupancy Type (such as “Retail”, “Hospital”, or “Multifamily Residence). These dollars per square foot estimates were taken from 2014 HAZUS data and adjusted to 2018 price levels based on a generic construction cost index. Population assignment is completed by dividing census block level estimates among structures using a weight determined by number of employee estimates for non-residential structures and housing unit estimates for residential structures. Day and night estimates of population vary to account for the movement between residences and work places; this process relies on data from Longitudinal Employer-Household Dynamics data developed by Census.

*Add schema table*
 
Nonetheless, despite significant advancements in recent years, many of the attribute fields of the data are based on a variety of generic assumption from FEMA’s HAZUS software and other sources and have not been validated by USACE personnel. For instance, foundation heights are randomly assigned to individual structures based on regional distributions created by HAZUS in the 1990s. Because Microsoft footprints often include porches and attached garages, single-family residences are assigned total square footage and number of stories from Census data distributions based on their region and year built. Due to these limitations, analysts using the NSI have been encouraged to thoroughly inspect the data in order to ensure its quality and appropriateness for their own study areas.



### API?
Describe the API
## Need for a National Structure Inventory
Clearly articulate why something like this is needed - maybe an example from Laura, Sandy or Puerto Rico?
### Requirements for an acceptable NSI
Define requirements to make NSI applicable for all hazards and for emergency managment planning.
- Consistent
- Complete
- Timely
- Open Data

## Moving Forward
Describe plans for how we are going to meet the requirements, what are our current investigations etc.
## Concluding Remarks

