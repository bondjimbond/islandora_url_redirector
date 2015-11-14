# Islandora Identifier Lookup

Proof of concept module to provide a simple HTTP interface for:

1. Given an Islandora object's PID, returning the corresponding UUID.
2. Given a UUID, returning the corresponding Islandora object's PID.

If neither the UUID or PID is found, the request returns a 404.

Take as an object with PID 'islandora:26' and &lt;identifier type="uuid"&gt;9299d87d-752b-4a24-a2b8-816103418bb2&lt;/identifier&gt; in its MODS  datastream. `curl "http://localhost:8000/islandora/idlookup/pid/islandora:26"` will yield `9299d87d-752b-4a24-a2b8-816103418bb2`, and `curl "http://localhost:8000/islandora/idlookup/uuid/9299d87d-752b-4a24-a2b8-816103418bb2"` will yield `islandora:26`.

Initially, querying for UUIDs is possible, but other types of identifiers may follow.

The module also provides an option to add an &lt;identifier&gt; field (type='uuid') to the MODS datastream of all new objects. To do this, the module calls out to the server's `uuidgen` function, so may not work on all platforms.

## Maintainer

Mark Jordan
