## SQL 
*(<b>A</b>tomicity, <b>C</b>onsistency, <b>I</b>solation, <b>D</b>urability)*
  - RDBMS
    - Postseq (Open Source), MariaDB [playground](https://sqlzoo.net/wiki/)
    - NoSql
#### CASCADE CONSTRAINTS
  - ON DELETE CASCADE
    - when the reference is deleted, the other rows that reference it also get deleted
```
 CONSTRAINT fk_column
     FOREIGN KEY (column1, column2, ... column_n)
     REFERENCES parent_table (column1, column2, ... column_n)
     ON DELETE CASCADE
);
```
  - ON UPDATE CASCADE
    - if the parent primary key is changed, the child value will also change to reflect that. 
  - NO ACTION
    - In MySQL, equivalent to RESTRICT. The MySQL Server rejects the delete or update operation 
      for the parent table if there is a related foreign key value in the referenced table.
  - RESTRICT 
    - means that any attempt to delete and/or update the parent will fail throwing an error. 
      This is the default behaviour in the event that a referential action is not explicitly specified.
    - When ON UPDATE or ON DELETE is not specified, restrict is always the default
  - SET NULL
    - When a parent node get deleted, the child nodes would be set to null
    
#### Having and groupby
Using having and groupby is simply used for summarizing data
  <b<Syntax</b>
  ```
  SELECT statements... GROUP BY column_name1[,column_name2,...] [HAVING condition];
  ```
  - "SELECT statements..." is the standard SQL SELECT command query.
  - "GROUP BY column_name1" is the clause that performs the grouping based on column_name1.
  - "[,column_name2,...]" is optional; represents other column names when the grouping is done on more than one column.
  - "[HAVING condition]" is optional; it is used to restrict the rows affected by the GROUP BY clause. It is similar to the  WHERE clause.

  <b>Grouby with multiple columns</b>

  ```
  SELECT 'category_id','year_released' FROM 'movies' GROUP BY 'category_id','year_released';
  ```


| category_id | year_released |
| :---:       |     :---:     |
| NULL        | 2008          |
| NULL        | 2010          |
| NULL        | 2012          |
| 1           | 2011          |
| 2           | 2008          |
| 6           | 2007          |
| 7           | 1920          |
| 8           | 1920          |
| 8           | 2005          |
| 8           | 2007          |

<strong>Category_id = 7 is the unique result that we get from the previous query</strong>

```
SELECT students.name as student, count(assignment_submissions.*) as total_submissions
FROM assignment_submissions
JOIN students ON students.id = student_id
WHERE students.end_date IS NULL
GROUP BY students.name
HAVING count(assignment_submissions.*) < 100;
```
<b>Having</b> is just like where, while where works for normal data, and having works for aggregated data <b>count(assignment_submissions.*)</b><br>
*NOTE: The HAVING clause is evaluated before the SELECT so we can't use the alias total_submissions alias that is created in the SELECT*

  #### Primary key
    Try to use index as primary key, otherwise you need to use something long as the foreign key and it is not easy to maintein
#### 3NF
- First Explanation: 
  - only foreign key columns should be used to reference another table, and no other columns from the parent table should exist in the referenced table (*Think about AuthorNationality is in Book table and Author table*)
- Second Explanation:
  - A table is in 2nd normal form.
  - It contains only columns that are non-transitively dependent on the primary key.
  *Note: transitively means A rely on B, B rely on C, then A rely on C.*
  ```
  Consider three columns:  AuthorNationality, Author, and Book.  Column values for AuthorNationality and Author rely 
  on the Book; once the book is known, you can find out the Author or AuthorNationality.  But also notice that the 
  AuthorNationality relies upon Author.  That is, once you know the Author, you can determine their nationality. 
  In this sense then, the AuthorNationality relies upon Book, via Author.  This is a transitive dependence.
  ```
