# TimescaleDB
TimescaleDB is an open-source database designed to make SQL scalable for time-series data. It is engineered up from PostgreSQL and packaged as a PostgreSQL extension, providing automatic partitioning across time and space (partitioning key), as well as full SQL support.

Timescale Cloud is our fully managed, hosted version of TimescaleDB, available in the cloud of your choice (pay-as-you-go, with free trial credits to start). To determine which option is best for you, see Timescale Products for more information about our Apache-2 version, TimescaleDB Community (self-hosted) and Timescale Cloud (hosted), including: feature comparisons, FAQ, documentation, and support.

Using TimescaleDB
TimescaleDB scales PostgreSQL for time-series data via automatic partitioning across time and space (partitioning key), yet retains the standard PostgreSQL interface.

In other words, TimescaleDB exposes what look like regular tables, but are actually only an abstraction (or a virtual view) of many individual tables comprising the actual data. This single-table view, which we call a hypertable, is comprised of many chunks, which are created by partitioning the hypertable's data in either one or two dimensions: by a time interval, and by an (optional) "partition key" such as device id, location, user id, etc. (Architecture discussion)

Virtually all user interactions with TimescaleDB are with hypertables. Creating tables and indexes, altering tables, inserting data, selecting data, etc., can (and should) all be executed on the hypertable.

From the perspective of both use and management, TimescaleDB just looks and feels like PostgreSQL, and can be managed and queried as such.

Before you start
PostgreSQL's out-of-the-box settings are typically too conservative for modern servers and TimescaleDB. You should make sure your postgresql.conf settings are tuned, either by using timescaledb-tune or doing it manually.
