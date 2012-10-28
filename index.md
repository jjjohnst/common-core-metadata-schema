---
layout: home
permalink: /index.html
---


This repository serves as the canonical description of the schema used to list agency datasets and APIs as hosted at agency.gov/data.  


Common core and extensible metadata 
-----------------------------------

Metadata are selected fields or elements which describe data.  The challenge is to define the standard metadata fields and the names of those fields so that the consumer of the data has sufficient information to process the data. The more information that can be conveyed in a recognized standard, the more valuable data becomes. Metadata can range from basic to advanced – from allowing one to discover the mere fact that a certain data asset exists and is about a general subject all the way to providing detailed semantic information that enables a high degree of machine readability. Making the metadata machine readable greatly increases its openness and utility.

Establishing a common vocabulary is the key to any communication, including communication between machines.  [Schema.org](http://www.schema.org) is a vocabulary that is being developed through a collaboration of the major search engines and will be the basis for the **common core metadata** required in this memorandum. The standard consists of a number of schemas (hierarchical vocabulary terms) that represent things that are most often looked for on the web and encapsulates many of the early lessons learned from vocabulary development.  

To fulfill the requirements of this memorandum, agencies should begin to [describe datasets using the schema.org vocabulary](http://blog.schema.org/). “Extensional” and/or domain specific metadata can easily be added using other vocabularies to embedded HTML markup even if it is not a term (entity/property) that will get indexed by the major search engines – it could still be indexed by other custom search engines and by Data.gov harvesting. 

Schema.org uses [RDFa Lite](http://www.w3.org/TR/rdfa-lite/), a subset of RDFa (Resource Description Framework in Attribute) that provides a common syntax for expressing metadata on websites in a way that computers can understand and begin to formulate knowledge about those data about your organization.  The “Lite” means that it is not the full set of metadata that may be used to convey useful information about an organization, but instead provides a minimal set that will supply the most relevant information about an organization.  Using RDFa Lite, an agency may include other vocabularies (such as DCAT, FOAF, and Dublin Core) as long as they are properly assigned.  More information on adopting common core and extensible metadata can be found on [Project Open Data](http://project-open-data.github.com/).


Hosting
-------

Each agency should catalog their existing datasets and APIs, both public and internal, in a file compatible with the formats described herein, and should host such a file at `agency.gov/data/data.xml` *and* `agency.gov/data/data.json`.


Datasets versus APIs
--------------------

APIs or Application Programming Interfaces are allow developers (both internal to the agency and the public) to dynamically query a dataset. For example, a dataset [of farmers markets](https://explore.data.gov/Agriculture/Farmers-Markets-Geographic-Data/wfna-38ey) may be made available for download as a single file (e.g., a CSV), or may be made available to developers as an API, such that a developer could provide the agency with a zipcode, and retrieve a list of farmers markets in that area.

The catalog file should include *both* datasets and APIs.

Basic Fields
------------

The following basic fields should be used to describe each dataset:

{.table .table-striped}
Field               | Definition                                    | JSON            | RDFa Lite
-------             | ---------------                               | --------------  | ------- 
Title               | Human-readable name                           | title           | [dct:title](http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#terms-title)
Description         | Human-readable description                    | description     | [dct:description](http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#terms-description)
Documentation URL   | URL to documentation                          | dataDictionary  | [dcat:dataDictionary](http://www.w3.org/TR/vocab-dcat/#property--data-dictionary)
URL                 | URL to dataset or API                         | accessURL       | [dcat:accessURL](http://www.w3.org/TR/vocab-dcat/#property--access-download)
Tags                | Keywords describing data                      | keywords        | [dcat:keyword](http://www.w3.org/TR/vocab-dcat/#property--keyword-tag)
License             | The license dataset is published with     | license               | [dct:license](http://purl.org/dc/terms/license)
Public              | Whether the dataset is public (true/false)    | public          | [xsd:boolean](http://www.w3.org/TR/xmlschema-2/#boolean)
Agency              | The publishing agency                     | Organization          | [foaf:Organization](http://xmlns.com/foaf/0.1/Organization)


Expanded Fields
---------------

Agencies our encourage to use the following expanded fields when appropriate. Agencies may freely augment these fields with their own.

{.table .table-striped}
Field               | Definition                                | JSON                  | RDFa Lite
------              | ------                                    | ----                  | --------
Last Modified       | Date of last update                       | modified              | [dct:modified](http://www.w3.org/TR/vocab-dcat/#property--update-modification-date-1)
Format              | The format(s) the dataset is available in | format                | [dct:format](http://www.w3.org/TR/vocab-dcat/#property--format)
Publisher           | Publishing entity                         | publisher             | [dct:publisher](http://www.w3.org/TR/vocab-dcat/#property--publisher-1)
Release Date        | date of formal issuance                   | issued                | [dct:issued](http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#issued)
Frequency           | frequency with which dataset is published | accrualPeriodicity   | [dct:accrualPeriodicity](http://purl.org/dc/terms/accrualPeriodicity)
Unique Identifier   | A unique identifier for the dataset       | identifier            | [dct:identifier](http://purl.org/dc/terms/identifier)
Geographic Coverage | Spatial coverage of the dataset           | spatial               | [dct:spatial](http://purl.org/dc/terms/spatial)
Temporal Coverage   | Temporal period the dataset covers        | temporal              | [dct:temporal](http://purl.org/dc/terms/temporal)
Language            | The language of the dataset               | language              | [dct:language](http://purl.org/dc/terms/language)
Granularity         | Level of granularity                      | granularity           | [dcat:granularity](http://www.w3.org/ns/dcat#)
Data Quality        | Describe the quality of the data          | dataQuality           | [dcat:dataQuality](http://www.w3.org/ns/dcat#dataQuality)
Category            | Main category of the dataset              | theme                 | [dcat:theme](http://www.w3.org/ns/dcat#theme)
Related Documents   | Related documents such as developer docs  | references            | [dcterms:references](http://purl.org/dc/terms/references)
Distribution        | Connects a dataset to available distributions | distribution     | [dcat:distribution](http://www.w3.org/ns/dcat#distribution)
Size                | The size of the distribution              | size                  | [dcat:size](http://www.w3.org/ns/dcat#size)
Format              | The format of the distribution            | format                | [dcterms:format](http://purl.org/dc/terms/format)
Download URL        | Downloadable distribution of a dataset    | download              | [dcat:download](http://www.w3.org/ns/dcat#Download)
Endpoint            | Endpoint of web service to access dataset  | WebService            | [dcat:WebService](http://www.w3.org/ns/dcat#WebService)
RSS Feed            | Availability of dataset as a feed         | Feed                  | [dcat:feed](http://www.w3.org/ns/dcat#Feed)

(need to add vocab.data.gov terms)

[Full documentation](http://www.w3.org/TR/vocab-dcat/)

Examples
--------

* [JSON](examples/catalog.json)
* [XML](examples/xml/)
