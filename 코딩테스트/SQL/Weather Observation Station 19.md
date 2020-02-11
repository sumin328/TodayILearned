# Weather Observation Station 19

## Problem

Consider P1(a,c) and P2(b,d) to be two points on a 2D plane where (a,b) are the respective minimum and maximum values of Northern Latitude (LAT_N) and (c,d) are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.

Query the Euclidean Distance between points P1 and P2 and format your answer to display 4 decimal digits.

## Solution
```sql
select round(sqrt(power((b-a),2) + power((d-c),2)),4)
from (select min(LAT_N) as a, max(LAT_N) as b, min(LONG_W) as c, max(LONG_w) as d
      from station) as temp
```
