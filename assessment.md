---
layout: default
---

[Back To Home](index.md)

# Assessment AI

While employed at Cosairus, I developed an API service using Django and spaCy which could be sent
text, which it would analyze and search in for sensitive medical information, such as mentions of
substance abuse and STDs. These findings would be reported back to the caller. I created it solo in
under two weeks with no prior knowledge of Django or spaCy.

The service was then rewritten by another developer as a headless CLI application that processes a
set of files. After this was completed the project was handed back to me and I implemented several
additional features. These include accessing files from an API, extracting text automatically from
PDF files, storing results to a SQL database, and creating and uploading an annotated version of
the PDF file with the sensitive information highlighted for review.

I later enhanced the AI to detect comingled records from multiple patients and release
authorization forms.
