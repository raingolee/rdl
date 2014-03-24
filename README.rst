rdl - Redis dump-load tool
==========================

This tool is made specially for dump & load certain database of a redis server,
if you want to dump whole redis or replicate from one to another,
please checkout ``redis bgsave`` or ``redis replication`` on google.

Usage
-----

::

    usage: rdl.py [-h] [-n N] [-f] ACTION FILE

    Redis dump-load tool.

    positional arguments:
      ACTION      `dump` or `load`.
      FILE        if action is dump, then its output file, if actions is load,
                  then its source file.

    optional arguments:
      -h, --help  show this help message and exit
      -n N        Number of database to process.
      -f          Force or flush database before load


Example
-------

Dump database 1 to file redis.dump::

    $ ./rdl.py dump redis.dump -n 1

Load to database 1 from file redis.dump::

    $ ./rdl.py load redis.dump -n 3 -f