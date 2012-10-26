---

---
Data Catalog Schema
===================

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

Field           | Definition                                    | JSON Field Key  | XML Tag  
-------         | ---------------                               | --------------  | ------- 
Name            | Human-readable name                           | name            | [dct:title](http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#terms-title)
Description     | Human-readable description                    | description     | [dct:description](http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#terms-description)
Documentation   | URL to documentation                          | documentation   | [dcat:dataDictionary](http://www.w3.org/TR/vocab-dcat/#property--data-dictionary)
URL             | URL to dataset or API                         | url             | [dcat:accessURL](http://www.w3.org/TR/vocab-dcat/#property--access-download)
Tags            | Keywords describing data                      | tags            | [dcat:keyword](http://www.w3.org/TR/vocab-dcat/#property--keyword-tag)
Public          | Whether the dataset is public (true/false)    | public          | TBD 
Queryable       | Whether dynamically queryable (true/false)    | queryable       | TBD

Expanded Fields
---------------

Agencies our encourage to use the following expanded fields when appropriate. Agencies may freely augment these fields with their own.

Field           | Definition                                | JSON Field Key  | XML Tag  
------          | ------                                    | --------------  | --------
Last Modified   | Date of last update                       | last_modified   | [dcterms:modified](http://www.w3.org/TR/vocab-dcat/#property--update-modification-date-1)
Format          | The format(s) the dataset is available in | format          | [dcterms:format](http://www.w3.org/TR/vocab-dcat/#property--format)

...

[Additional fields](http://www.w3.org/TR/vocab-dcat/)

Examples
--------

* [JSON](examples/catalog.json)
* [XML](examples/xml/)