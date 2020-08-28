# Quantum Computing Course Data
This repository holds data on US schools and courses related to quantum computing and information. There are three TSV files holding data on different aspects. See sections below for details

## Schools
The `schools.tsv` file holds data on institutions that have taught a quantum computing or quantum information course since 2018. Specific fields are as follows:
|Field           |Contents                   |
|----------------|---------------------------|
|ID|School id to distinguish without name. Referenced in `courses.tsv`|
|School|Name of the institution|
|State|State location of the school|
|Level|Level of students taught quantum computing and information. UG for undergraduates, GR for graduates, and PhD for doctoral students. May list multiple values; values are composite of all courses (e.g. a school may teach a course to undergrads and a second to graduates, or both in one combined class)|
|Departments|List of departments which teach quantum computing at the school. Comma seperated list standardized as MATH, CS, PHYS, ENG (engineering), or Other|
|Special Topic|Whether the school offers course as special topic. Yes if only special topics, No if no special topics, and Yes, No if multiple courses with different offering styles|

## Courses
The `courses.tsv` file holds data on all courses in quantum computing or quantum information that could be identified as being taught since 2018 or an unconfirmed date. Specific fields are as follows:
|Field           |Contents                   |
|----------------|---------------------------|
|School ID|Identifier for school that teaches course - foreign key to `schools.tsv`|
|Course ID|Identifier for course according to school (ex. CS 001)|
|Course Name|Title of course| 
|Departments|List of departments which teach course - may be multiple if cross-listed. Comma seperated list standardized as MATH, CS, PHYS, ENG (engineering), or Other
|Term|Term in which the course was last offered, or blank if this cannot be confirmed|
|Year|Year in which the course was last offered, or blank if this cannot be confirmed|
|Level|Level of students taught in course. UG for undergraduates, GR for graduates, and PhD for doctoral students. May list multiple values if there are sibling/shared courses (e.g. CS 400/500)|
|Special Topic|Whether the course is offered as special topic|
|Description|Course description|
|Syllabus|Link to a syllabus if one can be found|
|Text IDs|Textbooks or lecture notes for the course. Comma seperated list of ids referencing textbooks/lecture notes in `texts.tsv`|
|PreReqs|List of prerequisites for the course. Comma seperated list of course titles with some standardization|
|Concepts|Comma seperated list of key terms referenced in the course description or syllabus if one is included. Some standarization of terms|

## Texts
The `texts.tsv` file holds data on all textbooks/lecture notes cited by courses in `courses.tsv` as required reading. Specific fields are as follows:
|Field           |Contents                   |
|----------------|---------------------------|
|School ID|Identifier for school that teaches course - foreign key to `schools.tsv`|
|Course ID|Identifier for course according to school (ex. CS 001)|
|Course Name|Title of course| 
|ID|Identifier for text; referenced by `courses.tsv`|
|Author|Author(s) of text|
|Title|Title of text|
|Link|Link to text, if one can be found|
|Notes|Any additional notes, such as whether source is a set of lecture notes and some additional details|

