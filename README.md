# Project-2-RAG
## Overview
The repository is a RAG Intelligence system designed for Beloit College's Student Handbook and Course Catalog. This system is able to answer relevant questions about both documents as well has refuse to answer when the question is unrelated to any content in those documents.
## How to Run
Everything is ran through pipeline.ipynb, the documents are scanned as pdf's and split according to documents.csv, which separates the documents based on their indexes and page numbers. These are exported as txt documents and are then split into chunks of a chosen word size (750, 450, 150) and embedded. Using Google Clouds Vertex, questions from test_questions.md and evaluation_set.md are given and answered, results of these questions can be seen in failure_taxonomy.md and results.md.
