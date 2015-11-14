# Islandora Identifier Lookup

## Querying for identifiers

Islandora module that provides a simple HTTP interface for:

1. Given an Islandora object's PID, returning the corresponding UUID that exists in the configurable datastream location.
2. Given a UUID, returning the corresponding Islandora object's PID.

If neither the UUID or PID is found, the request returns a 404.

Take as an example an object with PID 'islandora:100' and &lt;identifier type="uuid"&gt;9299d87d-752b-4a24-a2b8-816103418bb2&lt;/identifier&gt; in its MODS  datastream. `curl "http://localhost:8000/islandora/idlookup/pid/islandora:100"` will yield `9299d87d-752b-4a24-a2b8-816103418bb2`, and `curl "http://localhost:8000/islandora/idlookup/uuid/9299d87d-752b-4a24-a2b8-816103418bb2"` will yield `islandora:100`.

Initially, querying for UUIDs stored in MODS is possible, but other types of identifiers and datastreams may follow.

## Adding UUIDs to new objects

The module also provides an option to add an &lt;identifier type="uuid"&gt; element to the MODS datastream of all new objects on ingest. To do this, the module calls out to the server's `uuidgen` function (the filesystem path to the utility that generates UUIDs is configurable).

The module does not offer the ability to retroactively add UUIDs to existing MODS datastreams.

## Installation

Same as any Drupal module. Go to admin/islandora/tools/idlookup to configure it.

## Maintainer

Mark Jordan
