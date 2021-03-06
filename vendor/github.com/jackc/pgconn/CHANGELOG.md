# 1.6.1 (June 27, 2020)

* Update golang.org/x/crypto to latest
* Update golang.org/x/text to 0.3.3
* Fix error handling for bad PGSERVICE definition
* Redact passwords in ParseConfig errors (Lukas Vogel)

# 1.6.0 (June 6, 2020)

* Fix panic when closing conn during cancellable query
* Fix behavior of sslmode=require with sslrootcert present (Petr Jediný)
* Fix field descriptions available after command concluded (Tobias Salzmann)
* Support connect_timeout (georgysavva)
* Handle IPv6 in connection URLs (Lukas Vogel)
* Fix ValidateConnect with cancelable context
* Improve CopyFrom performance
* Add Config.Copy (georgysavva)

# 1.5.0 (March 30, 2020)

* Update golang.org/x/crypto for security fix
* Implement "verify-ca" SSL mode (Greg Curtis)

# 1.4.0 (March 7, 2020)

* Fix ExecParams and ExecPrepared handling of empty query.
* Support reading config from PostgreSQL service files.

# 1.3.2 (February 14, 2020)

* Update chunkreader to v2.0.1 for optimized default buffer size.

# 1.3.1 (February 5, 2020)

* Fix CopyFrom deadlock when multiple NoticeResponse received during copy

# 1.3.0 (January 23, 2020)

* Add Hijack and Construct.
* Update pgproto3 to v2.0.1.

# 1.2.1 (January 13, 2020)

* Fix data race in context cancellation introduced in v1.2.0.

# 1.2.0 (January 11, 2020)

## Features

* Add Insert(), Update(), Delete(), and Select() statement type query methods to CommandTag.
* Add PgError.SQLState method. This could be used for compatibility with other drivers and databases.

## Performance

* Improve performance when context.Background() is used. (bakape)
* CommandTag.RowsAffected is faster and does not allocate.

## Fixes

* Try to cancel any in-progress query when a conn is closed by ctx cancel.
* Handle NoticeResponse during CopyFrom.
* Ignore errors sending Terminate message while closing connection. This mimics the behavior of libpq PGfinish.

# 1.1.0 (October 12, 2019)

* Add PgConn.IsBusy() method.

# 1.0.1 (September 19, 2019)

* Fix statement cache not properly cleaning discarded statements.
