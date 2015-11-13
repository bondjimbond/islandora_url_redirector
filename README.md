# Islandora Identifier Lookup

Proof of concept module to provide a simple HTTP interface for:

1. Given an Islandora object's PID, return the corresponding UUID.
2. Given a UUID, return the corresponding Islandora object's PID.

If neither the UUID or PID is found, returns a 404.

Initially, querying on and for UUIDs will be possible, but others may follow.

Also provides an option to add an &lt;identifier&gt; field (type='uuid') to the MODS datastream of all new objects. To do this, the module calls out to the server's `uuidgen` function, so may not work on all platforms.

## Maintainer

Mark Jordan
