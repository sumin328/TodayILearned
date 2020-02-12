# The Report

## Problem
You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks.

Ketty gives Eve a task to generate a report containing three columns: Name, Grade and Mark. Ketty doesn't want the NAMES of those students who received a grade lower than 8. The report must be in descending order by grade -- i.e. higher grades are entered first. If there is more than one student with the same grade (8-10) assigned to them, order those particular students by their name alphabetically. Finally, if the grade is lower than 8, use "NULL" as their name and list them by their grades in descending order. If there is more than one student with the same grade (1-7) assigned to them, order those particular students by their marks in ascending order.

Write a query to help Eve.

## Solution 1
```sql
(select s.name
     , g.grade
     , s.marks
from students as s 
join grades as g 
on s.marks >= g.Min_mark and s.marks <= g.Max_mark
where g.grade > 7
)

union 

(select Null as name
     , g.grade
     , s.marks
from students as s
join grades as g
on s.marks >= g.min_mark and s.marks <= g.max_mark
where g.grade < 8
)

order by grade desc, name, marks
```

## Solution 2
```sql
SELECT IF(g.Grade<8, NULL, s.Name)
     , g.Grade
     , s.Marks 
FROM Students AS s 
JOIN Grades AS g ON s.Marks 
BETWEEN g.Min_Mark AND g.Max_Mark 
ORDER BY g.Grade DESC, s.Name, s.Marks;
```