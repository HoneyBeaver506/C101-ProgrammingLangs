---
Title: Java Index
Topic: Java Learning Curve
tags:
  - programming/java
  - theme/reference
  - type/okr
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
FROM #programming/java
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
FROM #programming/java
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
FROM #programming/java
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
FROM #programming/java
SORT file.size DESC
LIMIT 10
```

### Files by Tag Usage

```dataview
TABLE WITHOUT ID
  tag as "🏷️ Tag",
  length(rows) as "📄 Files",
  join(map(rows.file.link, (l) => l), ", ") as "🔗 Tagged Files"
FROM #programming/java
FLATTEN file.etags as tag
WHERE tag
GROUP BY tag
SORT length(rows) DESC
LIMIT 15
```

---

