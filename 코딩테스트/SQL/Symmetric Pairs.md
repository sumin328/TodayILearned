# Symmetric Pairs
## Problem
You are given a table, Functions, containing two columns: X and Y.

Two pairs (X1, Y1) and (X2, Y2) are said to be symmetric pairs if X1 = Y2 and X2 = Y1.

Write a query to output all such symmetric pairs in ascending order by the value of X.

## Query
```sql
(select x,y
 from functions
 where x=y
 group by x, y
 having count(*) > 1)
union
(select F.X, F.Y
 from Functions as F
 where EXISTS (select X, Y
               from functions 
               where X = F.Y 
               and Y = F.X
               and X > Y))
ORDER BY X
```