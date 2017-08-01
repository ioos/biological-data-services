---
title: IOOS Biological Data Services Enrollment Procedure
tags: []
keywords: notes, tips, cautions, warnings, admonitions
last_updated: July 3, 2016
summary: This document describes the data enrollment procedure proposed by IOOS DMAC to support sharing and integration of aquatic biological data.
sidebar: mydoc_sidebar
#topnav: topnav
toc: false
#permalink: sos-wsdd-github-notoc.html
---

<!--  
* TOC
{:toc}
 -->

<!--
_ However these data services are applicable to any aquatic taxa that have presence, absence and abundance information._

_The document has the following major sections:_

- _**IOOS Basic Principle**<br>Describes the IOOS data principle for sharing ocean observing data._
- _**IOOS Biological Data Flow** <br>Describes the biological data flow from IOOS Data providers through IOOS Regional Association to US IOOS DMAC system._
- _**Enrollment Procedure** <br>Defines the types of enrollment procedure and the steps of enrolling a data provider._

 
&nbsp; <br>
&nbsp; <br>


## **INTRODUCTION**{: style="color: crimson"}
-->

>**_“This IOOS Biological data solutions and linking to users applications will allow people to do research that simply could not  be done before due to access and format challenges.  It will save weeks to months of time acquiring, reformatting,  understanding the collection techniques and conducting the analyses”_**
>
>Mitch Roffer (ROFFS TM Inc.)

>**_“The obtainable consistency of the biological data due to standards, as well as the richness and standard approach to detailed circumstances of observation, are what enable IOOS Biological Data for applications”_**
>
Philip Goldstein (OBIS-USA)


## **BASIC PRINCIPLE**{: style="color: crimson"}

IOOS was established with the core principle that observation data should be made freely available to all. This has implications: 

  1. Data providers must be made aware that their data will be offered freely through IOOS.
   
  2. Data providers will be responsible for restricting access to any data which may be too sensitive for general release (e.g. location data for endangered species). Providers are free to manage such control in any way that makes sense in their context.

## **IOOS BIOLOGICAL DATA FLOW**{: style="color: crimson"}

