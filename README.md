# Student Performance Analysis 🎓📊

## Project Description
In the modern high school education system, assessing student performance must go beyond merely reading grades on a transcript. The **Student Performance Analysis** project was developed to apply a data-driven mindset to the academic sector. It aims to help school administrators transition from simply "reporting grades" to "diagnosing and taking actionable steps."

The core objective of this project is to provide the Board of Principals, Heads of Departments, and Homeroom Teachers with a comprehensive visual tool to monitor academic health, identify bottlenecks in the curriculum early, and implement timely interventions to improve the overall score and pass rate.

## Business Questions
This project is designed to address the following key business problems:
1. **Seasonality Impact:** How do different semesters affect student performance? Which grade level is struggling the most?
2. **Bottlenecks:** Which subjects and assessment types have the highest failure rates?
3. **The Weight Paradox:** Does high-pressure assessment (high weight) negatively correlate with student performance?
4. **Teaching Quality:** Is there a correlation between a teacher's years of experience and the academic outcomes of their classes?
5. **Proactive Intervention:** How can the school quickly identify "at-risk" students who need urgent academic support?

## Dataset
The dataset simulates a High School Learning Management System (LMS), containing granular records of students, their assessment history across academic years, and faculty information. The Data Model utilizes a **Star Schema** approach:
* **Fact Table:** `FactPerformance` (Contains thousands of assessment records, scores, and weightings).
* **Dimension Tables:** `DimStudent`, `DimTeacher`, `DimSubject`, `DimAssessment`, `DimCalendar (DimDate)`.
<img width="1699" height="480" alt="image" src="https://github.com/user-attachments/assets/0f0ecbbf-4a3e-47f5-8e65-586cf1021eca" />
<img width="742" height="689" alt="image" src="https://github.com/user-attachments/assets/6ba7a598-38c5-4e01-9d97-08ebd7eb8258" />

## Analysis Approach
The dashboard employs a top-down analytical funnel, drilling down from a macro to a micro level across 6 specialized tabs:
1. **Overview:** A holistic view of school performance, pass rates, and semester trends.
2. **Performance Trend:** Deep dive into subject-level score fluctuations across Fall, Spring, and Summer semesters.
3. **Subject Analysis:** Comparing subject difficulty, pass/fail ratios, and perfect score distributions.
4. **Teacher Analysis:** Evaluating grading consistency and the impact of teaching experience.
5. **Assessment Analysis:** Analyzing the structural effectiveness of exams and the correlation between assessment weight and actual scores.
6. **Student Analysis:** Granular profiling of student grade distributions to build an Early Warning System (EWS).

## Key Metrics
* **Average Score:** The mean score achieved by students on a single, specific assessment.
* **Weighted Average:** The overall final grade for a subject, calculated by applying predefined weightings to various assessment types (e.g., Formative vs. Summative) within that subject.
* **Student Pass Rate:** The percentage of students who successfully meet the passing criteria for an entire course or subject.
* **Unique Assessments:** The total count of distinct, individual exams or assessment types administered across the curriculum.
* **Lowest Performing Subject:** The subject recording the lowest overall weighted average score, highlighting an area that requires urgent academic intervention.
* **Highest Performing Subject:** The subject with the highest overall weighted average score, indicating strong student comprehension and effective curriculum design.
* **Most Perfect Scores:** The subject that records the highest frequency of students achieving the maximum possible score (100%).
* **Avg. Years of Experience:** The mean teaching tenure (measured in years) of the faculty members involved in the evaluation.
* **Total Assessments Taken:** The cumulative volume of individual test submissions completed and graded across the students.
* **Assessment Pass Rate:** The percentage of students who successfully pass a specific individual exam or project (distinct from the overall course pass rate).

## Key Insights
* **The "Summer Slump":** There is a distinct, recurring drop in overall performance during the Summer semester (dropping to 65.9 - 67.5). The root cause points to the heavy concentration of high-pressure Summative exams combined with difficult STEM subjects (Math, Science) in a shortened timeframe.
<img width="776" height="350" alt="image" src="https://github.com/user-attachments/assets/77f93604-b4dc-4ee2-8361-5a714999b145" />

* **The Year 3 Bottleneck & Year 4 Paradox:** Year 3 (Grade 11) students record the lowest assessment pass rate (84.21%), while Year 4 (Grade 12) enjoys a near-perfect rate (99.69%). However, despite having the highest pass rate, Year 4 students are completely absent from the Top 10 Highest Performers list, suggesting they might be strategically aiming for "just passing" grades to save energy for university entrance exams.
<img width="435" height="319" alt="image" src="https://github.com/user-attachments/assets/3553a613-28b4-4d66-825d-862fe5638f28" />

<img width="501" height="303" alt="image" src="https://github.com/user-attachments/assets/8f9eb764-ed4c-4751-ae4d-fda3923bc714" />

* **Highly Standardized Grading:** The Pass/Fail rate across all 5 teachers converges perfectly at 78.66% (Passed) and 21.34% (Failed). Furthermore, the score variance between the most and least experienced teachers is practically negligible (0.11 points), indicating a highly standardized and potentially forced grading curve.
<img width="1129" height="300" alt="image" src="https://github.com/user-attachments/assets/da1d599e-06e8-4840-b261-90d69c323d4f" />

* **The Assessment Weight Paradox:** A scatter plot correlation reveals that assessments with the highest weight (e.g., Projects at 30%) actually yield the highest average scores (74 points). Conversely, "Quarter" exams act as the biggest bottleneck, recording an 18.28% failure rate.
<img width="641" height="371" alt="image" src="https://github.com/user-attachments/assets/39f21a62-9ae9-42fa-a032-c51559980b6c" />
<img width="1129" height="311" alt="image" src="https://github.com/user-attachments/assets/4a422f64-fde0-4be2-95fd-8762eddc61ca" />

* **Polarized Grade Distribution:** A striking 80% of students are clustered securely in the 'B' tier, while exactly 20% are trapped in the 'D' tier. There are absolutely zero students in the 'A' or 'C' bands, which highlights a severe polarization in student outcomes.
<img width="558" height="413" alt="image" src="https://github.com/user-attachments/assets/e7c2a581-6d8c-4fe3-b8c1-56f26482ced2" />

## Strategic Recommendations
1. **Summer Semester Restructuring:** Avoid scheduling high-stakes Summative assessments during the Summer. Implement mandatory tutoring sessions for STEM subjects at the beginning of the term to prevent widespread drop-offs.
2. **Targeted Grade Interventions:** Investigate the Year 3 curriculum to identify "killer" subjects and provide targeted support to build a foundation for their senior year. For Year 4, reassess the grading rubrics to ensure assessments have enough differentiation to challenge top achievers.
3. **Quarter Exam Review:** The Academic Department must review the difficulty and curriculum alignment of Quarter exams. Meanwhile, the school should scale up Project-based assessments, as data shows students perform significantly better under this practical format.
4. **Activate an Early Warning System (EWS):** Export the list of students in the 'D' grade band (60-69 points) directly from the Dashboard to Homeroom Teachers. Mandate 1-on-1 counseling sessions immediately before the next major exam cycle to rescue these at-risk students.

## Tools & Techniques Used
* **Excel**
* **Power BI**

## Author
**Nguyen Huu Thien**
