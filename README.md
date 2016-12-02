# Islandora URL Redirector

An Islandora migration module that preserves permalinks from objects' previous repositories. When an incoming URL matches a defined pattern, the module looks up an object's old "permanent" URL from an identifier field and redirects the viewer to its new home in Islandora. This module can work in multiple ways:

* Install on the new Islandora repository, if you kept the same domain name
* Install on the old repository if it uses a Drupal front end
* Build a new Drupal site using this module, and point your old domain name there

## Requirements

* [Islandora](https://github.com/Islandora/islandora)
* [Islandora Solr Search](https://github.com/Islandora/islandora_solr_search)

Note: Whichever server you install the module on **must have access to the target repository's Solr instance.** This is not an issue if you're installing the module on your target repository.

## Installation

Same as any Drupal module.

## Configuration
This module assumes your permalinks follow certain patterns - the base URL, some defined snippet, and some variable ending. 

e.g. Original URL http://kora.kpu.ca/facultypub/26 

Four fields:

* URL snippets: string to look up, such as "facultypub" from the above example, or "kora.kpu.ca/facultypub". Enter multiple snippets **delimited by semicolon (with no space)**. 
* Solr field: the Solr field that contains the old URL.
* New hostname base URL: defaults to base URL of the site where the module lives.
* Solr base URL: By deafult it's localhost - leave that if you're not targeting an external site. Otherwise, you need to target the other site's Solr URL.

## Maintainer

[Brandon Weigel](https://github.com/bondjimbond)

Many thanks to [Mark Jordan](https://github.com/mjordan) for major contributions and advice.
