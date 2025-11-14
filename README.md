# CourseKata Learning Analytics — DataFest 2024

**Language:** R (original code no longer available)  
**Libraries:** Used standard data-cleaning and visualization tools (tidyverse, etc.)  
**Dataset:** CourseKata Learnosity Question-Level Data (Statistics & Data Science ABC Book)  
**Group Project:** Completed as part of a collaborative team effort  
**Award:** *Best Visualizations* — DataFest 2024

---

## Objective

1. Analyze how **performance across Learnosity question types** relates to overall student success  
2. Identify question types that stronger and weaker students perform differently on  
3. Provide **data-driven recommendations** to CourseKata to improve statistical learning  

---

## Data Description

- Includes question-level responses across multiple chapters  
- Covers only the **Statistics & Data Science (ABC) book** to simplify analysis  

**Key Variables:**
- `student_id` — unique identifier for each learner  
- `question_type` — (Multiple Choice, Long Text, Ordering, Short Text, Choice Matrix, Association)  
- `EOC_correctness` — end-of-chapter correctness  
- `Chapter` — location of the question  
- Additional metadata on student performance  

**Data cleaning and preparation steps:**
1. Merged all CSV files by `student_id` to create a unified dataset per student  
2. Filtered the dataset to include only the ABC textbook content  
3. Calculated each student’s **overall EOC average across chapters**  
4. Sorted students into **four percentile groups** (0–25%, 25–50%, 50–75%, 75–100%)  
5. Computed average EOC correctness by question type within each percentile group  
6. Created tables and visualizations comparing distributions and performance patterns  

---

## Exploratory Data Analysis

### Distribution of Question Types per Chapter  
**Observations:**  
- Multiple choice questions dominate across all chapters  
- Long text responses are the second most common  
- Ordering problems appear in only one chapter  

### Distribution of EOC Values by Percentile Group  
**Observations:**  
- Middle groups (25–50%, 50–75%) show the least score variation  
- 0–25% group has the **highest variability**  
- 75–100% group has the **most outliers**  

### Percentile vs. Total Learnosity EOC  
**Observations:**  
- Clear **positive correlation** between percentile rank and total EOC  
- Small performance increase visible even within the 25th percentile  

*Visuals:*  
- Distribution by question type  
- EOC distribution by percentile  
- Percentile vs. total EOC correlation plot  

---

## Question-Type Insights

### Choice Matrix Questions  
- Minimal differences between percentile groups  
- Not a strong discriminator of student success  

### Multiple Choice Questions  
- Strong **positive linear correlation** with percentile  
- Sharpest gains appear in 0–25% and 75–100% groups  
- Middle groups show flatter performance  

### Short Text Responses  
- Mild positive relationship with percentile  
- Data highly scattered → difficult to predict consistency  

### Association Questions  
- Strong upward trend with percentile  
- High performers excel  
- Students perceive these as **time-intensive**, low-engagement, and low-value  

*Visuals:*  
- EOC-by-percentile plots for each question type  

---

## Student Feedback & Correlations with Pulse Checks

### Association Questions  
- Provide good evaluation of conceptual understanding  
- However, students find them frustrating and overly demanding  

**Recommendations:**  
- Reduce quantity in homework/practice  
- Use strategically as assessment tools  

### Short Text Questions  
- Weaker students complete fewer of them  
- Chapters with more short-text questions receive **more positive user feedback**  

**Recommendations:**  
- Increase number of short-text questions  
- Allow partial credit for explanations  
- Improve scaffolding to guide students naturally into these questions  

---

## Recommendations

- Fully integrate an **“I don’t know”** option to reduce student overwhelm  
- Some question types are poor predictors of student understanding → revise or replace  
- Rebalance question-type distributions across chapters  
- Reduce reliance on Association items for routine practice  
- Expand Short Text opportunities for formative assessment  

---

## Tools and Methods Used

- **R** for data cleaning, merging, and visualization *(original scripts no longer available)*  
- Percentile grouping for performance segmentation  
- Categorical analysis by question type  
- Visual exploration of EOC distributions  

---

**Author:** Mia Parker  
**Language:** R
