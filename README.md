pg_checksums - Activate/deactivate/verify checksums in PostgreSQL clusters
==========================================================================

`pg_checksums` is based on the `pg_verify_checksums` and `pg_checksums`
programs available in PostgreSQL version 11 and from 12, respectively. It can
verify, activate, or deactivate checksums. Activating requires all database
blocks to be read and all page headers to be updated, so it can take a long time
on a large database.

The database cluster needs to be shut down cleanly in the case of checksum
activation or deactivation, while checksum verification can be performed
online, unlike PostgreSQL's `pg_checksums`.

Other changes include the possibility to toggle progress reporting via the
`SIGUSR1` signal, more fine-grained progress reporting and I/O rate limiting.

PostgreSQL versions 9.3 and newer are supported. The November 8th 2018 PostgreSQL
point release is required.
