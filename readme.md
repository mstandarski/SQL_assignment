1.  Create a list of students showing first and last names only.

SELECT *
  FROM student
  WHERE years_of_experience

  first_name	last_name
  Eric	Ephram
  Greg	Gould
  Adam	Ant
  Howard	Hess
  Charles	Caldwell
  James	Joyce
  Doug	Dumas
  Kevin	Kraft
  Frank	Fountain
  Brian	Biggs



2.  Create a list of students with all the columns but only if the student has less than 8 years experience

  SELECT *
  FROM student
  WHERE years_of_experience < 8

  1	Eric	Ephram	2	2016-03-31
  2	Greg	Gould	6	2016-09-30
  3	Adam	Ant	5	2016-06-02
  4	Howard	Hess	1	2016-02-28
  5	Charles	Caldwell	7	2016-05-07
  8	Kevin	Kraft	3	2016-04-15
  10	Brian	Biggs	4	2015-12-25



3.  Create a list of students showing the lastname, startdate, and id columns only and sorted by last_name in ascending sequence

  SELECT last_name, start_date, student_id
    FROM student
    ORDER BY last_name

Ant	2016-06-02	3
Biggs	2015-12-25	10
Caldwell	2016-05-07	5
Dumas	2016-07-04	7
Ephram	2016-03-31	1
Fountain	2016-01-31	9
Gould	2016-09-30	2
Hess	2016-02-28	4
Joyce	2016-08-27	6
Kraft	2016-04-15	8


4.  Create a list of students showing all columns but only if the student first name is Adam, James, or Frank and sort them in last_name descending sequence.

  SELECT *
    FROM student
    WHERE first_name in ("Adam", "James", "Frank")
    ORDER BY last_name desc

    6	James	Joyce	9	2016-08-27
9	Frank	Fountain	8	2016-01-31
3	Adam	Ant	5	2016-06-02


5.  Create a list of students showing firstname, lastname and startdate where the startdate is between Jan 1, 2016 and June 30, 2016 and order the list by descending start_date sequence.

  SELECT first_name, last_name, start_date
    FROM student
    WHERE start_date > '2016-01-01' and start_date < '2016-06-30'
    ORDER BY start_date desc

    Adam	Ant	2016-06-02
Charles	Caldwell	2016-05-07
Kevin	Kraft	2016-04-15
Eric	Ephram	2016-03-31
Howard	Hess	2016-02-28
Frank	Fountain	2016-01-31






Medium Challenge

When you're done, execute the following commands then copy and paste them into the document.

Commands:

Explain assignment;
mysql> Explain assignment;
+----------------+------------------+------+-----+---------+----------------+
| Field          | Type             | Null | Key | Default | Extra          |
+----------------+------------------+------+-----+---------+----------------+
| assignment_id  | int(11) unsigned | NO   | PRI | NULL    | auto_increment |
| student_id     | int(11)          | NO   |     | NULL    |                |
| assignment_nbr | int(11)          | NO   |     | NULL    |                |
| class_id       | int(11)          | YES  |     | NULL    |                |
| grade_id       | int(11)          | YES  | MUL | NULL    |                |
+----------------+------------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

select * from assignment;
mysql> select * from assignment;
+---------------+------------+----------------+----------+----------+
| assignment_id | student_id | assignment_nbr | class_id | grade_id |
+---------------+------------+----------------+----------+----------+
|           101 |          7 |             25 |       50 |        3 |
|           102 |          2 |             25 |       50 |        1 |
|           103 |          4 |             25 |       50 |        2 |
|           104 |         10 |             25 |       50 |        4 |
|           105 |          1 |             25 |       50 |        5 |
+---------------+------------+----------------+----------+----------+
5 rows in set (0.00 sec)


Explain grade;
mysql> Explain grade;
+-------------+-------------+------+-----+---------+----------------+
| Field       | Type        | Null | Key | Default | Extra          |
+-------------+-------------+------+-----+---------+----------------+
| grade_id    | int(11)     | NO   | PRI | NULL    | auto_increment |
| grade_value | varchar(30) | YES  |     | NULL    |                |
+-------------+-------------+------+-----+---------+----------------+
2 rows in set (0.00 sec)


select * from grade;
mysql> select * from grade;
+----------+-----------------------------+
| grade_id | grade_value                 |
+----------+-----------------------------+
|        1 | incomplete                  |
|        2 | complete_and_unsatisfactory |
|        3 | complete_and_satisfactory   |
|        4 | exceeds_expectations        |
|        5 | not_graded                  |
+----------+-----------------------------+
5 rows in set (0.00 sec)
