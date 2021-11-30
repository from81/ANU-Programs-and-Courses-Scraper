# About

# Note

ANU search API Endpoints

```sh
curl --request GET -H "Accept: application/json" <url> > output.json 

# Class search
https://programsandcourses.anu.edu.au/data/CourseSearch/GetCourses\?AppliedFilter\=FilterByCourses\&Source\=\&ShowAll\=true\&PageIndex\=0\&MaxPageSize\=1000\&PageSize\=Infinity\&SortColumn\=\&SortDirection\=\&InitailSearchRequestedFromExternalPage\=false\&SearchText\=\&SelectedYear\=2020\&Careers%5B0%5D\=\&Careers%5B1%5D\=Postgraduate\&Careers%5B2%5D\=\&Careers%5B3%5D\=\&Sessions%5B0%5D\=\&Sessions%5B1%5D\=First+Semester\&Sessions%5B2%5D\=\&Sessions%5B3%5D\=\&Sessions%5B4%5D\=Second+Semester\&Sessions%5B5%5D\=\&DegreeIdentifiers%5B0%5D\=\&DegreeIdentifiers%5B1%5D\=\&DegreeIdentifiers%5B2%5D\=\&FilterByMajors\=\&FilterByMinors\=\&FilterBySpecialisations\=\&CollegeName\=CECS\&ModeOfDelivery\=All+Modes

# Program search
https://programsandcourses.anu.edu.au/data/ProgramSearch/GetProgramsUnderGraduate?AppliedFilter=FilterByPrograms&Source=&ShowAll=True&PageIndex=0&MaxPageSize=10&PageSize=Infinity&SortColumn=&SortDirection=&InitailSearchRequestedFromExternalPage=false&SearchText=&SelectedYear=2022&Careers%5B0%5D=&Careers%5B1%5D=&Careers%5B2%5D=&Careers%5B3%5D=&Sessions%5B0%5D=&Sessions%5B1%5D=&Sessions%5B2%5D=&Sessions%5B3%5D=&Sessions%5B4%5D=&Sessions%5B5%5D=&DegreeIdentifiers%5B0%5D=&DegreeIdentifiers%5B1%5D=&DegreeIdentifiers%5B2%5D=&FilterByMajors=&FilterByMinors=&FilterBySpecialisations=&CollegeName=All+Colleges&ModeOfDelivery=All+Modes
https://programsandcourses.anu.edu.au/data/ProgramSearch/GetProgramsPostGraduate?AppliedFilter=FilterByPrograms&Source=&ShowAll=True&PageIndex=0&MaxPageSize=10&PageSize=Infinity&SortColumn=&SortDirection=&InitailSearchRequestedFromExternalPage=false&SearchText=&SelectedYear=2022&Careers%5B0%5D=&Careers%5B1%5D=&Careers%5B2%5D=&Careers%5B3%5D=&Sessions%5B0%5D=&Sessions%5B1%5D=&Sessions%5B2%5D=&Sessions%5B3%5D=&Sessions%5B4%5D=&Sessions%5B5%5D=&DegreeIdentifiers%5B0%5D=&DegreeIdentifiers%5B1%5D=&DegreeIdentifiers%5B2%5D=&FilterByMajors=&FilterByMinors=&FilterBySpecialisations=&CollegeName=All+Colleges&ModeOfDelivery=All+Modes

# Specializations / Majors / Minors
https://programsandcourses.anu.edu.au/data/SpecialisationSearch/GetSpecialisations?AppliedFilter=FilterByAllSpecializations&Source=&ShowAll=True&PageIndex=0&MaxPageSize=10&PageSize=Infinity&SortColumn=&SortDirection=&InitailSearchRequestedFromExternalPage=false&SearchText=&SelectedYear=2022&Careers%5B0%5D=&Careers%5B1%5D=&Careers%5B2%5D=&Careers%5B3%5D=&Sessions%5B0%5D=&Sessions%5B1%5D=&Sessions%5B2%5D=&Sessions%5B3%5D=&Sessions%5B4%5D=&Sessions%5B5%5D=&DegreeIdentifiers%5B0%5D=&DegreeIdentifiers%5B1%5D=&DegreeIdentifiers%5B2%5D=&FilterByMajors=&FilterByMinors=&FilterBySpecialisations=&CollegeName=All+Colleges&ModeOfDelivery=All+Modes
https://programsandcourses.anu.edu.au/data/MinorSearch/GetMinors?AppliedFilter=FilterByAllSpecializations&Source=&ShowAll=True&PageIndex=0&MaxPageSize=10&PageSize=Infinity&SortColumn=&SortDirection=&InitailSearchRequestedFromExternalPage=false&SearchText=&SelectedYear=2022&Careers%5B0%5D=&Careers%5B1%5D=&Careers%5B2%5D=&Careers%5B3%5D=&Sessions%5B0%5D=&Sessions%5B1%5D=&Sessions%5B2%5D=&Sessions%5B3%5D=&Sessions%5B4%5D=&Sessions%5B5%5D=&DegreeIdentifiers%5B0%5D=&DegreeIdentifiers%5B1%5D=&DegreeIdentifiers%5B2%5D=&FilterByMajors=&FilterByMinors=&FilterBySpecialisations=&CollegeName=All+Colleges&ModeOfDelivery=All+Modes
https://programsandcourses.anu.edu.au/data/MajorSearch/GetMajors?AppliedFilter=FilterByAllSpecializations&Source=&ShowAll=True&PageIndex=0&MaxPageSize=10&PageSize=Infinity&SortColumn=&SortDirection=&InitailSearchRequestedFromExternalPage=false&SearchText=&SelectedYear=2022&Careers%5B0%5D=&Careers%5B1%5D=&Careers%5B2%5D=&Careers%5B3%5D=&Sessions%5B0%5D=&Sessions%5B1%5D=&Sessions%5B2%5D=&Sessions%5B3%5D=&Sessions%5B4%5D=&Sessions%5B5%5D=&DegreeIdentifiers%5B0%5D=&DegreeIdentifiers%5B1%5D=&DegreeIdentifiers%5B2%5D=&FilterByMajors=&FilterByMinors=&FilterBySpecialisations=&CollegeName=All+Colleges&ModeOfDelivery=All+Modes
```

