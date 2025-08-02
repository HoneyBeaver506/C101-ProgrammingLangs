---
Title: Programming Lang Index
Topic: Index
tags:
  - programming/java
  - programming/cpp
  - theme/reference
  - type/okr
---

---
# 💻 C101 - Programming Languages
Personalized Vault with updates of my Coding Journey. Includes all languages I will learn and plan to learn along the way. This github repo is made with the idea to add constant updates with new notes, templates and features. Feel free to use these notes for your own learning journey.

**Java Learning Journey**
*File Index with all Notes*: [[Java Index]] -  Will be used with `dataview` to create visually pleasing indexes to quickly find files
*File Database*: [[J-DB]] - Will be used with `DB Folder` for a database feel.

**CPP Learning Journey**
*Files index with all Notes:* [[CPP Index]]
*File Database*: [[J-DB]]

**Ruby Learning Journey**
*Will Come SOON!*

**Front End Programming (HTML, CSS, JS, Bun)**
*Will Come SOON!*


---

# 📂 File Index Dashboard

_Last Updated: `= this.file.mtime`_  

```button
name 🏠 Launchpad
type link
action obsidian://open?vault=N101-LearningHub&file=Launchpad
color default
```
---

## 📄 Recent Files

### Recently Modified (Last 7 Days)

```dataview
TABLE WITHOUT ID
  file.link as "📄 File",
  file.folder as "📁 Folder",
  dateformat(file.mtime, "MMM dd, yyyy HH:mm") as "🕐 Modified",
  round(file.size / 1024) + " KB" as "💾 Size"
FROM #programming/java AND #programming/cpp 
WHERE file.mtime >= date(today) - dur(7 days)
SORT file.mtime DESC
LIMIT 15
```

### Recently Created (Last 30 Days)

```dataview
TABLE WITHOUT ID
  file.link as "📄 File",
  file.folder as "📁 Folder",
  dateformat(file.ctime, "MMM dd, yyyy") as "📅 Created",
  choice(file.tags, join(file.tags, ", "), "No tags") as "🏷️ Tags"
FROM #programming/java AND #programming/cpp 
WHERE file.ctime >= date(today) - dur(30 days)
SORT file.ctime DESC
LIMIT 10
```

---

## 🏷️ Files by Type

### Markdown Files by Category

```dataview
TABLE WITHOUT ID
  category as "📂 Category",
  length(rows) as "📄 Count",
  round(average(file.size) / 1024) + " KB" as "📊 Avg Size"
FROM ""
WHERE file.extension = "md"
FLATTEN choice(contains(file.path, "Daily Notes"), "Daily Notes",
         choice(contains(file.path, "_Templates"), "Templates",
         choice(contains(file.path, "Projects"), "Projects",
         choice(contains(file.path, "Archive"), "Archive",
         choice(contains(file.path, "_Attachments"), "Resources",
         "Other"))))) as category
GROUP BY category
SORT length(rows) DESC
```

### Attachment Files

```dataview
TABLE WITHOUT ID
  file.link as "📎 Attachment",
  file.extension as "🔧 Type",
  file.folder as "📁 Location",
  round(file.size / 1024) + " KB" as "💾 Size"
FROM "_Attachments"
WHERE file.extension != "md"
SORT file.size DESC
LIMIT 20
```

---

## 📅 Files by Date

### Files Modified This Week

```dataview
CALENDAR file.mtime
FROM #programming/java AND #programming/cpp 
WHERE file.mtime >= date(today) - dur(30 days)
```



---

## 📈 File Activity

### Most Linked Files (Highest Connectivity)

```dataview
TABLE WITHOUT ID
  file.link as "📄 File",
  file.inlinks.length as "⬅️ Incoming",
  file.outlinks.length as "➡️ Outgoing",
  (file.inlinks.length + file.outlinks.length) as "🔗 Total Links"
FROM #programming/java
WHERE file.extension = "md"
SORT (file.inlinks.length + file.outlinks.length) DESC
LIMIT 15
```

### Largest Files

```dataview
TABLE WITHOUT ID
  file.link as "📄 File",
  file.folder as "📁 Folder",
  round(file.size / 1024) + " KB" as "💾 Size",
  dateformat(file.mtime, "MMM dd") as "🕐 Modified"
FROM #programming/java AND #programming/cpp 
SORT file.size DESC
LIMIT 10
```

### Files by Tag Usage

```dataview
TABLE WITHOUT ID
  tag as "🏷️ Tag",
  length(rows) as "📄 Files",
  join(map(rows.file.link, (l) => l), ", ") as "🔗 Tagged Files"
FROM #programming/java AND #programming/cpp 
FLATTEN file.etags as tag
WHERE tag
GROUP BY tag
SORT length(rows) DESC
LIMIT 15
```

---
# 🔌 Plugins Used
1. Advanced Tables
2. Auto Card Link
3. Banners
4. Buttons
5. Calendar
6. Commander
7. Dataview
8. DB Folder
9. Dictionary
10. Editing Toolbar
11. Excalidraw
12. Git
13. Hider
14. Homepage
15. Iconize
16. Janitor
17. Kanbam
18. Linter
19. Make.MD
20. Mind Map
21. Note Refactor
22. Plugin update Tracker
23. Quick Add
24. Settings Search
25. Style Settings
26. Table of Contents
27. Tag Wrangler
28. Tag Folder
29. Templater


# 🖼️ Style Settings:
*Appearance:* Border
```json
{
  "Components@@Ribbon-autohide": true,
  "Components@@CTA-BTN-enable": true,
  "Components@@file-names-untrim": true,
  "Components@@folder-font-bold": true,
  "Components@@outline-enhanced": true,
  "Components@@immersive-canvas": true,
  "Appearance-dark@@card-layout-open-dark": true,
  "Appearance-dark@@theme-dark-style-select": "theme-dark-background-darker",
  "Editor@@line-hover-indicator": true,
  "Editor@@border-focus-mode": true,
  "Editor@@codeblock-style-select": "codeblock-style-one-dark",
  "Editor@@callout-style-select": "callout-style-1",
  "Editor@@seamless-embeds": true
}
```


----
## ⚠️ Copyright Warning
These notes belong to me as I paraphrased and modified them. I took inspiration from several videos in youtube however and would like to give then credit for the great zettlekesten setup. I will also be using websites likes Programmiz, Tutorial Sploit, GeeksForGeeks and FreeCodeCamp as these are the most reliable when learning code.

## Open Source - No License (Please respect their original owner) 