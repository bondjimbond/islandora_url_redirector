# Islandora Identifier Lookup

An Islandora module that lets you query get the UUID for an object if you know its PID, and get an object's PID if you know its UUID. Also lets you assign UUIDs to newly ingested objects.

## Querying for identifiers

The HTTP interface:

1. given an Islandora object's PID, returns the corresponding UUID that exists in the configurable datastream location.
2. given a UUID, returns the corresponding Islandora object's PID.

If neither the UUID or PID is found, the request returns a 404.

Take as an example an object with PID 'islandora:100' and &lt;identifier type="uuid"&gt;9299d87d-752b-4a24-a2b8-816103418bb2&lt;/identifier&gt; in its MODS  datastream. `curl "http://localhost:8000/islandora/idlookup/pid/islandora:100"` will yield `9299d87d-752b-4a24-a2b8-816103418bb2`, and `curl "http://localhost:8000/islandora/idlookup/uuid/9299d87d-752b-4a24-a2b8-816103418bb2"` will yield `islandora:100`.

Initially, querying for UUIDs stored in MODS is possible, but other types of identifiers and datastreams may follow if there is interest.

## Rationiale

Islandora lets you create PIDs that contain UUIDs. That's awesome. If you're happy with that, you don't need this module.

But UUID PIDs make for ugly and long URLs. Also, if you have an Islandora repository that didn't start off with UUID PIDs, you may not want to change your PID pattern now. Plus, you may have been using UUIDs as unique identifiers in another repo platform that you migrated from, and you (wisely) included those UUIDs in your metadata when you migrated to Islandora.

## Adding UUIDs to new objects

The module also provides an option to add an &lt;identifier type="uuid"&gt; element to the MODS datastream of all new objects on ingest. To do this, the module calls out to the server's `uuidgen` function (the filesystem path to the utility that generates UUIDs is configurable).

The module does not offer the ability to retroactively add UUIDs to existing MODS datastreams. That would be an awesome feature though.

## Installation

Same as any Drupal module.

## Congfiguration

Go to admin/islandora/tools/idlookup to configure it.

## Maintainer

[Mark Jordan](https://github.com/mjordan)
