# Challenges

## Problem
Julia asked her students to create some coding challenges. Write a query to print the hacker_id, name, and the total number of challenges created by each student. Sort your results by the total number of challenges in descending order. If more than one student created the same number of challenges, then sort the result by hacker_id. If more than one student created the same number of challenges and the count is less than the maximum number of challenges created, then exclude those students from the result.


## Solution
```sql
SELECT H1.HACKER_ID
     , H1.NAME
     , COUNT(*) AS CNT
FROM HACKERS AS H1
    JOIN CHALLENGES AS C1
        ON H1.HACKER_ID = C1.HACKER_ID
GROUP BY H1.HACKER_ID, H1.NAME
HAVING CNT = (SELECT COUNT(*)
              FROM CHALLENGES AS C2
              GROUP BY C2.HACKER_ID
              ORDER BY COUNT(*) DESC
              LIMIT 1
             )
    OR CNT IN (SELECT DISTINCT C_COMPARE AS C_UNIQUE
               FROM (SELECT H2.HACKER_ID
                          , H2.NAME
                          , COUNT(CHALLENGE_ID) AS C_COMPARE
                     FROM HACKERS AS H2
                        JOIN CHALLENGES C3 ON C3.HACKER_ID = H2.HACKER_ID
                     GROUP BY H2.HACKER_ID, H2.NAME
                    ) AS COUNTS
               GROUP BY C_COMPARE
               HAVING COUNT(C_COMPARE) = 1
              )
ORDER BY CNT DESC, H1.HACKER_ID
```