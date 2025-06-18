```dataview
TABLE WITHOUT ID 
  min(rows.file.folder) as Folder,
  min(rows.file.link) as File, 
  sum(rows.item.tags) as Tags, 
  map(items, (r) => "[" + r.status + "] " + r.text) as Tasks
FLATTEN file.tasks as item
GROUP BY file.folder + file.name + item.tags
FLATTEN array( filter( rows.item, (r) => r.status != "x" ) ) as items
WHERE items 
```
*This is a dynamic table created using the [dataview plugin](https://github.com/blacksmithgu/obsidian-dataview).*
