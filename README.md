# Islandora URL Redirector

An Islandora migration module that looks up an object's old "permanent" URL from an identifier field and redirects the viewer to its new home in Islandora. 

## Requirements

* [Islandora](https://github.com/Islandora/islandora)
* [Islandora Solr Search](https://github.com/Islandora/islandora_solr_search)

## Installation

Same as any Drupal module.

## Configuration
This module assumes your permalinks follow certain patterns - the base URL, some defined snippet, and some variable ending. 
e.g. Original URL http://kora.kpu.ca/facultypub/26 
Three fields:
* URL snippets: such as "facultypub" from the above example. Enter multiple snippets **delimited by semicolon (with no space)**.
* Solr field: the Solr field that contains the old URL.
* New hostname base URL: defaults to base URL of the site where the module lives.

## Wish list

Coming soon

## Maintainer

[Brandon Weigel](https://github.com/bondjimbond)
