# Ingestion Plan

Our goal is to create a RAG Intelligence System for the Beloit Student Handbook and Beloit Course Catalog, our corpus will be made up of exclusively these two documents.

## Student Handbook
The Student Handbook will first be split based on the contents in pages 2-4. The handbook is split into four sections, each with their own subsections, each subsection will be one chunk, if that chunk is over our word limit (250 or 750) that chunk will be split into smaller chunks.

## Beloit Course Catalog
The Course Catalog will first be split based on the table of contents on page3 3. The course catalog is split into six sections, with most having their own subsections, each subsection will be one chunk, if that chunk is over our word limit (250 or 750) that chunk will be split into smaller chunks.

## Verification and Issues
### Single Pages with Multiple Sections
Many pages, (The Course Catalog Chapter 5 for example) fit multiple chunks into one page, this gives repeated pages when chunking our documents. This leads to a few chunks having the exact same pages and repeated data. A solution is deleting repeated pages, which can be fixed in the chunking or uploading process.

### Chunk Compare
Comparing chunk sizes for 250 and 750 is based on the results of the top 3 chunks from our first 3 questions:
#### Questions
Question 1: What weapons are prohibited on campus?
Question 2: Can I drink in any academic buildings ?
Question 3: Can I use spraychalk on beloit campus/sidewalks?

#### Results - 750 Word Chunks
##### Question 1
1st Chunk - Score 0.234  |  Student Handbook Policies and Regulations O  |  Correct? - Yes

2nd Chunk - Score 0.234  |  Student Handbook Judicial Processes  |  Correct? - Yes

3rd Chunk score 0.183  |  Student Handbook Policies and Regulations O  |  Correct? - Yes

##### Question 2
1st Chunk - score 0.216  |  Student Handbook Policies and Regulations B1  |  Correct? - Yes

2nd Chunk - score 0.181  |  Student Handbook Policies and Regulations B1  |  Correct? - No

3rd Chunk - score 0.173  |  Student Handbook Policies and Regulations B1  |  Correct? - No

##### Question 3
1st Chunk - score 0.202  |  Student Handbook Policies and Regulations D3  |  Correct? - Yes

2nd Chunk - score 0.202  |  Student Handbook Policies and Regulations D2  |  Correct? - Yes

3rd Chunk - score 0.094  |  Student Handbook Policies and Regulations D3  |  Correct? - No

#### Results - 250 Word Chunks
##### Question 1
1st Chunk - score 0.303  |  Student Handbook Policies and Regulations N  |  Correct? - Yes

2nd Chunk - score 0.232  |  Student Handbook Judicial Processes  |  Correct? - Yes

3rd Chunk score 0.232  |  Student Handbook Policies and Regulations O  |  Correct? - Yes

##### Question 2
1st Chunk - score 0.173  |  Student Handbook Policies and Regulations E  |  Correct? - No

2nd Chunk - score 0.166  |  Student Handbook Policies and Regulations B1  |  Correct? - No

3rd Chunk - score 0.164  |  Student Handbook Policies and Regulations B1  |  Correct? - No

##### Question 3
1st Chunk - score 0.204  |  Student Handbook Policies and Regulations D2 |  Correct? - Yes

2nd Chunk - score 0.204  |  Student Handbook Policies and Regulations D3  |  Correct? - Yes

3rd Chunk - score 0.176  |  Student Handbook Policies and Regulations H  |  Correct? - No

### Overall Analysis
750 word chunks did overall better in these three questions, for question 1 and 3 they returned the relevant chunks with similar scores, but in question 2, the 250 chunking got it completely wrong. Chunking by 750 also had larger differences with the irrelevant paragraphs, meaning it will give incorrect paragraphs at a lower rate than chunking by 250. As a result, we will move on with the project by chunking with 750 words.
