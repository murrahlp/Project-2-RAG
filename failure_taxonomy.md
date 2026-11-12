Failure Taxonomy: We had 7 questions fail out of 30 of our evaulation "gold" questions. 

Question 5: Who are the computer science major/minor faculty ?

Question 6: What is the academic honesty policy on campus?

Question 9: What are the four principles of Restorative Justice?

Question 12: How to get Departmental Honors in Data Science & Data Analytics?

Question 14: What are the requirements for Japanese Minor?

Question 16: What are all the Business and Economic majors?

Question 20: Who are the Critical Identity Studies Faculty?


These all catagorize into two different catagories : Right Document, Wrong chunk and Search Failed

In the right document, wrong chunk questions the system was able to identify the right area and got the correct document we were looking for but the way we did the embedding and chunking of the data it wasnt able to pick out the right chunk in that same document. In many cases they were just next to the right data. 

In the search failed the system did not pick the right documents at all. 

Right Document, Wrong Chunk : Question 5, Question 6, Question 12, Question 14, Question 20

One worked Example: Question 5: Who are the computer science major/minor faculty ?

Answer: I am sorry, but the provided context does not contain information about who the computer science major or minor faculty are.

Gold Answer: Eyad Haj Said, Katherine Harris, Sohaib Kiani, Tom Stojsavljevic, Ben Stucky, Robin Zebrowski
Document ID: cc_chapter2_computer_science



Which documents came back: 

[1] score 0.218  |  Course Catalog Majors & Minors Chapter 2 Computer Science  |  pdf pages 48-51  |  cc_chapter2_computer_science__01
Introductory courses prepare a student to do such problem-solving in any domain. Students pursuing a
computer science major learn more advanced techniques for such modeling and also focus on models
specifc to computer science and computer technology. Upper-level elective courses prepare students for
graduate-level study and for vocations in various computer felds. 

[2] score 0.218  |  Course Catalog Majors & Minors Chapter 2 Cognitave Science  |  pdf pages 45-48  |  cc_chapter2_cognitave_science__03
Introductory courses prepare a student to do such problem-solving in any domain. Students pursuing a
computer science major learn more advanced techniques for such modeling and also focus on models
specifc to computer science and computer technology. Upper-level elective courses prepare students for
graduate-level study and for vocations in various computer felds. 

[3] score 0.204  |  Course Catalog Majors & Minors Chapter 2 Computer Science  |  pdf pages 48-51  |  cc_chapter2_computer_science__01
Advanced Placement Credit for Computer Science
Supplemental to the college’s general policies of Advanced Placement and Credit, the department of
mathematics and computer science may grant additional placement (based on advising by faculty). The
department does not grant placement for computer programming alone but for mastery of concepts and
techniques of computer science.

It belongs in this catagory because we asked for the expected document to be cc_chapter2_computer_science and it got that exact document but the way we did the chunking it was not able to get the faculty list from this section and was in none of the chunks provided. 


Search Failed: Question 9, Question 16

Question 16: What are all the Business and Economic majors?

Answer: I am sorry, but the provided context does not contain information about all the Business and Economic majors.

Gold Answer: Business Management Major (11 units) Economics Major (13 units) Quantitative Economics Major (13 units) Entrepreneurship Minor (6 units) Finance Minor (6 units) Marketing Minor (6 units) Sports Management Minor (6 units) Finance Dual Degree Program
Document ID: cc_chapter2_index



[1] score 0.259  |  Course Catalog Majors & Minors Chapter 2 Data Science & Analytics  |  pdf pages 56-59  |  cc_chapter2_data_science_&_analytics__03
DSDA 395. Teaching Assistant (.25 - .5). Student assists faculty in classroom instruction. Graded credit/no
credit.
Economics & Business
The Samuel J. Campbell Department of Economics and Business curriculum provides students with a solid
understanding of fundamental economic and business principles, how the global market economy works,
how key institutions of a modern economic system operate, and how to apply these understandings to
business management, public policy, and their own lives. The department emphasizes the development of
quantitative and analytical skills and career readiness. 

[2] score 0.259  |  Course Catalog Majors & Minors Chapter 2 Economics & Business  |  pdf pages 59-66  |  cc_chapter2_economics_&_business__01
DSDA 395. Teaching Assistant (.25 - .5). Student assists faculty in classroom instruction. Graded credit/no
credit.
Economics & Business
The Samuel J. Campbell Department of Economics and Business curriculum provides students with a solid
understanding of fundamental economic and business principles, how the global market economy works,
how key institutions of a modern economic system operate, and how to apply these understandings to
business management, public policy, and their own lives. The department emphasizes the development of
quantitative and analytical skills and career readiness. 

[3] score 0.237  |  Course Catalog Majors & Minors Chapter 2 Economics & Business  |  pdf pages 59-66  |  cc_chapter2_economics_&_business__02
Economics & Business Courses
BUSN 206. International Business and Asian Economies (1). In the past few decades, economies of South
and East Asia have rapidly integrated into the global economy and achieved phenomenal economic success.
How did they do it? In the frst part of the course, students examine these countries’ economic policies
and discuss lessons for other countries. In the second part of the course, against the macroeconomic
background provided in part I, students learn to identify and evaluate business strategies that are relevant
for international business expansion to a diverse and rapidly globalizing Asia. Ofered once every other year.
Prerequisite: Economics 199.

This belongs in search failed since it did not get the expected document were this question was in the course catalog making it impossible to answer from the start. 
