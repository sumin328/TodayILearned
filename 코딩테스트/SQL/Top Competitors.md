# Top Competitors

## Problem
Julia just finished conducting a coding contest, and she needs your help assembling the leaderboard! Write a query to print the respective hacker_id and name of hackers who achieved full scores for more than one challenge. Order your output in descending order by the total number of challenges in which the hacker earned a full score. If more than one hacker received full scores in same number of challenges, then sort them by ascending hacker_id.

## Solution
```sql
select s.hacker_id, h.name
from submissions as s 
join (select c.challenge_id as challenge_id , d.score as score
      from challenges as c left 
      join difficulty as d
      on c.difficulty_level = d.difficulty_level) as t
on s.challenge_id = t.challenge_id and s.score = t.score
join hackers as h
on s.hacker_id = h.hacker_id
group by s.hacker_id, h.name
having count(S.challenge_id) > 1
order by count(s.challenge_id) desc, s.hacker_id
```