# PostgreSQL

### Information Schema
The information schema consists of a set of tables and views that contain information about the objects defined in the current database. The information schema is defined in the SQL standars

A couple of ways to list tables being managed for a database (public, information_schema, pg_catalog, etc):

```
SELECT * FROM information_schema.tables;
```

```
\dt *.*
```

```
SELECT * FROM pg_tables;
```

List views for an information schema:

```
SELECT * FROM information_schema.views;
```
```
SELECT * FROM information_schema.tables WHERE table_type = 'VIEW';
```

###### Examples

List tables:

```
SELECT table_catalog, table_schema, table_name, table_type FROM information_schema.tables WHERE table_type = 'BASE TABLE' AND table_schema = 'information_schema' ORDER BY table_schema ASC;
```
```
\dt information_schema.
```

List views:

```
SELECT table_catalog, table_schema, table_name, table_type FROM information_schema.tables WHERE table_type = 'VIEW' AND table_schema = 'information_schema' ORDER BY table_schema ASC;
```
```
SELECT table_schema, table_catalog, table_name FROM information_schema.views ORDER BY table_schema ASC;
```
```
\dv information_schema.
```

### System catalogs
The system catalogs contain schema metadata, such as information about tables, columns, and internal bookkeeping. System catalogs are regular tables. Normally you should not change the system catalogs by hand.

List tables:
