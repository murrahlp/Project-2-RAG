# Ingestion Plan

Our goal is to create a RAG Intelligence System for the Beloit Student Handbook and Beloit Course Catalog, our corpus will be made up of exclusively these two documents.

## Student Handbook
The Student Handbook will first be split based on the contents in pages 2-4. The handbook is split into four sections, each with their own subsections, each subsection will be one chunk, if that chunk is over our word limit (250 or 750) that chunk will be split into smaller chunks.

## Beloit Course Catalog
The Course Catalog will first be split based on the table of contents on page3 3. The course catalog is split into six sections, with most having their own subsections, each subsection will be one chunk, if that chunk is over our word limit (250 or 750) that chunk will be split into smaller chunks.

## Verification and Issues
### Single Pages with Multiple Sections
Many pages, (The Course Catalog Chapter 5 for example) fit multiple chunks into one page, this gives repeated pages when chunking our documents. This leads to a few chunks having the exact same pages and repeated data. A solution is deleting repeated pages, which can be fixed in the chunking or uploading process.
