## Artifact Narrative

### 1. Artifact Description
The artifact is a native Android application written in Java designed to track daily weight metrics against personal goals, created in 2026 as part of my computer science coursework.

### 2. Justification & Software Development Showcase
I selected this artifact for my ePortfolio because it demonstrates practical software engineering, UI design, and local data persistence using modern Android Architecture Components. For the Algorithms and Data Structures enhancement, the application showcases structured data handling through a Room SQLite database, leveraging DAO queries to perform efficient data retrieval and algorithmic calculations such as chronological sorting and goal progress tracking across user entries.

The artifact was significantly improved by refactoring the backend database architecture, implementing an MVVM pattern with LiveData observers, and fixing a critical IllegalArgumentException XML inflation crash by migrating the application theme to Theme.MaterialComponents.DayNight.DarkActionBar.

### 3. Course Outcomes Alignment
Through these enhancements, I successfully met my Module One course outcome goals, specifically in evaluating and implementing optimal data structures and robust software design patterns to ensure scalability and reliability. My outcome coverage plans remain aligned with demonstrating comprehensive proficiency in software design and algorithms.

### 4. Reflection, Learnings & Challenges
Reflecting on the enhancement process, I gained valuable hands-on experience troubleshooting Android theme inheritance conflicts and managing activity lifecycles. The primary challenge was diagnosing the root cause of XML component inflation failures while maintaining UI state during configuration changes, which I overcame by decoupling database logic from the UI layer and enforcing strict Material Design theme dependencies.

---


### Primary Algorithmic Implementation Files

| Component | Description |
| :--- | :--- |
| **Chronological Query Sorting** | Room DAO executing sorted SQL queries (`WeightDao.java`) |
| **Asynchronous Execution** | Background thread management (`WeightRepository.java`) |
| **Reactive State Binding** | LiveData observers managing UI updates (`WeightViewModel.java`) |

## Artifact Source Code & Downloads

* **Complete Enhanced Application Package:** [`ElijahsWeightTrackerApp_EnhancedAlgorithms.zip`](../assets/docs/ElijahsWeightTrackerApp_EnhancedAlgorithms.zip?raw=true))
