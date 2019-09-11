# Islandora Google Scholar - JSON-LD

## Introduction

Automatically embeds JSON-LD in object pages. The JSON-LD fields are mapped from an object's MODS record as follows.

cModel|	Schema.org|
|--------- |-------------| 
|ir:thesisCModel	| @type="Thesis"|
ir:citationCModel |	@type="ScholarlyArticle"
islandora:sp_basic_image |	@type="ImageObject"
islandora:sp_large_image_cmodel | @type="ImageObject"
islandora:sp_pdf |	@type="DigitalDocument"
islandora:sp-audioCModel |	@type="AudioObject"
islandora:sp_videoCModel |	@type="VideoObject"
islandora:bookCModel |	@type="Book"
islandora:newspaperCModel |	@type="Newspaper"
islandora:eventCModel |	@type="Event"
islandora:placeCModel |	@type="Place"
islandora:personCModel |	@type="Person"
islandora:organizationCModel |	@type="CollegeorUniversity"
islandora:sp_disk_image |	@type="Dataset"
islandora:sp_web_archive | @type="WebPage"

XPath|Schema.org|
|--------- |-------------| 
/mods:titleInfo/mods:title|	name
/mods:name[@type="corporate"][mods:role/mods:roleTerm = "Degree grantor"]/mods:namePart	| sourceOrganization @type="CollegeOrUniversity"
/mods:name/mods:role[mods:roleTerm = "author"]/../mods:namePart[@type="family"]	|	author @type="Person"
/mods:originInfo/mods:dateIssued	| datePublished
/mods:abstract	| description
/mods:part/mods:subject/mods:topic	|	keywords
/mods:extent[@unit="page"]/mods:start	| pageStart
/mods:identifier[@type="doi"]	|	identifier @type:"PropertyValue" propertyID:"DOI"
/mods:extension/etd:degree/etd:name, /mods:extension/etd:degree/etd:discipline	| inSupportOf
/mods:language	| inLanguage
/mods:nameIdentifier	|	@type:schema:Person @id

## Requirements

This module requires the following modules/libraries:

* [Islandora](https://github.com/islandora/islandora)
* [Islandora Scholar](https://github.com/islandora/islandora_scholar)
* [Islandora Google Scholar](https://github.com/Born-Digital-US/islandora_scholar/tree/7.x/modules/islandora_google_scholar)
* [Islandora Solr](https://github.com/Islandora/islandora_solr_search)
* [Citeproc](https://github.com/Islandora/islandora_scholar/tree/7.x/modules/citeproc)
* [CSL](https://github.com/Islandora/islandora_scholar/tree/7.x/modules/csl)
* [Bibutils](https://github.com/Islandora/islandora_scholar/tree/7.x/modules/bibutils)

## Installation

Install as usual, see [this](https://drupal.org/documentation/install/modules-themes/modules-7) for further information.

## Configuration

Enable the module via Administration » Modules (admin/modules)

## Troubleshooting/Issues

Having problems or solved a problem? Check out the Islandora google groups for a solution.

* [Islandora Group](https://groups.google.com/forum/?hl=en&fromgroups#!forum/islandora)
* [Islandora Dev Group](https://groups.google.com/forum/?hl=en&fromgroups#!forum/islandora-dev)

## Maintainers/Sponsors

Current maintainers:

* Hertzel Armengol <emudojo@gmail.com>

## Development

If you would like to contribute to this module, please check out our helpful [Documentation for Developers](https://github.com/Islandora/islandora/wiki#wiki-documentation-for-developers) info, as well as our [Developers](http://islandora.ca/developers) section on the Islandora.ca site.

## License

[GPLv3](http://www.gnu.org/licenses/gpl-3.0.txt)
