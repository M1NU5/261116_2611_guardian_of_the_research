
```widgets
type: clock
```
> [!quote] 
> ```dataviewjs
> // Load Quotes.md as text
> const page = dv.page("Quotes");
> 
> // Convert list items into array
> const quotes = page.file.lists.map(l => l.text);
> 
> // Pick one based on the day of year
> const index = moment().dayOfYear() % quotes.length;
> 
> dv.paragraph(quotes[index]);
> ```


---
```meta-bind-button
label: "➕ Daily Note"
style: default
class: "pretty-button"
actions:
  - type: templaterCreateNote
    templateFile: "Settings/Templates/Daily Note.md"
    fileName: "Daily Note"
    folderPath: "PhD/1 Fleeting Notes/Daily Notes"
    openNote: true
    openIfAlreadyExists: true
```
```meta-bind-button
label: "➕ Person Profile"
style: default
class: "pretty-button"
actions:
  - type: templaterCreateNote
    functionName: createPersonProfile
    templateFile: "Settings/Templates/Person Profile.md"
    fileName: "Person Profile"
    folderPath: "PhD/0 Sources/People"
    openNote: true
```
```meta-bind-button
label: "➕ Literature Note"
style: default
class: "pretty-button"
actions:
  - type: templaterCreateNote
    functionName: createPhDLiteratureNoteAPA
    templateFile: "Settings/Templates/PhD Literature Note (APA).md"
    fileName: "Literature Note"
    folderPath: "PhD/2 Literature Notes"
    openNote: true
```

# Forward Load

```dataviewjs
const filePath = "Kanban.md";
const content = await dv.io.load(filePath);
const lines = content.split("\n");

const today = dv.date("today");

// Parse tasks
const tasks = lines
  .filter(l => /^- \[ \]/.test(l))
  .map(l => {
    const match = l.match(/\@\{(\d{2})-(\d{2})-(\d{4})\}/);
    return {
      text: l.replace(/^- \[ \] /, "").trim(),
      due: match ? dv.date(`${match[3]}-${match[2]}-${match[1]}`) : null
    };
  });

// Buckets
const overdue = tasks.filter(t => t.due && t.due < today);
const dueToday = tasks.filter(t => t.due && t.due.equals(today));

// Pill renderer
function pill(label, icon, count) {
  return `
    <span style="
      display:inline-block;
      padding:6px 14px;
      margin:4px;
      border-radius:20px;
      border:1px solid #bbb;
      background:transparent;
      color:#777;
      font-size:13px;
      font-weight:500;
      white-space:nowrap;
      text-align:center;
      line-height:1.4;
    ">
      ${icon} ${label}<br>
      <span style="font-size:12px; font-weight:400; color:#999;">Tasks: <b>${count}</b></span>
    </span>
  `;
}

// Build HTML with two pills
const html =
  pill("Overdue","⚠️",overdue.length) +
  pill("Due Today","📌",dueToday.length);

// ✅ Center the row
const container = dv.el("div","");
container.innerHTML = `<div style="text-align:center;">${html}</div>`;

```

```dataviewjs
const filePath = "Kanban.md";
const content = await dv.io.load(filePath);
const lines = content.split("\n");

const today = dv.date("today");

// Parse tasks
const tasks = lines
  .filter(l => /^- \[ \]/.test(l))
  .map(l => {
    const match = l.match(/\@\{(\d{2})-(\d{2})-(\d{4})\}/);
    return {
      text: l.replace(/^- \[ \] /, "").trim(),
      due: match ? dv.date(`${match[3]}-${match[2]}-${match[1]}`) : null
    };
  });

// Buckets
const week1 = tasks.filter(t => t.due && t.due >= today && t.due <= today.plus({ days: 7 }));
const week2 = tasks.filter(t => t.due && t.due > today.plus({ days: 7 }) && t.due <= today.plus({ days: 14 }));
const week3 = tasks.filter(t => t.due && t.due > today.plus({ days: 14 }) && t.due <= today.plus({ days: 21 }));
const week4 = tasks.filter(t => t.due && t.due > today.plus({ days: 21 }) && t.due <= today.plus({ days: 28 }));

// Pill renderer
function pill(label, icon, count) {
  return `
    <span style="
      display:inline-block;
      padding:6px 14px;
      margin:4px;
      border-radius:20px;
      border:1px solid #bbb;
      background:transparent;
      color:#777;
      font-size:13px;
      font-weight:500;
      white-space:nowrap;
      text-align:center;
      line-height:1.4;
    ">
      ${icon} ${label}<br>
      <span style="font-size:12px; font-weight:400; color:#999;">Tasks: <b>${count}</b></span>
    </span>
  `;
}

// Build HTML
const html =
  pill("Week 1","📅",week1.length) +
  pill("Week 2","📅",week2.length) +
  pill("Week 3","📅",week3.length) +
  pill("Week 4","📅",week4.length);

// ✅ Center the row
const container = dv.el("div","");
container.innerHTML = `<div style="text-align:center;">${html}</div>`;

```

