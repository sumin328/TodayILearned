# Weather Observation Station 18

## Problem

Consider P1(a,b) and P2(c,d) to be two points on a 2D plane.

- <b>a</b> happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
- <b>b</b> happens to equal the minimum value in Western Longitude (LONG_W in STATION).
- <b>c</b> happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
- <b>d</b> happens to equal the maximum value in Western Longitude (LONG_W in STATION).

Query the Manhattan Distance between points  and  and round it to a scale of  decimal places.

## Solution
```sql
select round((c-a)+(d-b), 4)
from (select min(lat_n) as a
           , min(long_w) as b
           , max(lat_n) as c
           , max(long_w) as d
      from station) as Temp
```