# Todo

- [x] Get JSON datasets through API endpoints
- [ ] Scrape programsandcourses for additional data
  - [ ] scrape programs (degrees)
  - [ ] scrape concentrations / majors / minors
  - [ ] scrape classes
    - [ ] Challenge: Translating unstructured "Requisites" into a structured boolean expression tree.


# Semantic Parsing

```sh

# target: "and" / "or" where
# a. preceded or followed by a punctuation, unless that punctuation is part of a named entity
# b. different pair of named entity and verb on left and right of the sentence
# give priority to a over b
# action: split
"To enrol in this course you must be studying a Master of Engineering 
and 
have completed ENGN8100 and (ENGN8160 or ENGN8260)."

"To enrol in this course you must have either: completed COMP6250 (Professional Practice 1) 
and be enrolled in the Master of Computing; 
OR 
be enrolled in the Master of Computing (Advanced)."

# capture co-requisite (COMP6710 OR COMP6730)
# target: "or" & if verb to the left but no named entity to the left
# action: treat as one expression, co-requisite check
# turn it into OR of two expressions: enrolled, completed
"To enrol in this course you must have completed or be currently enrolled in COMP6710 OR COMP6730."

# split by "-" and check length
# note verb to the left of ":" and recursively divide the right half into left and right
"To enrol in this course you must: 
- be enrolled in the Master of Computing 
- have completed COMP8260 and COMP6442 
- find a project/supervisor; and 
- have an approved 'Independent Study Contract' Incompatible with COMP8715 and COMP8830."
```

```
# get frequency of conditions
grep "condition" classes.json | awk -F" " '{print $2}' | sort | uniq -c | sort -nr
```
output

      56 "completed",
      38 "incompatible",
      36 "studying",
      18 "enrolled",
      14 "Unknown",
      5 "permission",
      1 "obtained",