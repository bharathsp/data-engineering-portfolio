A **Factless Fact Table** is a type of fact table in a **data warehouse** that **does not contain any measurable facts (numeric values)** but is still useful for capturing the **relationships or events between dimension tables**.

---

### 🧱 Key Characteristics of Factless Fact Tables:

| Feature                 | Description                                                             |
| ----------------------- | ----------------------------------------------------------------------- |
| **No measurable facts** | Contains only **foreign keys** to dimension tables, no numeric metrics. |
| **Captures events**     | Useful for tracking the **occurrence of events** or **conditions**.     |
| **Supports counting**   | Enables answering “how many” or “how often” questions using `COUNT(*)`. |

---

### 📚 Example 1: Student Course Enrollment

\| 📘 Table: `EnrollmentFact` (Factless Fact Table) |
\|--------------|--------------|
\| StudentID (FK) | CourseID (FK) |
\| SemesterID (FK) | EnrollmentDate |

Here, there’s **no measurable amount** like fees or grades. But this table helps answer:

* How many students enrolled in each course?
* Which students enrolled in more than 3 courses?
* What is the total number of enrollments this semester?

---

### 📚 Example 2: Store Promotions Participation

\| 📘 Table: `PromotionParticipationFact` |
\|------------|-------------|
\| StoreID (FK) | PromotionID (FK) |
\| DateID (FK)  |

No numeric values, but you can still ask:

* Which stores participated in which promotions?
* How many stores joined the "Festival Sale 2024"?

---

### 🔍 Types of Factless Fact Tables

1. **Event Tracking** – Captures something **that happened**, like class attendance, logins, product views.
2. **Coverage/Eligibility** – Captures something **that could happen**, like which products **could** be eligible for a discount or which employees **are** scheduled for training.

---

### ✅ Use Cases

* Many-to-many relationships between dimensions (e.g., students and courses, doctors and patients).
* Recording participation, eligibility, and other **non-quantifiable events**.
* Simplifying complex queries by enabling **count-based analysis**.

---

### 🔁 Compared To Regular Fact Table

| Feature       | Regular Fact Table        | Factless Fact Table             |
| ------------- | ------------------------- | ------------------------------- |
| Has Measures? | Yes (e.g., sales, profit) | No                              |
| Used For      | Aggregating measures      | Counting events or relations    |
| Examples      | SalesFact, OrdersFact     | AttendanceFact, EligibilityFact |
