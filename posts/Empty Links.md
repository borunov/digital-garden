```dataview
TABLE without id
  file.link as "File",
  rows.Outlink as "Empty Link"
FLATTEN file.outlinks as Outlink
  WHERE !Outlink.file
  GROUP BY file
```

```dataview
TABLE without id
  file.link as "File",
  rows.Outlink as "Empty Link"
FLATTEN file.outlinks as Outlink
WHERE
  !Outlink.file and
  !startswith(meta(Outlink).path, "Files")
    GROUP BY file
```