Data flow is represented in [**Figure 1**](#Fig-1). IOOS Regional Associations (RA) can enroll biological data providers (i.e. IOOS Biological Core variables: fish species, fish abundance, zooplankton species, zooplankton abundance and phytoplankton species) following the IOOS enrollment procedure outlined and register their web services to the [IOOS Registry](http://www.ioos.noaa.gov/catalog/register.html). For broader dissemination, the IOOS registry will then connect the data to other data portals such as  [Data.gov](http://www.data.gov/), [OBIS](http://www.usgs.gov/obis-usa/), [NMFS InPort](https://inport.nmfs.noaa.gov/inport/), etc., and national Archiving Center ([NOAA's National Centers for Environmental Information (NCEI), formerly the National Oceanographic Data Center (NODC)](http://www.nodc.noaa.gov/)), and make the data accessible to data users.

<a name="Fig-1"></a>
&nbsp; <br> 

![IOOS Biological data flow](/biological-data-services-jekyll/img-fig-1-mod.jpg) 

**Figure 1. IOOS Biological data flow: from data providers through RAs to IOOS Registry/Catalog/Viewer <br>(i.e. US IOOS Portal) and other National portals (e.g. OBIS-USA, Data.gov, NMFS InPORT) and archiving center (NCEI).** 

&nbsp; <br>

Data providers can provide their biological data to RAs through accepted RAs webservice, database connection or data extract. RAs will then enroll the data using IOOS Biological Data Services (IOOS BDS) enrollment procedure (see below) and register the data to US IOOS service registry. The data users (e.g. scientists, managers) can access the data from US IOOS portal, RA portals or from other national portal and archiving center (NCEI) in a standard form.

In order for an RA to enroll biological data in the IOOS DMAC system, the RA must first agree to the following:

- The RA will work with their region’s data providers to enroll their data through IOOS DMAC system. This will include assisting/training the data providers in formatting their original data into IOOS Biological Data Services terms (IOOS BDS) to enhance standardization and integration with IOOS system, configuring the access service and helping data to serve data and how to help the data providers to improve discovery metadata.
- The RA will deploy standard-based data access services such as [ERDDAP](http://coastwatch.pfeg.noaa.gov/erddap/index.html) and/or other accepted IOOS data access service ([see details here](http://www.ioos.noaa.gov/data/contribute_data.html)).
- The RA will ensure that the data gets registered into the IOOS service registry according to the IOOS DMAC guidance that can be found [here](https://github.com/ioos/registry)

## **ENROLLMENT PROCEDURE**{: style="color: crimson"}

Data providers can provide their data set in electronic form to the RA in their region. Then, the RA will publish the data. The RA will then work with the provider to determine the necessary steps to ensure the data are compliant with IOOS BDS. Data providers, in turn, will work with the RA to complete the necessary data transformation according to IOOS BDS [Guidelines](http://ioos.github.io/biological-data-services/biological-observations/) and [Standard Vocabulary](http://mmisw.org/ont/ioos/biological).

Documentation and reference examples for the aspects of the enrollment process will be continually updated with community engagement. Further, the RA will provide resources (DMAC Coordinator and DMAC team) to assist the data provider with the enrollment process while continuing the essential involvement of data providers who know the content-specific details. Then, the RA will then publish the data via web services.

The optimal model for sharing data for a prospective provider depends on whether or not the group or individual is interested in maintaining their own data server and whether or not they expect to be making regular updates to the data set.

The IOOS model is one of a network of distributed data services. One benefit of such a model is data providers maintain and control distribution of their own data while at the same time these data are exposed through the wider network. However, it is recognized that many providers may not have the resources or interest in maintaining local data services. In these cases the RA can act as the initial data access point.

The following section of this document describe the steps ([**Figure 2**](#Fig-2)) by which an RA would enroll biological data providers in their region.

<a name="Fig-2"></a> 
&nbsp; <br>

![Procedure steps](/biological-data-services-jekyll/img-fig-2-mod.jpg) 

**Figure 2. Biological data provider’s enrollment procedure steps.**

&nbsp; <br>

Data files are the most common way for data providers to send their data to the RA. Data in relational databases can be dumped to data files are the next format that data providers use to transfer the data.

The core component of IOOS BDS is an occurrence record. An occurrence is an observer's, or an observing system's record of a named taxon at a specific location and time along with detailed information about the circumstances of the observation. A collection of occurrence records forms a database-like table of data, with columns (each with a specific type of information) and rows (each with an occurrence record). Though occurrence information can exist in other data structures, a table with columns and rows is a helpful model.

Occurrence data can be made more consistent by using standard observation methods and by following standards, such as IOOS BDS, for formatting and presenting the data. Data that is more consistent is more useful.
 
### **Step \# 1: Format Occurrence Data to enroll data in IOOS BDS**{: style="color: crimson"}

The goal is to obtain data in taxon-location-time format. The RA will work with the provider in two steps: (1a) verify that the contents of the dataset do in fact contain occurrence information (observed taxon-location-date-details), and (1b) perform data manipulation, such as relational joins, to gather the occurrence data in a single table with columns and rows with each row representing a taxon-specific occurrence. A row may represent a group of occurences, after binning by sex, size, or other characteristics of biology or the observation method, or they may be aggregated as totals without division into such bins. Each column from left to right across the row represents detail about the occurrence. For more on the use and meaning of each column, see [Step \#3](/biological-data-procedure/#step--3-format-data-to-ioos-bds).

### **Step \# 2: Gather Human Metadata**{: style="color: crimson"}

The RA will work with the data providers to gather descriptive metadata for the datasets, including: title, summary/abstract, the data provider’s name and email address, the recommended way to cite the dataset, keywords, georeference method, coordinate uncertainty, taxonomic identification details, the sampling protocol / effort / conditions, derived data calculation methods (e.g. for fish abundance
estimate), history, and related resources.

_**Machine metadata**_ is metadata can be generated from the data. See [Step \#4](/biological-data-procedure/#toc_11). This will be done by RA data staff.

_**Human metadata**_ refers to essential descriptive details, vital to effective use of the data, which must be gathered, written, edited by humans. Human metadata cannot be generated automatically from the contents of a dataset. Human metadata is the principle method used to capture expertise from the data providers; the RA data staff will assist in every way feasible.

### **Step \# 3: Format Data to IOOS BDS**{: style="color: crimson"}

This step involves matching columns in the provider’s data table with IOOS BDS terms (on [GitHub](http://ioos.github.io/biological-data-services/biological-observations/) or in [MMI](http://mmisw.org/ont/ioos/biological)) and documenting exceptions, questions, and issues that need any kind of follow-up. This step requires a thorough understanding of how each term is used in the original data table as well as a thorough understanding of the IOOS BDS terms. In many cases, terms in the original data table map directly to IOOS BDS terms, and a rich, standardized dataset can be created. In other cases, columns of data from the original data table need to be modified or reformatted to match the IOOS BDS specification. Precise attention to data formats and term definitions is required. IOOS Biology terms are specific: they are not used as "catch-all" terms that have general or approximate meaning. An "enrollment journal" approach is recommended (See example in Appendix). An enrollment journal is a document with a table that contains columns for: the IOOS Biology term, the definition of the IOOS Biology term, the name of the corresponding column in the original data, and documentation/comments regarding format changes or conversion requirements, related issues, processing details, and other issues that need further investigation. The enrollment journal is intended to be a multi-party document where enrollers and RA staff can communicate such issues and questions among those whose expertise is required to resolve the issues and complete the enrollment. The enrollment journal encourages an analytical, quality-based approach to gaining consensus of multiple parties within the data provider’s organization and the RA as to the best way to depict the original data in the IOOS BDS standard. The enrollment journal also provides a rich method to gather and refine information that will go into the human metadata that describes the dataset and how it was made available via IOOS BDS.

### **Step \# 4: Generate Machine Metadata**{: style="color: crimson"}

_**Machine metadata**_ is metadata that can be generated from data.
Examples: number of records, number of taxa and locations, date range, ranges and enumeration of other values, and geographic extent.

Other machine metadata comes from the IOOS BDS terminology definitions.

### **Step \# 5: Convert Metadata to ISO 19115 XML**{: style="color: crimson"}

IOOS recommends using ISO 19115 XML for metadata standards. In this step, the RA data staff can assist data providers with creating an ISO 19115 metadata document that follows the ISO 19115 guidance from NGDC and NCDDC. See [Category:ISO 19115](https://geo-ide.noaa.gov/wiki/index.php?title=Category%3AISO_19115) in NOAA Environmental Data Management Wiki. Or, if an RA is using ERDDAP, then [ERDDAP will automatically generate the ISO and FGDC XML documents](http://coastwatch.pfeg.noaa.gov/erddap/download/setupDatasetsXml.html#globalAttributes).

### **Step \# 6: Create Service Configurations**{: style="color: crimson"}

If the dataset will be published via ERDDAP, an [XML description of the dataset](http://coastwatch.pfeg.noaa.gov/erddap/download/setupDatasetsXml.html) needs to be created so that ERDDAP knows how to access the data and how to present the data to users.

### **Step \# 7: Publish Metadata**{: style="color: crimson"}

The dataset’s metadata, or a link to it, must be distributed to [IOOS Service Registry](https://github.com/ioos/registry). IOOS Registry then will make it available to desired locations, such as repositories (e.g., NASA GCMD etc.), portals (e.g., Data.gov), search engines, or other systems that can utilize the metadata. Requirements for this step include assuring that the master copy of metadata is under control, and that there are procedures in place to assure that all secondary copies will get updated whenever the master copy is changed.

### **Step \# 8: Archive with NOAA's National Centers for Environmental Information (NCEI)**{: style="color: crimson"}

Send the new dataset (data and metadata) to NCEI. This should be done with the process that is already in place between NOAA IOOS Program Office, RAs and NCEI to [archive observing data](https://www.ncdc.noaa.gov/customer-support/archiving-your-data-ncdc). Two important aspects of this coordination with NCEI are (1) make sure that NCEI has the same version of the data (i.e., the same snapshot in the lifecycle of the data contents) that IOOS is serving, and (2) as much as possible, the same metadata should be used by IOOS BDS and NCEI.

### **Step \# 9: Synchronizing data and metadata with OBIS-USA and IOOS System**{: style="color: crimson"}

This step requires OBIS-USA to establish a relationship with IOOS to query the IOOS Service Registry/Catalog and vise-versa. Since OBIS-USA is a national resource for discovery, attribution, access, and use of data from any and all US marine biogeographical data sources, each RAs data providers dataset's participation in OBIS-USA via IOOS can be an additional means of discovery, referral and attribution for IOOS data. In most cases, OBIS- USA will carry a more limited "biogeographic" form of data, with a reduced level of detail, than the IOOS nodes will be serving. If users find data at OBIS-USA and want more detailed data, they will be referred to the IOOS service.

The practical steps of integrating with OBIS-USA will largely be accomplished by IOOS's enrollment/publication process, due to the shared definitions within IOOS BDS and OBIS- USA's MBG (Marine BioGeography) standard, as well as common metadata practices.

## **ENROLLMENT JOURNAL TO DEVELOP A DATA RESOURCE FOR IOOS BDS**{: style="color: crimson"}

An example of the Enrollment Journal may be found in the [APPENDIX](https://github.com/abirger/biological-data-services/blob/master/doc/IOOS_BDS_ENROLLEMENT_PROCESS_Draft_vs1.0.pdf) section of the PDF version of the document. The example encompasses the [Comparative Assessment of Gulf Estuarine Systems (CAGES) Louisiana](http://www.galvestonlab.sefsc.noaa.gov/stories/2013/ecology/) performed by NOAA Southeast Fisheries Science Center Galveston Lab.

## **REFERENCE INFORMATION**{: style="color: crimson"}

### **Contribution**{: style="color: crimson"}

| Name  | Association  |
|:---|:---|
|[**Hassan Moustahfid**](Hassan.Moustahfid@noaa.gov) | NOAA, U.S. Integrated Ocean Observing System Program Office (**corresponding author**) |
| **Philip Goldstein** | University of Colorado/Ocean Biogeographic Information System-USA, Boulder, CO |

### **Validation**{: style="color: crimson"}

| Name  | Association  |
|:---|:---|
|**Zdenka Willis** | Director of U.S. Integrated Ocean Observing System Program Office |

### **Revisions**{: style="color: crimson"}

| Date | Author | Version | Notes 
| ------ | ---------- | ------------| ---------                                                      
|August 15, 2013 | Hassan Moustahfid | 0.9 | Created
|September 4-6, 2013 | Philip Goldstein | 0.9 | Added information to "Enrollment Procedure" section; added text, pp 9, 12, 13, 14; appended enrollment journal, pp 15-49
|September 6, 2013 | Hassan Moustahfid | 0.9 | Edits and revision to the drafts
|December 20, 2013  | Hassan Moustahfid | 0.9 | Final changes and edits
|January 10, 2014 | Hassan Moustahfid  | 0.9 | Revised in response to Charly Alexander, Rob Ragsdale and Derrick Snowden (US IOOS) comments
| February 14, 2014  | Hassan Moustahfid | 0.9 | Revised in response to Jim Potemra (PACIOOS), Vembu Subramanian (SECOORA), Matt Howard (GCOOS-RA) and Bob Simons (NOAA/SWFSC/ER) comments/edits.
| March 28, 2014  | Hassan Moustahfid | 1.0       
                                                           
 
### **Endorsement Disclaimer**{: style="color: crimson"}

Mention of a commercial company or product does not constitute an endorsement by NOAA. Use of information from this publication for publicity or advertising purposes concerning proprietary products or the tests of such products is not authorized

### **Acknowledgments**{: style="color: crimson"}

Special thanks go to Jim Potemra (PacIOOS), Vembu Subramanian (SECOORA), Matt Howard (GCOOS), Bob Simons (NOAA/SWFSC/ERD) and Charles Alexander, Rob Ragsdale and Derrick Snowden (U.S. IOOS) for comments and suggestions that considerably improved this document content.

### **Citations**{: style="color: crimson"}

1. [Guidance for Implementation of the Integrated Ocean Observing System (IOOS) Data Management and Communications (DMAC) Subsystem](https://ioos.noaa.gov/data/contribute-data/)

2. [IOOS Biological Data Terminology](http://mmisw.org/ont/ioos/biological)

3. [ISO 19115 Metadata Standard for Geographic Data NOAA NGDC](https://geo-ide.noaa.gov/wiki/index.php?title=Category%3AISO_19115)

4. [IOOS Service Registry](https://github.com/ioos/registry)

&nbsp; <br>
