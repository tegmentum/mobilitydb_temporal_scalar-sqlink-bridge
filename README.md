# mobilitydb-temporal-scalar-sqlite-bridge-dynlink

Phase A dynlink-mode sqlite bridge for `mobilitydb_temporal_scalar` (target `mobilitydb_temporal_scalar`).

Exports the declarative `sqlite:extension@1.0.0` metadata + scalar-
function contract. `metadata.describe()` advertises every scalar the
catalog names; `scalar-function.call(func-id, args)` routes per-row
invocations through `compose:dynlink/linker` against the resident
provider `mobilitydb_temporal_scalar-composed`. Aggregate / vtab / hook exports are
deferred to a follow-up.
