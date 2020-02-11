# Binary Tree Nodes

## Problem
You are given a table, BST, containing two columns: N and P, where N represents the value of a node in Binary Tree, and P is the parent of N.

Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:

Root: If node is root node.
Leaf: If node is leaf node.
Inner: If node is neither root nor leaf node.

## Solution
```sql
select N, case when P is null then 'Root' 
               when N in (select P 
                           from bst) then 'Inner'
               ELSE 'Leaf'
               END
from BST
order by N
```

> NOT IN의 경우, 집합 안에 NULL값이 있으면 설령 왼쪽 값이 집합 안에 포함되어 있지 않아도 참을 반환하지 않는다.  
> 그 결과는 '불명(UNKNOWN)'이 됩니다.
```sql
select N, case when P is null then 'Root' 
               when N not in (select P 
                              from bst) then 'Leaf'
               ELSE 'Inner'
               END
from BST
order by N
```
> NOT IN 부분에서 집합에 null이 존재하기 때문에 모든 값이 거짓으로 반환된다.  
> 따라서 OUTPUT에 LEAF가 반환되지 않는다.