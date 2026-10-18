# Category Enhancement 3: Databases

[Back to Home](../README.md)

---

## Artifact Narrative

### 1. Artifact Description
The artifact enhanced for this milestone is a native Android Weight Tracking Application, developed in Java using Android Studio and originally created in 2026 as part of my computer science coursework in mobile applications. The application provides a complete daily metric tracking system where users can register an account, securely authenticate, log daily body weight measurements, set target weight goals, and track their progress over time through an interactive dashboard interface.

### 2. Justification & Software Development Showcase
I selected this artifact for my ePortfolio because it demonstrates core software engineering principles, local data persistence, and modern reactive architecture on the Android platform. The database components specifically showcase my proficiency in designing relational schemas (`UserEntity` and `WeightEntry`), implementing Data Access Objects (`UserDao` and `WeightDao`), and managing asynchronous database transactions off the main thread using an `ExecutorService`.

The artifact was significantly improved by refactoring the backend persistence tier to use Room SQLite, implementing an MVVM pattern with `LiveData` observers to handle UI data binding, resolving runtime database migration issues using `fallbackToDestructiveMigration()`, and updating application theme dependencies to eliminate XML component inflation crashes.

### 3. Course Outcomes Alignment
Through these enhancements, I successfully met the course outcomes planned in Module One, specifically in designing, evaluating, and refactoring industry standard database solutions to ensure data integrity and system responsiveness. Managing asynchronous queries ensured that database operations never block the main UI thread, while Room ORM integration standardized model to database mapping. My outcome coverage plans remain fully aligned with demonstrating comprehensive database design, local data lifecycle management, and solid mobile architecture principles.

### 4. Reflection, Learnings & Challenges
I gained deeper practical insight into local SQLite database management, reactive state observation, and Android activity lifecycles. The primary technical challenges involved diagnosing runtime schema migration errors during entity updates and fixing theme conflicts between AppCompat and Material Components (`MaterialCardView`). I overcame these hurdles by configuring explicit migration strategies in `AppDatabase`, refactoring data access method signatures across the DAO and repository layers, and aligning manifest theme configurations to ensure seamless layout rendering across screen rotations and app state resets.

---


### Primary Database Implementation Files

| Component | Description |
| :--- | :--- |
| **Database Instance** | Room SQLite Database builder and migration strategy (`AppDatabase.java`) |
| **User DAO** | Data Access Object for user accounts and goal records (`UserDao.java`) |
| **Weight DAO** | Data Access Object for historical entries and queries (`WeightDao.java`) |
| **Relational Schemas** | Entity mappings for persistent local data (`UserEntity.java` & `WeightEntry.java`) |

## Artifact Source Code & Downloads

* **Complete Enhanced Application Package:** [`ElijahsWeightTrackerApp_EnhancedDatabases.zip`](../assets/docs/ElijahsWeightTrackerApp_EnhancedDatabases.zip?raw=true))
