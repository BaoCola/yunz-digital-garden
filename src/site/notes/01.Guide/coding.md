```dataviewjs
for (let status of dv.pages("#coding").groupBy(p => p.status)) {
	dv.header(3, status.key);
	dv.table(["title", "date created", "tags"],
		status.rows
			.sort(s => s["date created"], 'desc')
			.map(s => [s.file.link, s["date created"], s.tags])
		)
}
```