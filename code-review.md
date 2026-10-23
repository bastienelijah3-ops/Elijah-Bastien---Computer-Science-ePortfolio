# Code Review

[Back to Home](../README.md)

---

## Presentation Walkthrough

Below is my code review video walkthrough covering the initial state of the artifact, code analysis for planned enhancements, and alignment with course outcomes.

> **Watch Code Review Video:** [Link to Code Review Presentation (YouTube)](https://youtu.be/9D3v4A9D-PA)

---

## Executive Summary & Walkthrough Outline

### 1. Existing Functionality
* **Core Architecture:** Built as a native Android application in Java using Android Studio.
* **Features:** Provides secure user authentication, persistent account registration, and a dynamic dashboard to record and track daily body weight measurements against target goals.
* **Initial State:** Relied on legacy layout structures and basic UI threads before architectural refactoring.

### 2. Targeted Code Analysis & Areas for Improvement
* **Architecture & Structure:** Identified tight coupling between UI controllers and data layers, necessitating a transition to the MVVM (Model-View-ViewModel) architectural pattern.
* **Security & Permissions:** Audited the application manifest and successfully identified legacy, unused permissions (such as SMS requests) to tighten user data privacy.
* **Robustness & Testing:** Diagnosed runtime `IllegalArgumentException` layout inflation failures caused by legacy theme inheritance conflicts with `MaterialCardView`.

### 3. Planned Enhancements & Course Outcome Alignment
* **Software Design & Engineering:** Upgraded UI themes to `Theme.MaterialComponents.DayNight.DarkActionBar` and decoupled data handling to ensure lifecycle resilience during configuration changes (screen rotations).
* **Algorithms & Data Structures:** Engineered O(1) background thread execution using `ExecutorService` and structured DAO query ordering (`ORDER BY date DESC`) for O(n \log n) chronological data presentation.
* **Databases:** Implemented Room SQLite persistence with indexed relational tables (`UserEntity` and `WeightEntry`) and configured safe schema migration fallback strategies (`fallbackToDestructiveMigration()`).
