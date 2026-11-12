# Failure Taxonomy

Out of 30 of our evaluation "gold" questions, **7 questions failed**. 

### The Failed Questions
* **Question 5:** Who are the computer science major/minor faculty?
* **Question 6:** What is the academic honesty policy on campus?
* **Question 9:** What are the four principles of Restorative Justice?
* **Question 12:** How to get Departmental Honors in Data Science & Data Analytics?
* **Question 14:** What are the requirements for Japanese Minor?
* **Question 16:** What are all the Business and Economic majors?
* **Question 20:** Who are the Critical Identity Studies Faculty?

---

## Failure Categories

These failed questions categorize into two distinct issues:

1. **Right Document, Wrong Chunk:** Question 5, Question 6, Question 12, Question 14, Question 20
2. **Search Failed:** Question 9, Question 16

### 1. Right Document, Wrong Chunk
In these cases, the system successfully identified the right area and retrieved the correct document. However, due to the way the data was embedded and chunked, it wasn't able to pick out the exact right chunk containing the answer. In many cases, the retrieved chunks were immediately adjacent to the correct data.

### 2. Search Failed
In these cases, the system failed to retrieve the right documents at all.

---

## Worked Examples

### Example 1: Right Document, Wrong Chunk
* **Question 5:** Who are the computer science major/minor faculty?
* **Answer:** I am sorry, but the provided context does not contain information about who the computer science major or minor faculty are.
* **Gold Answer:** Eyad Haj Said, Katherine Harris, Sohaib Kiani, Tom Stojsavljevic, Ben Stucky, Robin Zebrowski
* **Expected Document ID:** `cc_chapter2_computer_science`

**Documents Retrieved:**
> **[1] Score: 0.218 | `cc_chapter2_computer_science__01` (PDF Pages 48-51)**
> Introductory courses prepare a student to do such problem-solving in any domain. Students pursuing a computer science major learn more advanced techniques for such modeling and also focus on models specifc to computer science and computer technology. Upper-level elective courses prepare students for graduate-level study and for vocations in various computer felds.

> **[2] Score: 0.218 | `cc_chapter2_cognitave_science__03` (PDF Pages 45-48)**
> Introductory courses prepare a student to do such problem-solving in any domain. Students pursuing a computer science major learn more advanced techniques for such modeling and also focus on models specifc to computer science and computer technology. Upper-level elective courses prepare students for graduate-level study and for vocations in various computer felds.

> **[3] Score: 0.204 | `cc_chapter2_computer_science__01` (PDF Pages 48-51)**
> **Advanced Placement Credit for Computer Science:** Supplemental to the college’s general policies of Advanced Placement and Credit, the department of mathematics and computer science may grant additional placement (based on advising by faculty). The department does not grant placement for computer programming alone but for mastery of concepts and techniques of computer science.

**Diagnosis:** 
This belongs in this category because we expected the document `cc_chapter2_computer_science` and the system retrieved that exact document. However, due to the chunking strategy, it was not able to isolate the faculty list from this section, meaning the correct answer was in none of the provided chunks.

---

### Example 2: Search Failed
* **Question 16:** What are all the Business and Economic majors?
* **Answer:** I am sorry, but the provided context does not contain information about all the Business and Economic majors.
* **Gold Answer:** Business Management Major (11 units), Economics Major (13 units), Quantitative Economics Major (13 units), Entrepreneurship Minor (6 units), Finance Minor (6 units), Marketing Minor (6 units), Sports Management Minor (6 units), Finance Dual Degree Program.
* **Expected Document ID:** `cc_chapter2_index`

**Documents Retrieved:**
> **[1] Score: 0.259 | `cc_chapter2_data_science_&_analytics__03` (PDF Pages 56-59)**
> DSDA 395. Teaching Assistant (.25 - .5). Student assists faculty in classroom instruction. Graded credit/no credit.
> 
> **Economics & Business:** The Samuel J. Campbell Department of Economics and Business curriculum provides students with a solid understanding of fundamental economic and business principles... The department emphasizes the development of quantitative and analytical skills and career readiness.

> **[2] Score: 0.259 | `cc_chapter2_economics_&_business__01` (PDF Pages 59-66)**
> DSDA 395. Teaching Assistant (.25 - .5). Student assists faculty in classroom instruction. Graded credit/no credit.
> 
> **Economics & Business:** The Samuel J. Campbell Department of Economics and Business curriculum provides students with a solid understanding of fundamental economic and business principles...

> **[3] Score: 0.237 | `cc_chapter2_economics_&_business__02` (PDF Pages 59-66)**
> **Economics & Business Courses:** BUSN 206. International Business and Asian Economies (1). In the past few decades, economies of South and East Asia have rapidly integrated into the global economy and achieved phenomenal economic success... Ofered once every other year. Prerequisite: Economics 199.

**Diagnosis:** 
This belongs in the search failed category because the system entirely missed the expected document (`cc_chapter2_index`) from the course catalog, making it impossible for the model to answer the question from the start.
