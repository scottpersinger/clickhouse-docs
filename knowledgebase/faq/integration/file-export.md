---
slug: /en/faq/integration/file-export
title: How do I export data from ClickHouse to a file?
toc_hidden: true
toc_priority: 10
---

# How Do I Export Data from ClickHouse to a File? {#how-to-export-to-file}

## Using INTO OUTFILE Clause {#using-into-outfile-clause}

Add an [INTO OUTFILE](https://clickhouse.com/docs/en/sql-reference/statements/select/into-outfile.md) clause to your query.

For example:

``` sql
SELECT * FROM table INTO OUTFILE 'file'
```

By default, ClickHouse uses the [TabSeparated](https://clickhouse.com/docs/en/interfaces/formats.md) format for output data. To select the [data format](https://clickhouse.com/docs/en/interfaces/formats.md), use the [FORMAT clause](https://clickhouse.com/docs/en/sql-reference/statements/select/format.md).

For example:

``` sql
SELECT * FROM table INTO OUTFILE 'file' FORMAT CSV
```

## Using a File-Engine Table {#using-a-file-engine-table}

See [File](https://clickhouse.com/docs/en/engines/table-engines/special/file.md) table engine.

## Using Command-Line Redirection {#using-command-line-redirection}

``` bash
$ clickhouse-client --query "SELECT * from table" --format FormatName > result.txt
```

See [clickhouse-client](https://clickhouse.com/docs/en/interfaces/cli.md).
