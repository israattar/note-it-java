# Note-It (Java Web App)

A simple note-taking web application built with Java, JSP/Servlets, and Tomcat 11.  
Users can create, edit, delete, and categorise notes with support for images, search, and sorting.  
Designed with clean architecture, thread safety, and modular principles for maintainability.

---

# Features
- CRUD Notes → Create, edit, delete notes (title, content, URLs, images)
- Categorisation → Organise notes into multiple categories, filter by category
- Views → Grid, List, and Summary display modes
- Search → Keyword-based search through notes
- Sorting → Newest first, oldest first, title (A–Z/Z–A)
- Persistence → JSON-based storage (using Gson)
- Thread Safety → `ConcurrentHashMap` for multi-user access

---

# Tech Stack
- Java 21
- Tomcat 11
- JSP/Servlets
- Gson (for JSON persistence)
- Maven (build tool)

---

# Getting Started

# Clone the repository
```bash
git clone https://github.com/<your-username>/note-it-java.git
cd note-it-java
