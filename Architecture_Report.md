# Architecture Report – Note-It (Java Web App)

## Overview
This Java-based web application implements a simple note-taking system.  
Key features include:
- Creation, editing, and deletion of notes
- Categorisation into multiple categories
- Grid, list, and summary views
- Keyword search and sorting
- JSON-based persistence of data
- Support for images and attachments

---

## Design Principles
The design follows key software engineering principles:

- **Single Responsibility Principle (SRP)** – each class has one responsibility.
- **Open/Closed Principle (OCP)** – classes are open for extension but closed for modification.
- **Encapsulation** – private fields with getters and setters for controlled access.
- **Abstraction** – implementation details are hidden behind clear interfaces.
- **Thread Safety** – `ConcurrentHashMap` ensures safe concurrent access.
- **Separation of Concerns** – business logic, data access, and HTTP handling are clearly separated.

---

## Class Responsibilities

### Main Class
- Manages application startup and embedded Tomcat configuration.
- Encapsulates server lifecycle (startup, shutdown).
- Centralises server-related functionality.

### Model Class
- Singleton managing application state.
- Uses `ConcurrentHashMap` for thread-safe note management.
- Provides JSON-based persistence using the Gson library.
- Separates persistence logic from business logic.

### Note Class
- Represents individual notes with title, content, metadata, and optional images.
- Each note has a unique UUID and immutable timestamp.
- Encapsulates logic for automatic modification time updates.

### NoteCategory Class
- Defines and manages categories of notes.
- Supports filtering, renaming, and deletion of categories.
- Designed for future extensibility (e.g., icons, colours).

### Servlet Classes
- REST-style HTTP endpoints for CRUD operations and searching.
- Responsible only for request/response handling.
- Business logic delegated to the Model class.
- Implements consistent error handling and response formatting.

---

## Architecture Benefits
- **Separation of Concerns** → easier maintenance and scaling.
- **Thread Safety** → reliable handling of concurrent requests.
- **Modularity** → clear class boundaries and well-defined responsibilities.
- **Extensibility** → flexible for future features (authentication, DB storage).
- **Maintainability** → clean architecture with minimal coupling.

---

## Future Improvements
- User authentication and login system.
- Enhanced categories (icons, colours, hierarchies).
- Migration from JSON to relational or NoSQL database.
- Exposing REST APIs for external clients.
- Improved UI and styling.

---

## UML Diagram
![UML Diagram](uml.png)

![UML Diagram](uml.png)
