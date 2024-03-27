```dataviewjs
dv.span("** Exercise **")

const calendarData = {
    entries: []
}

//DataviewJS loop

for (let page of dv.pages('"Journal/Daily"').where(p => p.exercise)) {
    
    // dv.span("<br>" + page.file.name) // uncomment for troubleshooting
    calendarData.entries.push({
        date: page.file.name,     // (required) Format YYYY-MM-DD
        intensity: page.exercise, // (required) the data you want to track, will map color intensities automatically         
        content: await dv.span(`[](${page.file.name})`)
	})
}

renderHeatmapCalendar(this.container, calendarData)
```
