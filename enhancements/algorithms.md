# Category Enhancement 1: Algorithms

[Back to Home](../README.md)

## Artifact Narrative

### 1. Artifact Description
The artifact selected for the Software Design and Engineering category is **FitTrack** (Elijah’s Weight Tracker App), a native Android application designed to track user weight metrics, set personal goals, and manage goal progression over time. The application was originally developed during my coursework in **CS 360: Mobile Architecture and Programming**. Built using Java and the Android SDK, the original application utilized a traditional Android SQLite architecture (`SQLiteOpenHelper`) to store local user records, authentication credentials, and daily weight entries. The core baseline functionality allowed users to log in, enter daily weight data, view historical entries in a list layout, and receive SMS alerts when weight milestones were reached.

### 2. Justification & Software Development Showcase
I selected this artifact for my ePortfolio because it represents a complete, full-lifecycle mobile application that demonstrates my ability to design, architect, and optimize object-oriented software. Mobile applications require careful management of hardware resources, asynchronous processing, and clean structural architecture to ensure system responsiveness, maintainability, and scalability. 

To demonstrate modern software design principles, I executed several targeted structural enhancements:
* **MVVM & Repository Pattern Architecture:** Refactored the original architecture—which tightly coupled UI controllers (`Activity` and `Fragment` classes) directly with database helper methods—to follow the Model-View-ViewModel (MVVM) and Repository patterns. Decoupling business logic and data access from the presentation layer resulted in cleaner, highly maintainable, and unit-testable code.
* **Database & Persistence Layer Refactoring:** Replaced raw `SQLiteOpenHelper` implementations with Android's Room Persistence Library, providing compile-time verification of SQL queries, robust object-relational mapping (ORM), and seamless integration with observable data streams.
* **Asynchronous Execution & UI Responsiveness:** Eliminated database transactions on the main UI thread (which previously caused minor rendering stutters during heavy read/write operations) by implementing asynchronous execution using background thread executors and wrapping database queries in `LiveData`. This guarantees smooth UI rendering and real-time interface updates.
* **Code Cleanliness & Modularization:** Modularized utility classes, extracted hardcoded UI strings into dynamic resource files (`strings.xml`), and unified data validation logic into reusable helper components.

### 3. Course Outcomes Alignment
Through these software design enhancements, I successfully met and demonstrated progress toward **Course Outcomes 2, 3, and 4**:
* **Outcome 2 (Professional Communication):** Delivered clear, modular, and self-documenting code supported by clean architectural patterns.
* **Outcome 3 (Algorithmic & Design Choices):** Designed and evaluated computing solutions using object-oriented principles, managing design trade-offs between synchronous UI rendering and asynchronous background thread execution.
* **Outcome 4 (Tools & Techniques):** Demonstrated mastery of industry-standard mobile tools and architecture frameworks, including Room ORM, ViewModels, and `LiveData`.

My original outcome-coverage plan established in Module One remains fully accurate, and the execution fulfilled all intended milestones without requiring deviation from the initial plan established during the code review.

### 4. Reflection, Learnings & Challenges
Enhancing an artifact created earlier in my academic program provided a valuable lesson in software maintenance and technical debt management. While authoring code from scratch is often straightforward, stepping back into a legacy codebase to refactor architecture requires deep static analysis and structural planning. I gained practical, hands-on experience refactoring synchronous database code into an asynchronous, lifecycle-aware data pipeline.

The primary technical challenges involved managing Android lifecycle states and database schema migration:
* **Lifecycle State Management:** During the MVVM transition, I had to ensure that asynchronous background tasks correctly observed the Android Activity lifecycle. Unmanaged background operations can trigger memory leaks or app crashes during configuration changes, such as device rotation. I resolved this by leveraging ViewModel scopes and `LiveData` observers to handle UI state updates safely.
* **Schema Mapping:** Transitioning legacy SQLite tables into Room `@Entity` models required careful alignment of data types, primary keys, and auto-generation strategies to ensure clean mapping without data corruption or runtime exceptions.

---

## Technical Source Files

| Component | Description |
| :--- | :--- |
| **Architecture Pattern** | MVVM Pattern with `ViewModel` and `LiveData` Observers |
| **Data Repository** | Single Source of Truth managing asynchronous `ExecutorService` tasks |
| **UI Components** | Refactored `MainActivity` & `DashboardActivity` adhering to clean UI/UX guidelines |

## Artifact Downloads & Source Code

**Complete Enhanced Package:** [`ElijahsWeightTrackerApp_EnhancedAlgorithms.zip`](../assets/docs/ElijahsWeightTrackerApp_EnhancedAlgorithms.zip)
