---
title: IOOS Biological Observations Data Services
tags: [BDS,"Biological Data Services",IOOS,observations]
keywords: notes, tips, cautions, warnings, admonitions
last_updated: July 3, 2016
summary: The objective of the IOOS Biological Observations Services is to develop and deploy an efficient and effective information infrastructure for biological observations, adding components and links as necessary to serve end-users.
toc: false
#permalink: sos-wsdd-github-notoc.html
---

<!--  
* TOC
{:toc}
-->


## **Introduction**{: style="color: crimson"}

The IOOS Biological Observations Data Services address the Data Management and Communications (DMAC) requirements that pertain to biological observations standards and interoperability applicable to U.S. IOOS and to various observing systems. Biological observations are highly heterogeneous and the variety of formats, logical structures, and sampling methods create significant challenges.

## **Biological Data Standards**{: style="color: crimson"}

The IOOS Biological Observations Data Services had adopted/adapted or had built the following data standards:

* Schema Terminology will be based on ratified [Darwin core](http://rs.tdwg.org/dwc/), [Dublin core](http://dublincore.org/documents/dces/) and proposed IOOS vocabularies. XML guide will also based on Darwin core XML guidance.
* [CF Conventions](http://cfconventions.org/) had been applied to biological data definition at the field level. This is to assure that IOOS Biological Project will be compatible with other geophysical datasets.
* [FGDC Content Standard for Digital Geospatial Metadata (CSDGM)](http://www.fgdc.gov/metadata/geospatial-metadata-standards#csdgm) and [ISO 19115-2](http://service.ncddc.noaa.gov/rdn/www/metadata-standards/documents/MI-Metadata.pdf) are the adopted Metadata standards.
* [ERDDAP](http://coastwatch.pfeg.noaa.gov/erddap/index.html) is the main webservice for this project.
* [Environmental Data Connector (EDC)](http://www.pfeg.noaa.gov/products/EDC/) is the client developed to connect directly to ERDDAP and access data using customer application tools such as [ArcGIS](http://www.esri.com/software/arcgis) and [R Project](http://www.r-project.org/).
* To learn more about the biological data standards implemented at the Pacific Islands Region please follow the following links:
  - [Biological data services at the Pacific Islands Region website](http://pacioos-mapserver2.ancl.hawaii.edu/erddap/info/index.html?page=1&itemsPerPage=1000)
  - [FGDC and ISO Metadata](http://oos.soest.hawaii.edu/cgi-bin/get_metadata.py?id=PACN_FISH_TRANSECT&format=fgdc)

<br>
<br>


## **IOOS Biological Data Terminology**{: style="color: crimson"}

The IOOS Biological Data terminology is a list of data fields with names, descriptions, and format notes. It was based on ratified Darwin core, Dublin core and proposed IOOS vocabularies. XML guide was based on Darwin core XML guidance. CF Conventions had been applied to biological data definition at the field level. This is to assure that IOOS Biological Project will be compatible with other IOOS geophysical datasets. In order to “map” your database fields to the IOOS Biological Data terminology fields you will need to download the following files.

### **Current Revision**{: style="color: crimson"}

* [US IOOS and OBIS-USA Marine Biogeography Terms v2.1 @ Marine Metadata Interoperability (MMI) Ontology Registry and Repository (ORR) Website](http://mmisw.org/ont/ioos/marine_biogeography).
* Submitted by Philip Goldstein, USGS/OBIS-USA on 2016-05-13.

#### &nbsp; &nbsp; _**Definitions**_{: style="color: crimson"}

|	Term	|	Darwin Core or Extension	|	Definition |   Section |    Reference
|  -------------	| --------------------------------------------- | ----------------- | ------------ | ----------------
|aggregator|MBG Common Terms Extension|The name of an institution also involved in gathering or developing this data, in between the data originator and OBIS-USA.|RecordOrigination|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|altitude|MBG Common Terms Extension|The altitude or elevation of the surface of the water, in meters above sea level, in which the observation was made. "altitude" is expressed as a single value rather than the min and max as in DwC. Work with a representative of the original data to determine what is the preferred way to represent single value and min/max, as necessary. This single value named "altitude" is required for ERDDAP and Climate and Forecast compatibility.|Elevation|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|aphiaID|MBG Fish Abundance Extension|A unique taxon identifier obtained by validation of the taxon name with the World Register of Marine Species (WoRMS), www.marinespecies.org.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|associatedMetadata|MBG Common Terms Extension|Identifier(s) or url(s) that identify the reference copy (system of record) of metadata associated with the datasetID. OBIS-USA practice is to name the metadata file with the contents of the "datasetID" term, to make a durable connection between data and metadata.|AdminAndId|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|associatedReferences|Ratified Darwin Core|A list (concatenated and separated) of identifiers (publication, bibliographic reference, global unique identifier, URI) of literature associated with the Occurrence. Use this to reference literature that was the source of biogeographic information in some cases; an example is occurrences that formerly had 'derivedFromLiterature' as the "basisOfRecord".|AdminAndId|[http://rs.tdwg.org/dwc/terms/#associatedReferences](http://rs.tdwg.org/dwc/terms/#associatedReferences)
|associatedSequences|Ratified Darwin Core|A list (concatenated and separated) of identifiers (publication, global unique identifier, URI) of genetic sequence information associated with the Occurrence. Use this for example to record GenBank accession number(s) associated with an observed taxon.|OccurrenceDetail|[http://rs.tdwg.org/dwc/terms/#associatedSequences](http://rs.tdwg.org/dwc/terms/#associatedSequences)
|basisOfRecord|Ratified Darwin Core|Identifies the source of information or observation that generated the biological occurrence record.|RecordOrigination|[http://rs.tdwg.org/dwc/terms/#basisOfRecord](http://rs.tdwg.org/dwc/terms/#basisOfRecord)
|bearingToAnimals|MBG VLTS Extension|Horizontal angle in degrees between the trackline and the line to the animal or group of animals when first sighted, even if a reliable species identification has not yet been made. The trackline is defined as the line of travel that the platform is actually doing, which may not necessarily be the proposed line that was in the original design. Calculate the bearing from 0 toward 359.999 degrees offset clockwise from 0 degrees, where 0 = 360 degrees. Assuming the platform is traveling forwards, the line of travel on the trackline, which is the front of the platform (e.g. bow of ship or front of plane) is at zero degrees bearing. For groups of animals, use the bearing for the approximate geometric center of the group of animals when first sighted.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|beaufortSeaState|MBG VLTS Extension|Number corresponding to Beaufort sea state (scale 0 to 12) to describe sea conditions|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|behavior|Ratified Darwin Core|Verbatim description of the behavior shown by the subject at the time the occurrence was recorded. For example, swimming, charging, spy hopping. If behavioral codes are used in this term, they must be used consistently within a dataset and they must be explained in metadata.|OccurrenceDetail|[http://rs.tdwg.org/dwc/terms/#behavior](http://rs.tdwg.org/dwc/terms/#behavior)
|bibliographicCitation|Ratified Darwin Core|A bibliographic reference for the resource as a statement indicating how this record should be cited (attributed) when used. Recommended practice is to include sufficient bibliographic detail to identify the resource as unambiguously as possible.|AdminAndId|[http://rs.tdwg.org/dwc/terms/#dcterms:bibliographicCitation](http://rs.tdwg.org/dwc/terms/#dcterms:bibliographicCitation)
|bottomType|MBG Fish Abundance Extension|A description or identifier of general information about the sea floor at the coordinates or locality where the observation was made. Vocabulary will be consistent within a dataset and will be explained in metadata. Methods of determination (where applicable) will be explained in metadata.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|catalogNumber|Ratified Darwin Core|A record identifier provided by the data originator. The identifier is controlled by the data originator and reflects the originator's practices of data administration. Special concerns about the identifier, such as whether it is unique, how it is controlled, if it is persistent, or if it contains embedded information, can be addressed in metadata if applicable.|AdminAndId|[http://rs.tdwg.org/dwc/terms/#catalogNumber](http://rs.tdwg.org/dwc/terms/#catalogNumber)
|class|Ratified Darwin Core|The full scientific name of the class in which the taxon is classified.|HigherTaxonomy|[http://rs.tdwg.org/dwc/terms/#class](http://rs.tdwg.org/dwc/terms/#class)
|collectionCode|Ratified Darwin Core|An identifier for a subset(s) of data within the dataset, partitioned by methods or parameters meaningful to the data originators. The system and purpose for defining and partitioning by collectionCode within a dataset will be explained in metadata.|AdminAndId|[http://rs.tdwg.org/dwc/terms/#collectionCode](http://rs.tdwg.org/dwc/terms/#collectionCode)
|coordinateUncertaintyInMeters|Ratified Darwin Core|An expression in meters of the overall uncertainty of the georeference provided by the latitude and longitude data. The uncertainty can combine issues of both accuracy and precision, and depends on the method the data originator used to determine coordinates. Methods and considerations that go into determinations of uncertainty will be described in metadata.|Georeference|[http://rs.tdwg.org/dwc/terms/#coordinateUncertaintyInMeters](http://rs.tdwg.org/dwc/terms/#coordinateUncertaintyInMeters)
|country|Ratified Darwin Core|The name of the country in which the observation location occurs. Such geographic named locations may not be available or applicable for marine data, and accordingly the use of this term is optional. In some cases such jurisdiction identification may be crucial for data attribution, management and/or use, so this term is retained in the terminology for cases where it may be essential.|NamedGeography|[http://rs.tdwg.org/dwc/terms/#country](http://rs.tdwg.org/dwc/terms/#country)
|county|Ratified Darwin Core|The name of the county or other comparable geographic unit in which the observation location occurs. Such geographic named locations may not be available or applicable for marine data, and accordingly the use of this term is optional. In some cases such jurisdiction identification may be crucial for data attribution, management and/or use, so this term is retained in the terminology for cases where it may be essential.|NamedGeography|[http://rs.tdwg.org/dwc/terms/#county](http://rs.tdwg.org/dwc/terms/#county)
|datasetID|Ratified Darwin Core|An abbreviated name for the dataset that contains the occurrence record. This may also be the technical name for the data resource in a database or web service. The datasetID occurs on each row to preserve record identity in case records served by the resource become distributed to other resources or applications.|AdminAndId|[http://rs.tdwg.org/dwc/terms/#datasetID](http://rs.tdwg.org/dwc/terms/#datasetID)
|datasetName|Ratified Darwin Core|This is a long-form name for the dataset, more explanatory than the DatasetID. The DatasetName will read as a recognizable title that reflects information about the dataset. Suggested information to include in the datasetName can refer to originator, content, purpose, method, geography, or other characteristics of the dataset. This datasetName term in the data record will match the dataset name in metadata.|AdminAndId|[http://rs.tdwg.org/dwc/terms/#datasetName](http://rs.tdwg.org/dwc/terms/#datasetName)
|dateIdentified|Ratified Darwin Core|The date the identification on this record was made, expressed in ISO 8601 date format.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#dateIdentified](http://rs.tdwg.org/dwc/terms/#dateIdentified)
|depth|MBG Common Terms Extension|The depth below the surface of the water, in meters, at which the observation was made. "depth" is expressed as a single value rather than the min and max as in DwC. Work with a representative of the original data to determine what is the preferred way to represent single value and min/max, as necessary. This single value named "depth" is required for ERDDAP and Climate and Forecast compatibility.|Depth|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|distanceEstimationMethod|MBG VLTS Extension|Brief name of the type of binoculars used (e.g. BE = Big Eye) corresponding to the number of reticles recorded in the term reticles, or Naked Eye if sighting distance was estimated without binoculars. If codes for type of binoculars are used, they must be used consistently within a dataset and they must be explained in metadata. Metadata should also include additional information about the specific binoculars used, such as power (magnification X objective diameter in mm)|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|dynamicProperties|Ratified Darwin Core|A list of observed measurements and facts about a biological occurrence record that are not captured by other terms. Recorded in text format according to the following example: "weightInKilograms=8.4". Multiple measurements can be recorded, separated by semi-colons. Facts about the sampling activity, in contrast to the biological entity, will be recorded in the terms for sampling protocol, effort, and conditions, using the same convention. Development of data using "dynamicProperties" may be preparatory for future use of the Darwin Core MeasurementOrFact extension.|OccurrenceDetail|[http://rs.tdwg.org/dwc/terms/#dynamicProperties](http://rs.tdwg.org/dwc/terms/#dynamicProperties)
|equipment|MBG Common Terms Extension|Identifies the equipment or type of equipment used to obtain or gather the sample or otherwise make the observation.|SampleEvent|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|eventDate|Ratified Darwin Core|The date and time of observation expressed in local time using the standard ISO 8601:2004(E). Where date and time are imprecise, for example, time not recorded or day not recorded, ISO 8601 practice is to omit the components of the date and time string for those unspecified details. Where date and time imprecision are more complex, for example, "observed between 10am and noon" or "observed during the first half of July", supplement the use of ISO 8601 in this term with the use of verbatimEventDate, time, timeUncertainty, and eventDateRemarks.|DateTime|[http://rs.tdwg.org/dwc/terms/#eventDate](http://rs.tdwg.org/dwc/terms/#eventDate)
|eventDateRemarks|MBG Common Terms Extension|eventDateRemarks explains information about date and time that may not be evident in verbatim, ISO 8601, or nominal forms of the date and time. For example, date and time may include uncertainty, such as time of day left null because time was not recorded. However, data originators may be able to say that although time was not recorded, the observation is known to have been made between 8am and 5pm local time. eventDateRemarks can provide a concise explanation of this condition. eventDateRemarks can also provide explanation for how timeUncertainty was determined.|DateTime|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|eventDateTimeZone|MBG Common Terms Extension|The time zone of the observation event, expressed as +/- hh:mm offset from UTC. While time zone information can also be included in the full ISO 8601 expression in eventDate, time zone is stored here for reliable use in time and timeUncertainty calculations. (The term) time must be expressed in UTC.|DateTime|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|family|Ratified Darwin Core|The full scientific name of the family in which the taxon is classified.|HigherTaxonomy|[http://rs.tdwg.org/dwc/terms/#family](http://rs.tdwg.org/dwc/terms/#family)
|footprintWKT|Ratified Darwin Core|A Well-Known Text (WKT) representation of geometry associated with the observation. For example, this can be a line segment or polyline representing a cruise path or transect. The location for an occurrence record may have both a point-radius representation (see latitude, longitude) and a footprint representation. This would be a case known to occur in marine data, where the record contains both a point along a transect, as well as a representation of the transect itself. The footprintWKT can also represent other geometry such as a polygon.|Georeference|[http://rs.tdwg.org/dwc/terms/#footprintWKT](http://rs.tdwg.org/dwc/terms/#footprintWKT)
|genus|Ratified Darwin Core|The full scientific name of the genus in which the taxon is classified.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#genus](http://rs.tdwg.org/dwc/terms/#genus)
|geodeticDatum|Ratified Darwin Core|The ellipsoid, geodetic datum, or spatial reference system used in (the terms) latitude and longitude. OBIS-USA practice is to provide all coordinates using EPSG:4326, also known as WGS 84. This element will identify the actual datum used, confirming WGS 84 or identifying what other datum applies.|Georeference|[http://rs.tdwg.org/dwc/terms/#geodeticDatum](http://rs.tdwg.org/dwc/terms/#geodeticDatum)
|georeferencedBy|Ratified Darwin Core|The name or other identifier of individual(s) or institution(s) that determined the georeference. Can be a list delimited by semicolon.|Georeference|[http://rs.tdwg.org/dwc/terms/#georeferencedBy](http://rs.tdwg.org/dwc/terms/#georeferencedBy)
|georeferenceProtocol|Ratified Darwin Core|A description or reference to the methods used to determine the spatial footprint, coordinates, and uncertainties. Georeference methods, including determination of coordinates and uncertainty, should be explained in metadata.|Georeference|[http://rs.tdwg.org/dwc/terms/#georeferenceProtocol](http://rs.tdwg.org/dwc/terms/#georeferenceProtocol)
|habitat|Ratified Darwin Core|A description or identifier of general information about the habitat in which the observation was made. Vocabulary will be consistent within a dataset and will be explained in metadata. Methods of determination (where applicable) will be explained in metadata.|SampleEvent|[http://rs.tdwg.org/dwc/terms/#habitat](http://rs.tdwg.org/dwc/terms/#habitat)
|higherInstitutionCode|MBG Common Terms Extension|Institution codes, in the form of abbreviated institution names, separated by semicolons, that define the hierarchy of institutions within which the data originator operates. Includes the originating institution as the lowest level (rightmost) code. Abbreviations for institutions in all levels of the hierarchy will be explained in metadata.|AdminAndId|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|identificationQualifier|Ratified Darwin Core|A brief phrase or a standard term ("cf.", "aff.") to express the determiner's uncertainty about the identification.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#identificationQualifier](http://rs.tdwg.org/dwc/terms/#identificationQualifier)
|identificationRemarks|Ratified Darwin Core|Comments or notes about the identification, including any applicable reference to process, authorities, keys, uncertainties, or special conventions used in making the identification and assigning the name and/or formatting the name.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#identificationRemarks](http://rs.tdwg.org/dwc/terms/#identificationRemarks)
|identifiedBy|Ratified Darwin Core|The name or other identifier of individual(s) or institution(s) that assigned the taxonomic name. Can be a list delimited by semicolons.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#identifiedBy](http://rs.tdwg.org/dwc/terms/#identifiedBy)
|individualCount|Ratified Darwin Core|The number of individuals represented in the observation record. Valid values include positive integers, zero, and null. Positive integers represent presence. If the observation record and metadata also contain other required information such as details about the sampling activity, individualCount can contribute to the abundance calculations. Null value for individualCount represents a record of presence, with quantity unspecified, and null values do not support abundance calculations. Zero value represents absence. Zero values for absence are only valid if methodology for establishing absence is recorded in metadata.|OccurrenceDetail|[http://rs.tdwg.org/dwc/terms/#individualCount](http://rs.tdwg.org/dwc/terms/#individualCount)
|individualID|Ratified Darwin Core|An identifier for a recognizable individual or group of individuals potentially being observed more than once. Observer procedures for determining consistent identity of the individual or group must be documented in metadata.|Tracking|[http://rs.tdwg.org/dwc/terms/#organismID](http://rs.tdwg.org/dwc/terms/#organismID)
|individualIdentifyingFeature|MBG Common Terms Extension|The feature or technology that identifies an individual or group reliably from one observation to another, such as distinct dorsal fin or tail fluke pattern, or technology such as a passive or active tag that is detected by sensing equipment that locates and identifies the individual.|Tracking|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|infraspecificEpithet|Ratified Darwin Core|The full scientific name of the subspecies, variant or other finer level identification.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#infraspecificEpithet](http://rs.tdwg.org/dwc/terms/#infraspecificEpithet)
|institutionCode|Ratified Darwin Core|An abbreviation for the institution that is the originator of this data resource; the institution involved in research, data collection and/or data management that most directly produced this dataset. This institution also appears as the lowest level (rightmost) code in the higherInstitutionCode term.|AdminAndId|[http://rs.tdwg.org/dwc/terms/#institutionCode](http://rs.tdwg.org/dwc/terms/#institutionCode)
|island|Ratified Darwin Core|The name of an island associated with the location where the observation was made.|NamedGeography|[http://rs.tdwg.org/dwc/terms/#island](http://rs.tdwg.org/dwc/terms/#island)
|islandGroup|Ratified Darwin Core|The name of an island group associated with the location where the observation was made.|NamedGeography|[http://rs.tdwg.org/dwc/terms/#islandGroup](http://rs.tdwg.org/dwc/terms/#islandGroup)
|kingdom|Ratified Darwin Core|The full scientific name of the kingdom in which the taxon is classified.|HigherTaxonomy|[http://rs.tdwg.org/dwc/terms/#kingdom](http://rs.tdwg.org/dwc/terms/#kingdom)
|latitude|MBG Common Terms Extension|The position of the observation north or south of the equator in decimal degrees. Latitudes north of the equator are positive and range to +90 degrees. Positions south of the equator are negative, and range to -90 degrees. This term is implemented in the OBIS-USA database as character data to preserve the exact information provided by the data originator, particularly the number of decimal places, that must be retained to remain true to the original information.|Georeference|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|lengthType|MBG Fish Abundance Extension|The type or method of length measurement used in this observation record, such as TL for total length, FL for fork length, SL for standard length.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|lifeStage|Ratified Darwin Core|An expression or description of age or lifestage of biological individual(s) in the observation record. Vocabulary will be consistent within a dataset and will be explained in metadata. Methods of determination (where applicable) will be explained in metadata.|OccurrenceDetail|[http://rs.tdwg.org/dwc/terms/#lifeStage](http://rs.tdwg.org/dwc/terms/#lifeStage)
|locality|Ratified Darwin Core|The locality is the most specific named place to identify the location of the observation. Many marine data rely strictly on geographic coordinates, so the locality term may be null. If a locality is used, it may be a specific location or feature name, such as "Pier 39" or "Atafu Atoll", or it may include a descriptive phrase, such as "a tidal pool 1500 meters north of Pier 39". Note that in marine observations, the latitude and longitude may be more precise than any named place would suggest, because the coordinates often come from navigation of GPS systems. Geographic names can be secondary locality identifiers and they can be less precise than coordinates.|NamedGeography|[http://rs.tdwg.org/dwc/terms/#locality](http://rs.tdwg.org/dwc/terms/#locality)
|longitude|MBG Common Terms Extension|The position of the observation east or west of the prime meridian in decimal degrees. Positions west of the prime meridian are negative, and range to -180. Positions east of the prime meridian are positive, and range to +180. This term is implemented in the OBIS-USA database as character data to preserve the exact information provided by the data originator, because exact features such as the number of decimal places must be retained to remain true to the original information.|Georeference|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|materialSampleID|Ratified Darwin Core|A unique identifier for a unit of material, or other medium of observation, gathered at a discrete point in time, that serves as a sample for a survey of biological occurrence (presence, quantification, absence, or derived value). The definition of a sample and assignment of IDs is controlled by the data originator. If applicable, details about how samples are defined and IDs assigned will be provided in metadata.|SampleEvent|[http://rs.tdwg.org/dwc/terms/#materialSampleID](http://rs.tdwg.org/dwc/terms/#materialSampleID)
|maximumDepthInMeters|Ratified Darwin Core|minimumDepthInMeters and maximumDepthInMeters express the depth range below the surface of the water at which the observation was made. If the data originator provides a single depth measurement, the minimumDepthInMeters and maximumDepthInMeters show that measurement and will be equal. If no depth information is provided, both the min and max terms will be NULL.|Depth|[http://rs.tdwg.org/dwc/terms/#maximumDepthInMeters](http://rs.tdwg.org/dwc/terms/#maximumDepthInMeters)
|maximumElevationInMeters|Ratified Darwin Core|minimumElevationInMeters and maximumElevationInMeters express the elevation range of the surface of the water, in meters above sea level, in which the observation was made. If the data originator provides a single elevation measurement, the minimumElevationInMeters and maximumElevationInMeters show that measurement and will be equal. If no elevation information is provided, both the min and max terms will be NULL.|Elevation|[http://rs.tdwg.org/dwc/terms/#maximumElevationInMeters](http://rs.tdwg.org/dwc/terms/#maximumElevationInMeters)
|minimumDepthInMeters|Ratified Darwin Core|minimumDepthInMeters and maximumDepthInMeters express the depth range below the surface of the water at which the observation was made. If the data originator provides a single depth measurement, the minimumDepthInMeters and maximumDepthInMeters show that measurement and will be equal. If no depth information is provided, both the min and max terms will be NULL.|Depth|[http://rs.tdwg.org/dwc/terms/#minimumDepthInMeters](http://rs.tdwg.org/dwc/terms/#minimumDepthInMeters)
|minimumElevationInMeters|Ratified Darwin Core|minimumElevationInMeters and maximumElevationInMeters express the elevation range of the surface of the water, in meters above sea level, in which the observation was made. If the data originator provides a single elevation measurement, the minimumElevationInMeters and maximumElevationInMeters show that measurement and will be equal. If no elevation information is provided, both the min and max terms will be NULL.|Elevation|[http://rs.tdwg.org/dwc/terms/#minimumElevationInMeters](http://rs.tdwg.org/dwc/terms/#minimumElevationInMeters)
|modified|Ratified Darwin Core|The most recent date the data originator updated or verified the record, expressed in the standard ISO 8601:2004(E). Can be the record creation date or date of subsequent update or verification. If the data originator does not record or provide this information, OBIS-USA will populate this date with the date the record became available to OBIS-USA.|AdminAndId|[http://rs.tdwg.org/dwc/terms/#dcterms:modified](http://rs.tdwg.org/dwc/terms/#dcterms:modified)
|municipality|Ratified Darwin Core|The name of the municipality in which the observation location occurs. Such geographic named locations may not be available or applicable for marine data, and accordingly the use of this term is optional. In some cases such jurisdiction identification may be crucial for data attribution, management and/or use, so this term is retained in the terminology for cases where it may be essential.|NamedGeography|[http://rs.tdwg.org/dwc/terms/#municipality](http://rs.tdwg.org/dwc/terms/#municipality)
|observationHeight|MBG VLTS Extension|For aerial surveys: Altitude of aircraft in feet above sea level. Altitude is acquired using an altimeter that measures barometric pressure. Accuracy of this measurement relies on daily calibration of mean sea level, and may vary during the length of a flight due to changes in barometric pressure. Consequently, negative altitudes often appear around take-offs and landings; these values should be disregarded. For boat-based surveys: Specifies the average height of the floor of the observationLocation above the water level in meters. This information is linked to the information in observationLocation. observationHeight and reticles is used to calculate the radial distance from the vessel to the animals. For more accurate distance calculations, you can include observer’s name (see MBG term recordedBy) and each observer’s height (included in metadata for recordedBy).|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|observationLocation|MBG VLTS Extension|For aerial surveys: Description of where on the airplane the observer was located when the animal was first detected For example observer location could be “Left side” or “Right side and front” of the airplane. For boat-based surveys: Description of where on the vessel the observer was located when the animal was first detected (e.g. tower, bridge). Any verbatim codes used in this term must be explained in the metadata.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|observedIndividualLengthInCm|MBG Fish Abundance Extension|If a single individual is observed and measured, record length in centimeters here.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|observedMaxLengthInCm|MBG Fish Abundance Extension|If measuring more than one individual for aggregate length values, record maximum length in centimeters here.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|observedMeanLengthInCm|MBG Fish Abundance Extension|If measuring more than one individual for aggregate length values, record mean length in centimeters here.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|observedMinLengthInCm|MBG Fish Abundance Extension|If measuring more than one individual for aggregate length values, record minimum length in centimeters here.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|observersCounts|MBG VLTS Extension|Integer labels and values for additional estimates of group size or counts. For visual line transect surveys this term may consist of separated values estimating group size (best estimate, minimum estimate, maximum estimate). This term is optional if survey protocols do not include additional group size estimates. The contents of such a list of counts is flexible, if other types of labels and counts are required and can include counts of number of calves. Format the contents using the Darwin core [dynamic properties](http://rs.tdwg.org/dwc/terms/#dynamicProperties) approach to key-value pairs, e.g. “bestEstimate=10; minEstimate=8; maxEstimate=15; calves = 2”|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|occurrenceRemarks|Ratified Darwin Core|Information, that is not addressed elsewhere in MBG, about the observation event and biological or other context details about what was observed. Can be general remarks directly from a corresponding column in the original data. Can also include miscellaneous but applicable information carried over from conversion to Darwin Core / MBG and placed here for future reference.|OccurrenceDetail|[http://rs.tdwg.org/dwc/terms/#occurrenceRemarks](http://rs.tdwg.org/dwc/terms/#occurrenceRemarks)
|onEffort|MBG VLTS Extension|One character string to flag whether a record was on effort or off effort. The start and end of effort observations can be identified where there is a change from off effort to on effort and vice-versa. Examples of off effort sighting records may include going off effort to approach animals to obtain better count information, or to photograph animals. Some position-only records may also occur off effort. Fixed vocabulary terms: Y = on effort, N = off effort|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|order|Ratified Darwin Core|The full scientific name of the order in which the taxon is classified.|HigherTaxonomy|[http://rs.tdwg.org/dwc/terms/#order](http://rs.tdwg.org/dwc/terms/#order)
|originatorResourceUrlIdentifier|MBG Common Terms Extension|This term contains a URL provided by the data originator that links to a resource specific to this individual record, for example, an image file or web page devoted to this observation.|OriginatorResource|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|originatorResourceUrlTitle|MBG Common Terms Extension|This term is only used as a companion to the originatorResourceIdentifier term. The "originatorResourceUrlTitle" term contains the title or label text to be displayed to a web user in relation to the corresponding URL.|OriginatorResource|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|ownerInstitutionCode|Ratified Darwin Core|An abbreviation that identifies the institution, within the higherInstitutionCode hierarchy, that is considered the owner or controller of the data.|AdminAndId|[http://rs.tdwg.org/dwc/terms/#ownerInstitutionCode](http://rs.tdwg.org/dwc/terms/#ownerInstitutionCode)
|phylum|Ratified Darwin Core|The full scientific name of the phylum in which the taxon is classified.|HigherTaxonomy|[http://rs.tdwg.org/dwc/terms/#phylum](http://rs.tdwg.org/dwc/terms/#phylum)
|platformSpeed|MBG VLTS Extension|For aerial surveys: Speed of the aircraft at the time of the sighting, recorded in knots. For boat-based surveys: The actual speed of the vessel in knots at the time of the animal sighting. Usually information available from the ship navigation system.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|platformVLTS|MBG VLTS Extension|One-character string to flag survey platform type for visual line transect surveys. For aerial surveys: All records flagged “A”. For boat-based surveys: All records flagged “B”|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|positionVLTS|MBG VLTS Extension|One-character string to flag position only, non-sighting records (P) and additional platform position information when available. Position only records are required for recording tracklines and may also include additional information on sighting conditions. All position-only records will be flagged ‘P’ or ‘T’ for turning, although flagging ‘T’ is not required. Data providers should explain how frequently position only records were obtained (e.g. every 30 minutes) in the metadata. For sighting records this term describes the survey platform position during a sighting. Unless additional information is provided, all sighting records will be flagged as an observation location (O), or C for circling which may be on or off effort. This term records specific survey platform positions using the following fixed vocabulary: T = turning, C = circling, P = position only (non-turning), O = observation.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|preparations|Ratified Darwin Core|A list (concatenated and separated by semicolons) of preparations and preservation methods for a specimen.|OccurrenceDetail|[http://rs.tdwg.org/dwc/terms/#preparations](http://rs.tdwg.org/dwc/terms/#preparations)
|quantificationDeterminedBy|MBG Common Terms Extension|The name or ID of person(s) or institution(s) that determined the quantification.|Quantification|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|quantificationDeterminedDate|MBG Common Terms Extension|The date the quantification was determined, expressed in ISO 8601 date format. Can be different from the observation date.|Quantification|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|quantificationMethod|MBG Common Terms Extension|A reference to the method used to determine the quantification. This will be different from the method used to make the observation of biological occurrence; it will be the companion calculation method that followed the observation method. Quantification information is expected to be useful only if method is sufficiently documented, so this term is vitally important for use of quantification terms for derived values. This term can contain a code or other abbreviated reference to a method. In all cases quantificationMethod should be explained in metadata and supporting publications or related resources identified.|Quantification|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|quantificationName|MBG Common Terms Extension|A name for a derived value or processed data about the occurrence, for example, "Biomass". The word used in this terminology for such information is "quantification", rather than "abundance", because the word "abundance" may already be associated with specific, rather than general, practices of quantification in biology. In this example, biomass would not be obtained at survey time, rather biomass would be calculated from input data that was obtained at survey time, combined with a biomass calculation methodology. This term is used along with companion terms for quantification value, units, uncertainty, method, and determination details. It is suggested that names for derived values be more specific than "Biomass", because many institutions will develop biomass information using diverse methods. Suggested practice is to include some more specific reference(s) in the quantification name, such as institution, survey, date or other specifics. For example, "Biomass-PIFSC-2011", and explain the name and method of calculation in metadata.|Quantification|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|quantificationStatus|MBG Common Terms Extension|This is a one-character string with enumerated values indicating what type of quantification this record represents. "P" for presence (and no quantification), "Q" for quantified or "A" for absence.|Quantification|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|quantificationUncertainty|MBG Common Terms Extension|An estimate of the uncertainty, positive and negative (+/-) offset of the stated value, that expresses the uncertainty of the value as calculated and reported. This can be reported in the units of the quantification, or as a percentage. Note that the expression in this term can combine both accuracy and precision considerations to a more general estimate uncertainty; hence the slightly different name for this term compared to the Darwin Core (dwc) reference term.|Quantification|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|quantificationUnit|MBG Common Terms Extension|The units in which the value expresses the quantification, for example, "kg/m^2 surface" or "kilograms per square meter of ocean surface".|Quantification|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|quantificationValue|MBG Common Terms Extension|The value of the derived information product, such as the numerical value for biomass. This term does not include units. Units are contained in another term.|Quantification|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|quantificationVocabulary|MBG Common Terms Extension|The names for derived values, referred to as quantification, can be drawn from a controlled vocabulary or vocabularies of quantification names. Or they can be reported using the verbatim name given by the data originator. Either the name of the controlled vocabulary or the word “verbatim” should be used in this term to record the level of control over names. Verbatim means the names are not using a controlled vocabulary other than the names assigned just as they are by the data originator. Either way, within a dataset, identifiers for quantification names must be used consistently and explained in metadata.|Quantification|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|receiverID|MBG Common Terms Extension|The identifier of any form of technology used in tracking an individual, such as a satellite or radio transceiver, that helps document how the observation was made and known to be a consistent individual.|Tracking|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|recordedBy|Ratified Darwin Core|The name or other identifier of individual(s) or institution(s) responsible for making the observation and recording it in electronic form. Can be a list delimited by semicolon.|RecordOrigination|[http://rs.tdwg.org/dwc/terms/#recordedBy](http://rs.tdwg.org/dwc/terms/#recordedBy)
|recordType|MBG Common Terms Extension|Use "recordType" to refine the information in "basisOfRecord". For one example, within the "basisOfRecord" that is 'HumanObservation' use "recordType" to distinguish a an animal captured, identified, and recorded in human possession (such as outcome of a trawl) from an animal observed and identified at a distance and recorded by a human (such as VLTS observations).|RecordOrigination|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|references|Ratified Darwin Core|A related resource that is referenced, cited, or otherwise pointed to by the described resource. Use this term to point to related resources, such as other forms of the data, other data from the same cruise (such as physical oceanography data), and models and synthesis made from the data.|AdminAndId|[http://rs.tdwg.org/dwc/terms/#dcterms:references](http://rs.tdwg.org/dwc/terms/#dcterms:references)
|reliability|MBG VLTS Extension|Estimate of reliability of species identification ranging from 0 (high uncertainty of species identification) to 100% (high certainty of correct species identification) reliability. This term can use the verbatim terminology from the data provider and will be described in the metadata.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|reticles|MBG VLTS Extension|The number of reticles below the horizon using a specified type of binoculars. Reticle 0 indicates the sighting is at the horizon. The type of binoculars must be specified in the term distanceEstimationMethod. If distanceEstimationMethod did not include binoculars with reticles then no values will be required for this field.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|sampleAreaInSquareMeters|MBG Fish Abundance Extension|The area in square meters, if projected vertically to a plane representing the ocean surface, of the sample space in which the observation was made.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|sampleHeightInMeters|MBG Fish Abundance Extension|The height in meters of the sample space in which the observation was made.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|sampleLengthInMeters|MBG Fish Abundance Extension|The length in meters of the sample space in which the observation was made.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|sampleRadiusInMeters|MBG Fish Abundance Extension|The radius in meters of a cylindrical sample space.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|sampleShape|MBG Fish Abundance Extension|The shape of the sample space in which the observation was made, such as R for rectangular, C for cylindrical.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|sampleVolumeInCubicMeters|MBG Fish Abundance Extension|The volume in cubic meters of the sample space in which the observation was made.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|sampleWidthInMeters|MBG Fish Abundance Extension|The width in meters of the sample space in which the observation was made.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|samplingConditions|MBG Common Terms Extension|Information about the state of the sampling location, determined by external factors such as weather, water conditions, lighting and visibility, etc., at the time of the sampling event. Like samplingEffort, this term describes phenomena other than the method intended by the data collector in the samplingProtocol. The difference between samplingEffort and samplingConditions is that samplingConditions describes the state of the environment, and samplingEffort describes the actions of the sampler. More than one type of information about conditions can be concatenated into this term, delimited by semicolon. Contents in this term (either verbatim or by vocabulary) will be used consistently in a dataset and will be explained in metadata. More extensive discussion of sampling conditions may be provided in metadata as needed.|SampleEvent|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|samplingEffort|Ratified Darwin Core|Information about the extent, duration or other variable aspects of the sampling activity, as conducted by the data originator, that occurred at the time of the sampling event. In contrast to the samplingProtocol, which describes the intended method of sampling prior to the event, samplingEffort describes actual phenomena as they occur at the time of sampling. More than one type of effort information can be concatenated into this term, delimited by semicolon. Contents in this term (either verbatim or by vocabulary) will be used consistently in a dataset and will be explained in metadata. More extensive discussion of sampling effort may be provided in metadata as needed.|SampleEvent|[http://rs.tdwg.org/dwc/terms/#samplingEffort](http://rs.tdwg.org/dwc/terms/#samplingEffort)
|samplingProtocol|Ratified Darwin Core|Information about the intended sampling method as defined by the data originator. Contents in this term (either verbatim or by vocabulary) will be used consistently in a dataset and will be explained in metadata. If there is more than one aspect of sampling protocol worth capturing, information can be concatenated into this term, delimited by semicolon. More extensive discussion of sampling protocol may be provided in metadata as needed.|SampleEvent|[http://rs.tdwg.org/dwc/terms/#samplingProtocol](http://rs.tdwg.org/dwc/terms/#samplingProtocol)
|scientificName|Ratified Darwin Core|The taxonomic identification of the observation as either 1) Genus and species (and subspecies if provided) in Latin binomial nomenclature form, or 2) the lowest-level taxonomic name to which the observation is identified, expressed in Latin form. scientificName is a required term. Authorities, references and procedures for making identifications should be documented in metadata.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#scientificName](http://rs.tdwg.org/dwc/terms/#scientificName)
|scientificNameAuthorship|Ratified Darwin Core|The authorship information for the scientificName.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#scientificNameAuthorship](http://rs.tdwg.org/dwc/terms/#scientificNameAuthorship)
|scientificNameID|Ratified Darwin Core|An identifier for the nomenclatural (not taxonomic) details of the scientific name. For OBIS-USA, this may be an ITIS taxon serial number or a WoRMS aphia ID, or other similar reference.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#scientificNameID](http://rs.tdwg.org/dwc/terms/#scientificNameID)
|sex|Ratified Darwin Core|The sex of biological individuals represented in the observation record. Vocabulary will be consistent within a dataset and will be explained in metadata. Methods of determination (where applicable) will be explained in metadata.|OccurrenceDetail|[http://rs.tdwg.org/dwc/terms/#sex](http://rs.tdwg.org/dwc/terms/#sex)
|sightingCue|MBG VLTS Extension|Description of what was seen first of the group, that is, the cue associated with the first sighting of the animal (or group of animals). A behavioral code may be used (e.g. BL = blow). Additional explanation of the role of cues in sighting may be helpful to explain in metadata. If behavioral codes are used in sightingCue, they must be used consistently within a dataset and they must be explained in metadata.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|sightingDistanceInMeters|MBG VLTS Extension|For boat-based surveys: Radial distance in meters between the animal (or center of group of animals) and the vessel when the first sighting was made. This value is can be reported if 1) prior calibrations of radial distances have been made using the known observation height and the reticles on the specific types of binoculars used during the survey, and 2) sighting was detected by eye if ‘Naked Eye’ is specified in distanceEstimationMethod. *Optional use for aerial surveys: Typically these radial sighting distances are not recorded, but they can be calculated from clinometer readings (verticalAngle) and altitude (observationHeight). If distances between the plane and the animals are provided (e.g. using lasers, or calculating distance to the trackline using GPS locations above the initial animal sightings) this information can be included in this term.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|source|MBG Common Terms Extension|The Source term carries over from vOBIS, where it had been considered for discontinuation. However, it has proven useful for identifying literature as a source of biogeographic information, so it is retained in MBG for use at the record level when the occurrence record is derived from literature. Enter the literature citation in this term. This will be required when the basisOfRecord is "DerivedFromLiterature". Transition to the Darwin Core term for this purpose in MBG. See [http://rs.tdwg.org/dwc/terms/associatedReferences](http://rs.tdwg.org/dwc/terms/associatedReferences)|RecordOrigination|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|specificEpithet|Ratified Darwin Core|The full scientific name of the species in which the taxon is classified|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#specificEpithet](http://rs.tdwg.org/dwc/terms/#specificEpithet)
|stateProvince|Ratified Darwin Core|The name of the state or province in which the observation location occurs. Such geographic named locations may not be available or applicable for marine data, and accordingly the use of this term is optional. In some cases such jurisdiction identification may be crucial for data attribution, management and/or use, so this term is retained in the terminology for cases where it may be essential.|NamedGeography|[http://rs.tdwg.org/dwc/terms/#stateProvince](http://rs.tdwg.org/dwc/terms/#stateProvince)
|subgenus|Ratified Darwin Core|The full scientific name of the subgenus in which the taxon is classified.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#subgenus](http://rs.tdwg.org/dwc/terms/#subgenus)
|subsampleID|MBG Common Terms Extension|If a sample is further divided by the data originator for purposes of organization, handling, or analysis, and if the data originator wants to maintain the identity of the subsample, capture the ID of the subsample here. Explain in metadata if applicable.|SampleEvent|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|surveyEventID|MBG Common Terms Extension|surveyEventID identifies a tow, trawl, cast, cruise, transect or other event or unit that survey operators, data gatherers and data managers want to treat as a single consistent event or unit. A survey event can contain one or many sample events sampleIDs.|SampleEvent|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|taxonRank|Ratified Darwin Core|The taxonRank term is a companion to the scientificName term. taxonRank identifies the taxonomic level of the lowest-level name in the scientificName term, if the scientificName refers to a level above genus.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#taxonRank](http://rs.tdwg.org/dwc/terms/#taxonRank)
|time|MBG Common Terms Extension|This term identifies a specific instant chosen to represent the date and time of the observation, in Coordinated Universal Time (UTC). Both date and time are specified in this term in order to facilitate some searches and services that require resolution of events to this level of precision in time. Some observation events occur with uncertainty at the level of minutes, hours, or even days or more. A nominal event date and time is determined, even for observations with date and time uncertainty, for web services to best represent the instant of the event. The companion term, timeUncertainty, defines an interval of uncertainty that quantifies precision to correspond to the precision the original data recorded. Methods for determining nominal time and uncertainty will be documented in metadata, and they can be explained (if concise) in the eventDateRemarks term.|DateTime|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|timeUncertainty|MBG Common Terms Extension|This is the uncertainty in seconds before and after the (the term) time, as a result of both precision and accuracy factors in determining observation time. This use of uncertainty makes (the term) time the mid-point in the range of uncertainty equal to twice the value of this term.|DateTime|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|totalInSample|MBG Common Terms Extension|In cases where subsampling has been done and the data record represents a subsample, the totalInSample term contains information about the total quantity in the original sample, usually expressed as total count or weight, for example "Count=85" or "WeightInKilograms=4.4". Specific details about how subsampling was done in relation to the total sample must be explained in samplingProtocol, and/or in metadata.|SampleEvent|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|trackHomeRecord|MBG Common Terms Extension|trackHomeRecord identifies the single record and location to consider home for the individual or group identified by the individualID. trackHomeRecord assists determination that multiple records may be included in OBIS-USA, but only one should be counted to accurately assess the total number of individuals in OBIS-USA. trackHomeRecord will be determined according to practices approved by the data originator. For example, trackHomeRecord can be the first record, or a mid-point record based on time or geography, or determined by some other approved method. Values can be true, false, or null.|Tracking|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|trackSequenceNumber|MBG Common Terms Extension|The combination of individuaID and the eventDate should capture information about multiple observations as well as the sequence of observations, representing the track covered by the individual. The sequence number term will be generated, in coordination with the data originator, as a series of ordinal integers. The purpose is either to cross-validate the sequence, or to accommodate missing information in a track (such as imprecise time stamps). The practice of adding this sequence number may prove to be unnecessary if track observation data is complete and verifiable.|Tracking|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|tsn|MBG Fish Abundance Extension|A unique taxon identifier obtained by validation of the taxon name with the Integrated Taxonomic Information System (ITIS), www.itis.gov.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|typeStatus|Ratified Darwin Core|A list (concatenated and separated by semicolons) of nomenclatural types (type status, typified scientific name, publication) applied to the subject.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#typeStatus](http://rs.tdwg.org/dwc/terms/#typeStatus)
|typeVLTS|MBG VLTS Extension|One-character string to flag only the initial sighting records which can be used in density and abundance estimation. Opportunistic and subsequent sighting records can be included in the dataset, but these are easily identified from this term for exclusion from abundance and density modeling. The fixed vocabulary terms are: F = first observation sighting on transect, O = opportunistic sighting, S = subsequent sighting either on or off transect, Null = for position-only records or non-VLTS datasets.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|verbatimCoordinates|Ratified Darwin Core|Record original coordinate information here (both latitude and longitude) for audit trail purposes where necessary.|Georeference|[http://rs.tdwg.org/dwc/terms/#verbatimCoordinates](http://rs.tdwg.org/dwc/terms/#verbatimCoordinates)
|verbatimCoordinateSystem|Ratified Darwin Core|The spatial coordinate system for the verbatimCoordinates.|Georeference|[http://rs.tdwg.org/dwc/terms/#verbatimCoordinateSystem](http://rs.tdwg.org/dwc/terms/#verbatimCoordinateSystem)
|verbatimEventDate|Ratified Darwin Core|The expression of the date and time of the observation in language identical to the originator's description of the date and time of observation. If the originator used a non-standard format or descriptive language for date and time, verbatimEventDate contains this information.|DateTime|[http://rs.tdwg.org/dwc/terms/#verbatimEventDate](http://rs.tdwg.org/dwc/terms/#verbatimEventDate)
|verbatimModified|MBG Common Terms Extension|The date and time value of the modified term, recorded in the exact format that the data originator provided it, for purposes of audit trail, since OBIS-USA will convert this to ISO 8601:2004(E) for operational purposes.|AdminAndId|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|verbatimSRS|Ratified Darwin Core|The ellipsoid, geodetic datum, or spatial reference system (SRS) upon which coordinates given in verbatimCoordinates are based.|Georeference|[http://rs.tdwg.org/dwc/terms/#verbatimSRS](http://rs.tdwg.org/dwc/terms/#verbatimSRS)
|vernacularName|Ratified Darwin Core|A common or vernacular name for the taxon observed. vernacularName is not required. Use of this term is at the discretion of the data originator. If this term is used, then authorities, references and procedures for making identifications and translating vernacular name to scientific name should be documented in metadata. The recommended practice is that vernacular names be used consistently within a dataset.|TaxonomicIdentification|[http://rs.tdwg.org/dwc/terms/#vernacularName](http://rs.tdwg.org/dwc/terms/#vernacularName)
|verticalAngle|MBG VLTS Extension|Estimated angle of declination from the plane to the sighting from 0 to 90 degrees, typically measured with a clinometer. Angles range from 0 to 90 degrees where 0 means the sighting is at the horizon and 90 degrees is when the sighting is directly under the aircraft.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|verticalDatum|MBG Common Terms Extension|A reference system that defines zero elevation, in relation to which observation measurements of elevation and depth are expressed; for example, categories of vertical datums can include tidal datums and geodetic datums.|Georeference|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|vesselActivity|MBG VLTS Extension|Description of vessel activity occurring when the animal is first sighted (e.g. periods of surveying during active sound production or periods of transit). This is to make users aware of aspects of the survey, vessel activity or observation details that may bias the detection of animals and so may impact how they select and handle dataset-specific observations in applications.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|visibilityImpairment|MBG VLTS Extension|Description of any impairments to visibility, such as: fog, precipitation, low ceiling, haze, glare. This term will use the verbatim terminology from the data provider that may include information on the degree of impairment as well as the description of impairment type.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|visibilityInMeters|MBG VLTS Extension|For aerial surveys: Estimated maximum distance from the plane in meters at which an animal can be observed on the water surface given the present environmental conditions. Different visibilities can be reported separately for left and right side of the plane if these are recorded. In this case the term will consist of two values separated by semicolons. The first term will describe the estimated visibility in meters for left side of the plane, and the second term will describe visibility in meters for the observer on the right side of the plane. If more than two observers record visibility information in meters these can be incorporated by formatting the contents using the Darwin core dynamic properties approach to key-value pairs (http://rs.tdwg.org/dwc/terms/#dynamicProperties). For boat-based surveys: Estimated maximum distance from the vessel in meters at which an animal can be observed on the water surface given the present environmental conditions, such as glare, rain, fog, sea state, swell height. For underwater surveys: Visibility through the water column in meters.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|visibilityType|MBG Fish Abundance Extension|The direction of estimated visibility, horizontal or vertical.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|waterBody|Ratified Darwin Core|The name of the water body in which the observation was made. For marine data, this is the ocean name. If there is a more specific named region, such as a bay or reef, or sector of the ocean (for example, northwest Pacific), add the regional name after the ocean name, separated by a semicolon. Note that the Locality term will contain the most specific name, such as a pier or other named feature, so that lowest level of detail need not be included in the waterBody term. The waterBody term is for the ocean and any named intermediate geography such as a region.|NamedGeography|[http://rs.tdwg.org/dwc/terms/#waterBody](http://rs.tdwg.org/dwc/terms/#waterBody)
|waterTemperatureInCelsius|MBG Fish Abundance Extension|The temperature of the water at the time of the observation, expressed in Celsius.|FishAbundance|[http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml](http://rs.gbif.org/sandbox/extension/mbg-fish-abundance.xml)
|weightInKg|MBG Common Terms Extension|The recorded weight in kilograms of the individuals in the observation. Capture in metadata details about weight, such as what kind of weight (e.g., dry weight), calculation or estimation procedures, or other details applied in determining weight. This is in contrast to totalInSample, that can report the total in the original sample in cases of subsampling. In cases of subsampling, weightInKg will be the weight of the subject of this occurrence record, be it an individual or more than one individual total weight.|OccurrenceDetail|[http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml](http://rs.gbif.org/sandbox/extension/mbg-common-terms.xml)
|windDirectionRelativeToTrueNorth|MBG VLTS Extension|Wind direction in degrees relative to true North.|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)
|windSpeedInKnots|MBG VLTS Extension|True wind speed in knots (removes effect of vessel course and speed).|VLTS|[http://rs.gbif.org/sandbox/extension/mbg-vlts.xml](http://rs.gbif.org/sandbox/extension/mbg-vlts.xml)




#### &nbsp; &nbsp; _**XML Schema**_{: style="color: crimson"}

```
<?xml version="1.0"?>
<!-- version 0.9 2011/11/30 Philip Goldstein (University of Colorado, Boulder)
-->
<?xml-stylesheet href='ioosxsdstyle.xsl' type='text/xsl'?>
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:dwc="http://rs.tdwg.org/dwc/terms/"
    xmlns:dcterms="http://purl.org/dc/terms/" xmlns:ioosbiology="http://domain.gov/folder/terms/"
    targetNamespace="http://domain.gov/folder/terms/">

    <!--  Administration and identification terms  -->

    <xsd:element name="modified" ref="dcterms:modified" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The most recent date the data originator updated or verified the
                record, expressed in the standard ISO 8601:2004(E). Can be the record creation date
                or date of subsequent update or verifiction. If the data originator does not record
                or provide this information, IOOS will populate this date with the date the record
                became available to IOOS.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="verbatimModified" ref="ioosbiology:verbatimModified" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The date and time value of the "modified" term, recorded in the exact
                format that the data originator provided it, for purposes of audit trail, since IOOS
                will convert this to ISO 8601:2004(E) for operational purposes.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="datasetID" ref="dwc:datasetID" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>An abbreviated name for the dataset that contains this occurrence
                record. This may also be the technical name for the data resource in a database or
                web service. The datasetID occurs on each row to preserve record identity in case
                records served by the resource become distributed to other resources or
                applications.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="datasetName" ref="dwc:datasetName" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>This is a long-form name for the dataset, more explanatory than the
                datasetID. The datasetName will read as a recognizable title that reflects
                information about the dataset. Suggested information to include in the datasetName
                can refer to originator, content, purpose, method, geography, or other
                characteristics of the dataset. This datasetName term in the data record will match
                the dataset name in metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="higherInstitutionCode" ref="ioosbiology:higherInstitutionCode"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>Institution codes, in the form of names, abbreviation or acronyms,
                separated by semicolons, that define the hierarchy of institutions within which the
                data originator operates. Includes the originating institution as the lowest level
                (rightmost) code. All abbreviations or acronyms for institutions in all levels of
                the hierarchy will be explained in dataset metadata. </xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="institutionCode" ref="dwc:institutionCode" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A name, abbreviation or acronym for the institution that is the
                originator of this data resource: the institution most directly involved in
                research, operations, data collection and/or data management that produced this
                dataset. This institution also appears as the lowest level (rightmost) code in the
                higherInstitutionCode term.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="ownerInstitutionCode" ref="ioosbiology:ownerInstitutionCode"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>An abbreviation that identifies the institution, within the
                "higherInstitutionCode" hierarchy, that is considered the owner or controller of the
                data.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="collectionCode" ref="dwc:collectionCode" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>An identifier for a subset(s) of data within the dataset, partitioned
                by methods or parameters meaningful to the data originators. The scheme and purpose
                for defining and partitioning by collectionCode within a dataset will be explained
                in metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="catalogNumber" ref="dwc:catalogNumber" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A record identifier provided by the data originator. The identifier
                is controlled by the data originator and reflects the originator's practices of data
                administration. Special concerns about the identifier, such as whether it is unique,
                if it is persistent, or if it contains embedded information, can be addressed in
                metadata if applicable.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <!--  Date and time terms  -->

    <xsd:element name="observationDateTime" ref="dwc:eventDate" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The date and time of observation expressed in local time using the
                standard ISO 8601:2004(E). Where date and time are imprecise, for example, time not
                recorded or day not recorded, ISO 8601 practice is to omit the components of the
                date and time string for those unspecified details. Where date and time imprecision
                are more complex, for example, "observed between 10am and noon" or "observed during
                the first half of July", supplement the use of ISO 8601 in this term with the use of
                verbatimObservationDateTime, nominalObservationDateTime,
                nominalObservationDateTimeUncertainty, and
                observationDateTimeAnnotation.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="observationTimeZone" ref="ioosbiology:observationTimeZone" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The time zone of the observation event, expressed as +/- hh:mm offset
                from UTC. While time zone information can also be included in the full ISO 8601
                expression in observationDateTime, time zone is stored here for reliable use in
                nominalObservationDateTime and nominalObservationDateTimeUncertainty calculations.
                nominalObservationDateTime must be expressed in UTC.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="observationDateTimeAnnotation"
        ref="ioosbiology:observationDateTimeAnnotation" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>observationDateTimeAnnotation explains information about date and
                time that may not be evident in verbatim, ISO 8601, or nominal forms of the date and
                time. For example, date and time may include uncertainty, such as time of day left
                null because time was not recorded. Howewver, data originators may be able to say
                that although time was not recorded, the observation is known to have been made
                between 8am and 5pm local time. observationDateTimeAnnotation can provide a concise
                explanation of this condition. observationDateTimeAnnotation can also provide
                explanation for how nominalObservationDateTimeUncertainty was
                determined.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="verbatimObservationDateTime" ref="dwc:verbatimEventDate" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The expression of the date and time of the observation in language
                identical to the originator's description of the date and time of observation. If
                the originator used a non-standard format or descriptive language for date and time,
                verbatimObservationDateTime contains this information.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="nominalObservationDateTime" ref="ioosbiology:nominalObservationDateTime"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>In an IOOS service, this variable may appear simply with the name
                "time" or with the full name "nominalObservationDateTime". This term identifies a
                specific instant chosen to represent the date and time of the observation, in
                Coordinated Universal Time (UTC). Both date and time are specified in this term in
                order to facilitate some searches and services that require resolution of events to
                this level of precision in time. Some observation events occur with uncertainty at
                the level of minutes, hours, or even days or more. A nominal event date and time is
                determined, even for observations with date and time uncertainty, for IOOS services
                to best represent the instant of the event. The companion term,
                nominalObservationDateTimeUncertainty, defines an interval of uncertainty that
                quantifies precision to correspond to the precision the original data recorded.
                Methods for determining nominal time and uncertainty will be documented in metadata,
                and they can be concisely explained in the "obsrvationDateTimeAnnotation"
                term.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="nominalObservationDateTimeUncertainty"
        ref="ioosbiology:nominalObservationDateTimeUncertainty" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>In an IOOS service, this variable may appear simply with the name
                "timeUncertainty" or with the full name "nominalObservationDateTimeUncertainty".
                This is the uncertainty in seconds before and after the nominalObservationDateTime,
                as a result of both precision and accuracy factors in determining observation time.
                This use of uncertainty makes the nominalObservationDateTime the mid-point in the
                range of uncertainty equal to twice the value of this term.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <!--  Georeference (coordinate geography) terms  -->

    <xsd:element name="latitude" ref="dwc:decimalLatitude" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The position of the observation north or south of the equator in
                decimal degrees. Latitudes north of the equator are positive and range to +90
                degrees. Positions south of the equator are negative, and range to -90
                degrees.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="longitude" ref="dwc:decimalLongitude" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The position of the observation east or west of the prime meridian in
                decimal degrees. Positions west of the prime meridian are negative, and range to
                -180. Positions east of the prime meridian are positive, and range to
                +180.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="coordinateUncertaintyInMeters" ref="dwc:coordinateUncertaintyInMeters"
        type="xsd:decimal">
        <xsd:annotation>
            <xsd:documentation>An expression in meters of the overall uncertainty of the
                georeference provided by the latitude and longitude data. The uncertainty can
                combine issues of both accuracy and precision, and depends on the method the data
                originator used to determine coordinates. Methods and considerations that go into
                determinations of uncertainty will be described in metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="geodeticDatum" ref="dwc:geodeticDatum" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The ellipsoid, geodetic datum, or spatial reference system used in
                decimalLatitude and decimalLongitude. IOOS preference is to provide all coordinates
                using EPSG:4326, also known as WGS 84. This element will identify the actual datum
                used, confirming WGS 84 or identifying what other datum applies.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="georeferencedBy" ref="dwc:georeferencedBy" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name or other identifier of individual(s) or institution(s) that
                determined the georeference. Can be a list delimited by
                semicolon.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="georeferenceProtocol" ref="dwc:georeferenceProtocol" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A description or reference to the methods used to determine the
                spatial footprint, coordinates, and uncertainties.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="verbatimCoordinates" ref="dwc:verbatimCoordinates" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>Record original coordinate information here (both latitude and
                longitude) for audit trail purposes where necessary.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="verbatimCoordinateSystem" ref="dwc:verbatimCoordinateSystem"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The spatial coordinate system for the verbatimLatitude and
                verbatimLongitude or the verbatimCoordinates.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="verbatimSRS" ref="dwc:verbatimSRS" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The ellipsoid, geodetic datum, or spatial reference system (SRS) upon
                which coordinates given in verbatimCoordinates are based.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <!--  Depth terms  -->

    <xsd:element name="minimumDepthInMeters" ref="dwc:minimumDepthInMeters" type="xsd:decimal">
        <xsd:annotation>
            <xsd:documentation>The minimumDepthInMeters and maximumDepthInMeters express the depth
                range in which the observation was made. If the data originator provides a single
                depth measurement, the minimumDepthInMeters and maximumDepthInMeters show that
                measurement and will be equal. If no depth information is provided, both the min and
                max terms will be NULL.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="maximumDepthInMeters" ref="dwc:maximumDepthInMeters" type="xsd:decimal">
        <xsd:annotation>
            <xsd:documentation>The minimumDepthInMeters and maximumDepthInMeters express the depth
                range in which the observation was made. If the data originator provides a single
                depth measurement, the minimumDepthInMeters and maximumDepthInMeters show that
                measurement and will be equal. If no depth information is provided, both the min and
                max terms will be NULL.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <!--  Record origination terms  -->

    <xsd:element name="basisOfRecord" ref="dwc:basisOfRecord" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>Identifies the source of information or observation that generated
                the biological occurrence record.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="recordedBy" ref="dwc:recordedBy" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name or other identifier of individual(s) or institution(s)
                responsible for making the observation and recording it in electronic form. Can be a
                list delimited by semicolon.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <!--  Taxonomic identification terms  -->

    <xsd:element name="vernacularName" ref="dwc:vernacularName" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A common or vernacular name for the taxon observed. A vernacularName
                is not required. Use of this term is at the discretion of the data originator. If
                this term is used, then authorities, references and procedures for making
                identifications and translating vernacular name to scientific name should be
                documented in metadata. The recommended practice is that vernacular names be used
                consistently within a dataset.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="scientificName" ref="dwc:scientificName" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The taxonomic identification of the observation as either 1) Genus
                and species (and subspecies if provided) in Latin binomial nomenclature form, or 2)
                the lowest-level taxonomic name to which the observation is identified, expressed in
                Latin form. scientificName is a required term. Authorities, references and
                procedures for making identifications should be documented in
                metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="taxonRank" ref="dwc:taxonRank" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The taxonRank term is a companion to the scientificName term.
                taxonRank identifies the taxonomic level of the lowest-level name in the
                scientificName term.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="aphiaID" ref="ioosbiology:aphiaID" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A unique taxon identifier obtained by validation of the taxon name
                with the World Register of Marine Species (WoRMS),
                www.marinespecies.org.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="tsn" ref="ioosbiology:tsn" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A unique taxon identifier obtained by validation of the taxon name
                with the Integrated Taxonomic Information System (ITIS),
                www.itis.gov.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <!--  Occurrence detail terms  -->

    <xsd:element name="individualCount" ref="dwc:individualCount" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The number of individuals represented in the observation record.
                Valid values include positive integers, zero, and null. Positive integers represent
                presence. If the observation record and metadata also contain other required
                information such as details about the sampling activity, individualCount can
                contribute to the abundance calculations. Null value for individualCount represents
                a record of presence, with quantity unspecified, and null values do not support
                abundance calculations. Zero value represents absence. Zero values for absence are
                only valid if methodology for establishing absence is recorded in
                metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="sex" ref="dwc:sex" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The sex of biological individuals represented in the observation
                record. Vocabulary will be consistent within a dataset and will be explained in
                metadata. Methods of determination (where applicable) will be explained in
                metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="lifeStage" ref="dwc:lifeStage" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>An expression or description of age or lifestage of biological
                individual(s) in the observation record. Vocabulary will be consistent within a
                dataset and will be explained in metadata. Methods of determination (where
                applicable) will be explained in metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="observedIndividualLengthInCm" ref="ioosbiology:observedIndividualLengthInCm"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>If a single individual is observed and measured, record length in
                centimeters here.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="observedMeanLengthInCm" ref="ioosbiology:observedMeanLengthInCm"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>If measuring more than one individual for aggregate length values,
                record mean length in centimeters here.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="observedMaxLengthInCm" ref="ioosbiology:observedMaxLengthInCm"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>If measuring more than one individual for aggregate length values,
                record maximum length in centimeters here.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="observedMinLengthInCm" ref="ioosbiology:observedMinLengthInCm"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>If measuring more than one individual for aggregate length values,
                record minimum length in centimeters here.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="lengthType" ref="ioosbiology:lengthType" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The type or method of length measurement used in this observation
                record, such as TL for total length, FL for fork length, SL for standard
                length.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <!-- Sample identification and sampling event terms  -->

    <xsd:element name="sampleID" ref="ioosbiology:sampleID" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A unique identifier for a unit of material that serves as a sample
                for a survey of biological occurrence (presence, absence or derived value). The
                definition of a sample and assignment of IDs is cojntroled by the data originator.
                If applicable, details about how sample ares are defined and IDs assigned will be
                provided in metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="subsampleID" ref="ioosbiology:subsampleID" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>If a sample is further divided by the data originator for purposes of
                organization, handling or analysis, and if the data originator wants to maintain the
                identity of the subsample, capture the ID of the subsample here. Explain in metadata
                if applicable.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="samplingProtocol" ref="dwc:samplingProtocol" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>Information about the sampling method as defined by the data
                originator. Valid values include S for stationary, T for towed, D for diver swim.
                Contents or vacabulary used in this term will be used consistently in a dataset and
                will be explained in metadata. Additional information can be concatenated into the
                term, delimited by semicolon. More extensive discussion of sampling protocol, effort
                and conditions may be provided in metadata as needed.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="samplingEffort" ref="dwc:samplingEffort" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>Information about the extent, duration or other variable aspects of
                the sampling activity, as conducted by the data originator, that occurred at the
                time of the sampling event. More than one type of effort information can be
                concatenated into this term, delimited by semicolon. Other terms are available in
                this terminology for some specific details of sampling effort, such as sample
                dimensions, that are expected to be frequently used in IOOS services. Use the
                samplingEffort term for additional effort information that is not addressed by other
                terms. More extensive discussion of sampling protocol, effort and conditions may be
                provided in metadata as needed.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="samplingConditions" ref="ioosbiology:samplingConditions" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>Information about the state of the sampling location, determined by
                external factors such as weather, at the time of the sampling event. More than one
                type of information about conditions can be concatenated into this term, delimited
                by semicolon. Other terms are available in this terminology for some specific
                details of sampling conditions, such as habitat, bottomType, visibilty and
                temperature, that are expected to be frequently used in IOOS services. Use the
                samplingConditions term for additional information about conditions that is not
                addressed by other terms. More extensive discussion of sampling protocol, effort and
                conditions may be provided in metadata as needed.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="sampleShape" ref="ioosbiology:sampleShape" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The shape of the sample space in which the observation was made, such
                as R for rectangular, C for cylindrical.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="sampleWidthInMeters" ref="ioosbiology:sampleWidthInMeters" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The width in meters of the sample space in which the observation was
                made.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="sampleHeightInMeters" ref="ioosbiology:sampleHeightInMeters"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The length in meters of the sample space in which the observation was
                made.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="sampleRadiusInMeters" ref="ioosbiology:sampleRadiusInMeters"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The radius in meters of a cylindrical sample
                space.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="sampleAreaInSquareMeters" ref="ioosbiology:sampleAreaInSquareMeters"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The area in square meters, if projected vertically to a plane
                representing the ocean surface, of the sample space in which the observation was
                made.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="sampleVolumeInCubicMeters" ref="ioosbiology:sampleVolumeInCubicMeters"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The volume in cubic meters of the sample space in which the
                observation was made.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="visibilityInMeters" ref="ioosbiology:visibilityInMeters" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>Visibility through the water column in meters.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="visibilityType" ref="ioosbiology:visibilityType" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The direction of estimated visibility, horizontal or
                vertical.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="waterTemperatureInCelsius" ref="ioosbiology:waterTemperatureInCelsius"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The temperature of the water at the time of the observation,
                expressed in degrees Celsius.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="habitat" ref="dwc:habitat" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A description or identifier of general information about the habitat
                in which the observation was made. Vocabulary will be consistent within a dataset
                and will be explained in metadata. Methods of determination (where applicable) will
                be explained in metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="bottomType" ref="ioosbiology:bottomType" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A description or identifier of general information about the sea
                floor at the coordinates or locality where the observation was made. Vocabulary will
                be consistent within a dataset and will be explained in metadata. Methods of
                determination (where applicable) will be explained in metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <!-- Quantification terms  -->

    <xsd:element name="quantificationVocabulary" ref="ioosbiology:quantificationVocabulary"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The names for dervied values, referred to as "quantification", can be
                drawn from a controlled vocabulary or vocabularies of quantification names. Or they
                can be reported in IOOS services using the verbatim name given by the data
                originator. Either the name of a controlled vocabulary or the word "verbatim" should
                be used in this term. Either way, within a dataset, both verbatim and vocabulary
                names must be used consistently, and explained in metadata.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="quantificationName" ref="dwc:measurementType" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A name for a derived value or processed data about the occurrence,
                for example, "Biomass". The word used in this terminology for such information is
                "quantification", rather than "abundance", because "abundance" may have specific
                methodological immplications in biology. In this example, biomass would not be
                obtained at survey time, rather biomass would be calculated from input data that was
                obtained at survey time, combined with a biomass calculation methodology. This term
                is used along with companion terms for quantification value, units, uncertainty,
                method, and determination details. It is suggested that names for derived values be
                more specific than "Biomass", because many institutions will develop biomass
                information using diverse methods. Suggested practice is to include some more
                specific reference(s) in the quantification name, such as insitution, survey, date
                or other specifics. For example, "Biomass-PIFSC-2011", and explain naming in
                metadata. </xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="quantificationValue" ref="dwc:measurementValue" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The value of the derived information product, such as the numerical
                value for biomass. This term does not include units. Units are contained in another
                term.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="quantificationUnit" ref="dwc:measurementUnit" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The units in which the value expresses the quantification, for
                example, "kg/m^2 surface" or "kilograms per square meter of ocean
                surface".</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="quantificationUncertainty" ref="dwc:measurementAccuracy" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>An estimate of the uncertainty, positive or negative (+/-) offset of
                the stated value, that expresses the uncertainty of the value as calculated and
                reported. Note that the expression in this term can combine both accuracy and
                precision considerations to a more general estimate, uncertainty, hence the slightly
                different name for this term from compared to the Darwin Core (dwc) reference
                term.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="quantificationDeterminedDate" ref="dwc:measurementDeterminedDate"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The date the quantification was determined. Can be different from the
                observation date.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="quantificationDeterminedBy" ref="dwc:measurementDeterminedBy"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name or ID of person(s) or institution(s) that determined the
                quantification.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="quantificationMethod" ref="dwc:measurementMethod" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A reference to the method used to determine the quantification. This
                will be different from the method used to make the observation of biological
                occurrence; it will be the companion calucation method that followed the observation
                method. Quantification information is expected to be only useful if method is
                sufficiently documented, so this term is vitally important for use of quantification
                terms for derived values. This term can contain a code or other abbreviated
                reference to a method. In all cases quantificationMethod should be explained in
                metadata and supporting publications or related resources
                identified.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <!-- Named geography terms  -->

    <xsd:element name="waterBody" ref="dwc:waterBody" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name of the water body in which the observation was made. For
                marine data, this is the ocean name. If there is a more specific named region, such
                as a bay or reef, or sector of the ocean (for example, northwest Pacific), add the
                regional name after the ocean name, separated by a semicolon. Note that the locality
                term will contain the most specific name, such as a pier or other named feature, so
                that lowest level of detail is not included in waterbody. The waterbody term is for
                the ocean and any named intermediate geography such as a region.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="islandGroup" ref="dwc:islandGroup" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name of an island group associated with the location where the
                observation was made.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="island" ref="dwc:island" type="xsd:">
        <xsd:annotation>
            <xsd:documentation>The name an island associated with the location where the observation
                was made.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="locality" ref="dwc:locality" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The locality is the most specific named place to identify the
                location of the observation. Many marine data rely strictly on geographic
                coordinates, so the locality term may be null. If a locality is used, it may be a
                specific location or feature name, such as "Pier 39" or "Atafu Atoll", or it may be
                a descriptive phrase, such as "a tidal pool 1500 meters north of Pier 39". Note that
                in marine observations, the latitude and longitude may be more precise than any
                named place would suggest, because the coordinates often come from navigation of GPS
                systems. Place names can be secondary locality identifiers and thus less precise
                than coordinates.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="country" ref="dwc:country" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name of the country in which the observation location
                ocurs.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="stateProvince" ref="dwc:stateProvince" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name of the state or province in which the observation location
                ocurs. Such geographic named locations may not be available or applicable for marine
                data, and acordingly the use of this term is optional. In some cases such
                jurisdiction identification may be crucial for data attribution, management and/or
                use, so this term is retained in the terminology for cases where it may be
                essential.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="county" ref="dwc:county" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name of the county or other comparable geographic unit in which
                the observation location ocurs. Such geographic named locations may not be available
                or applicable for marine data, and acordingly the use of this term is optional. In
                some cases such jurisdiction identification may be crucial for data attribution,
                management and/or use, so this term is retained in the terminology for cases where
                it may be essential.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="municipality" ref="dwc:municipality" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name of the municipality in which the observation location ocurs.
                Such geographic named locations may not be available or applicable for marine data,
                and acordingly the use of this term is optional. In some cases such jurisdiction
                identification may be crucial for data attribution, management and/or use, so this
                term is retained in the terminology for cases where it may be
                essential.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="geodeticDatum" ref="dwc:geodeticDatum" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The ellipsoid, geodetic datum, or spatial reference system used in
                decimalLatitude and decimalLongitude. IOOS preference is to provide all coordinates
                using EPSG:4326, also known as WGS 84. This element will identify the actual datum
                used, confirming WGS 84 or identifying what other datum applies.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="kingdom" ref="dwc:kingdom" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The full scientific name of the kingdom in which the taxon is
                classified.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="phylum" ref="dwc:phylum" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The full scientific name of the phylum in which the taxon is
                classified.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="class" ref="dwc:class" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The full scientific name of the class in which the taxon is
                classified.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="order" ref="dwc:order" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The full scientific name of the order in which the taxon is
                classified.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="family" ref="dwc:family" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The full scientific name of the family in which the taxon is
                classified.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="genus" ref="dwc:genus" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The full scientific name of the genus in which the taxon is
                classified.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="subgenus" ref="dwc:subgenus" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The full scientific name of the subgenus in which the taxon is
                classified. Values should include the genus to avoid homonym
                confusion.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="species" ref="dwc:specificEpithet" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The full scientific name of the species in which the taxon is
                classified. If a subspecies identification is provided, add the subspecies name
                after the species name separated by a space.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="infraspecificEpithet" ref="dwc:infraspecificEpithet" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The full scientific name of the subspecies, variant or other finer
                level identification.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="scientificNameAuthorship" ref="dwc:scientificNameAuthorship"
        type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The authorship information for the
                scientificName.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="taxonRemarks" ref="dwc:taxonRemarks" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>Comments or notes about the taxon or name.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="identifiedBy" ref="dwc:identifiedBy" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The name or other identifier of individual(s) or institution(s) that
                assigned the taxonomic name. Can be a list delimited by
                semicolon.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="identificationDate" ref="dwc:eventDate" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>The date the identification on this record was made, expressed in ISO
                8601 date format.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="identificationQualifier" ref="dwc:identificationQualifier" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>A brief phrase or a standard term ("cf.", "aff.") to express the
                determiner's doubts about the Identification.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

    <xsd:element name="identificationRemarks" ref="dwc:identificationRemarks" type="xsd:string">
        <xsd:annotation>
            <xsd:documentation>Comments or notes about the identification.</xsd:documentation>
        </xsd:annotation>
    </xsd:element>

</xsd:schema>

```

### **Previous Revisions**{: style="color: crimson"}

* [IOOS Biological Terms at Marine Metadata Interoperability (MMI) Ontology Registry and Repository (ORR) Website](http://mmisw.org/orr/#http://mmisw.org/ont/ioos/biological):
  - The MMI ORR provides reference URLs that promote machine-to-machine discovery and use of ontologies and vocabularies.
  -  To find out earlier version of the ontology, press the button "Versions" on top of the screen, and choose a URI from the drop-down window.  
