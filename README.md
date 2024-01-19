Railway PgBouncer Template
======================

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/L09YMd?referralCode=_Q8oMR)

This is a minimal PgBouncer image, based on Alpine Linux. Derived from https://github.com/edoburu/docker-pgbouncer

Features:

* Very small, quick to pull (just 15MB)
* Configurable using environment variables
* Uses standard Postgres port 5432, to work transparently for applications.


Why use PgBouncer
-----------------

PostgreSQL connections take up a lot of memory ([about 10MB per connection](http://hans.io/blog/2014/02/19/postgresql_connection)). There is also a significant startup cost to establish a connection with TLS, hence web applications gain performance by using persistent connections.

By placing PgBouncer in between the web application and the actual PostgreSQL database, the memory and start-up costs are reduced. The web application can keep persistent connections to PgBouncer, while PgBouncer only keeps a few connections to the actual PostgreSQL server. It can reuse the same connection for multiple clients.
