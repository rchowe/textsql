
TextSQL
=======

TextSQL is a way of querying text files (csv, tsv) files using SQLite queries. The script loads the file into an in-memory SQLite3 database, and then runs arbitrary commands on it.

The script is used like this:

```bash
$ textsql file.tsv
```

The tool is usable on any number of files, so long as they share the same delimiters. The first file is loaded into the table `file1`, the second is loaded into `file2`, and so on. By default each column is numbered `V1`, `V2`, and so on, however if you want to substitute your own headers you can specify them in a special way:

```bash
$ textsql file.tsv:header1,header2
```

This will give the file the headers `header1`, and `header2`. If a third column exists, it will be labed `V3`. Additionally, if the headers should be taken from the first line of the file instead:

```bash
$ textsql 'file.tsv:*'
```

This reads the headers from the first line of the file.

