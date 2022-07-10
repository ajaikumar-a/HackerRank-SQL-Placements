# HackerRank-SQL-Placements

You are given three tables: Students, Friends and Packages. Students contains two columns: ID and Name. Friends contains two columns: ID and Friend_ID (ID of the ONLY best friend). Packages contains two columns: ID and Salary (offered salary in $ thousands per month).

Write a query to output the names of those students whose best friends got offered a higher salary than them. Names must be ordered by the salary amount offered to the best friends. It is guaranteed that no two students got same salary offer.

Check out the challenge here 👉 https://bit.ly/3ym1ieY

### Solution:

```
SELECT
  s.Name
FROM
  Students s 
  JOIN Friends f ON s.ID = f.ID
  JOIN Packages p1 ON s.ID = p1.ID
  JOIN Packages p2 ON f.Friend_ID = p2.ID
WHERE
  p1.Salary <= p2.Salary
ORDER BY
  p2.Salary;
  ```
  
### Output:

```
Stuart 
Priyanka 
Paige 
Jane 
Julia 
Belvet 
Amina 
Kristeen 
Scarlet 
Priya 
Meera
```
  
