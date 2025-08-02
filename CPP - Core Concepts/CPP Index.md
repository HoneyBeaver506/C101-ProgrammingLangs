---
Title: C++ Index
Topic: C++ Learning Curve
tags:
  - programming/cpp
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
FROM #programming/cpp 
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
FROM #programming/cpp
WHERE file.ctime >= date(today) - dur(30 days)
SORT file.ctime DESC
LIMIT 10
```

---

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
FROM #programming/cpp
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
FROM #programming/cpp 
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
FROM #programming/cpp 
SORT file.size DESC
LIMIT 10
```

### Files by Tag Usage

```dataview
TABLE WITHOUT ID
  tag as "🏷️ Tag",
  length(rows) as "📄 Files",
  join(map(rows.file.link, (l) => l), ", ") as "🔗 Tagged Files"
FROM #programming/cpp
FLATTEN file.etags as tag
WHERE tag
GROUP BY tag
SORT length(rows) DESC
LIMIT 15
```

---

