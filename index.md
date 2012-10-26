---
layout: home
permalink: /index.html
---

This repository serves as the canonical description of the schema used to list agency datasets and APIs as hosted at agency.gov/catalog.

Rationale
---------

Data is a national treasure... etc.

The digital strategy [requires](http://www.whitehouse.gov/sites/default/files/omb/egov/digital-government/digital-government.html#existing-data action item 2.2) agency to catalog and tag their data to make it more easily discoverable.

Think about it this way: Let's say you're an entrepreneur that wants to build a mobile app for people who enjoy fishing. Government data about fishing is spread across many agencies, thus making it hard to unlock the resources the govenment makes available. If however, both the Department of Commerce and Department of the Interior both tag their fisheries data "salmon", to use [http://www.youtube.com/watch?v=UIYgetzo1aQ a popular example], the entrepreneur can find salmon-related data across agency lines, by forcing the government, not the citizen, to absorb the complexity.

While it would be a fool's errand to try to predict in advance every such tag, a [http://en.wikipedia.org/wiki/Folksonomy folksonomy] would allow government agencies to describe their APIs as they see fit, and disambiguation can occur on the data.gov CMS/catalog level as necessary.

(talk about how outside developers can use this file, how it relates to sitemap.xml, etc.)

Hosting
-------

Each agency should catalog their existing datasets and APIs, both public and internal, in a file compatible with the formats described herein, and should host such a file at `agency.gov/catalog.xml` *and* `agency.gov/catalog.json`.

Datasets versus APIs
--------------------

APIs or Application Programming Interfaces are allow developers (both internal to the agency and the public) to dynamically query a dataset. For example, a dataset [of farmers markets](https://explore.data.gov/Agriculture/Farmers-Markets-Geographic-Data/wfna-38ey) may be made available for download as a single file (e.g., a CSV), or may be made available to developers as an API, such that a developer could provide the agency with a zipcode, and retrieve a list of farmers markets in that area.

The catalog file should include *both* datasets and APIs.

Basic Fields
------------

The following basic fields should be used to describe each dataset:

{.table striped}
Field               | Definition                                    | JSON            | RDFa Lite
-------             | ---------------                               | --------------  | ------- 
Title               | Human-readable name                           | title           | [dct:title](http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#terms-title)
Description         | Human-readable description                    | description     | [dct:description](http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#terms-description)
Documentation URL   | URL to documentation                          | dataDictionary  | [dcat:dataDictionary](http://www.w3.org/TR/vocab-dcat/#property--data-dictionary)
URL                 | URL to dataset or API                         | accessURL       | [dcat:accessURL](http://www.w3.org/TR/vocab-dcat/#property--access-download)
Tags                | Keywords describing data                      | keywords        | [dcat:keyword](http://www.w3.org/TR/vocab-dcat/#property--keyword-tag)
Public              | Whether the dataset is public (true/false)    | public          | TBD 
Queryable           | Whether dynamically queryable (true/false)    | queryable       | TBD

Expanded Fields
---------------

Agencies our encourage to use the following expanded fields when appropriate. Agencies may freely augment these fields with their own.

{.table striped}
Field               | Definition                                | JSON                  | RDFa Lite
------              | ------                                    | ----                  | --------
Last Modified       | Date of last update                       | modified              | [dct:modified](http://www.w3.org/TR/vocab-dcat/#property--update-modification-date-1)
Format              | The format(s) the dataset is available in | format                | [dct:format](http://www.w3.org/TR/vocab-dcat/#property--format)
Publisher           | Publishing entity                         | publisher             | [dct:publisher](http://www.w3.org/TR/vocab-dcat/#property--publisher-1)
Release Date        | date of formal issuance                   | issued                | [dct:issued](http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#issued)
Frequency           | frequency with which dataset is published | accrualPeriodicuity   | [dct:accrualPeriodicity](http://purl.org/dc/terms/accrualPeriodicity)
Unique Identifier   | A unique identifier for the dataset       | identifier            | [dct:identifier](http://purl.org/dc/terms/identifier)
Geographic Coverage | Spacial coverage of the dataset           | spacial               | [dct:spacial](http://purl.org/dc/terms/spatial)
Temporal Coverage   | Temporal period the dataset covers        | temporal              | [dct:temporal](http://purl.org/dc/terms/temporal)
Language            | The language of the dataset               | language              | [dct:language](http://purl.org/dc/terms/language)
License             | The license dataset is published with     | license               | [dct:license](http://purl.org/dc/terms/license)
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
Agency              | The publishing agency                     | Organization          | [foaf:Organization](http://xmlns.com/foaf/0.1/Organization)

(need to add vocab.data.gov terms)

[Full documentation](http://www.w3.org/TR/vocab-dcat/)

Examples
--------

* [JSON](examples/catalog.json)
* [XML](examples/xml/)
