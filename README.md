                                      Query questions:
_______________________________________________________________________________
  
    insert into movies
    ->  VALUES (null, 'Dragon Ball Super: Super Hero', 100, 'Animation', 7.1,'PG-13' );

    insert into movies
    ->  VALUES (null,'The Book of Life', 95, 'Animation', 7.2,'PG');

_____________________________________________________________________________________
    
    select * from movies where Genre LIKE 'Sci-Fi%';

    select * from movies where IMDBScore <= 6.5;
___________________________________________________________________________________
    

    select * from movies where Runtime < 100 AND Rating = 'PG' OR Rating = 'G';
    
    mysql> select genre, AVG(Runtime) as average_runtime
    -> from movies where IMDBScore < 7.5
    -> group by Genre;

_____________________________________________________________________________________


     UPDATE movies
    -> SET Rating = 'R'
    -> WHERE Title = 'StarShip Troopers'; 
    

    mysql> select movieID, Rating
    -> From movies
    -> WHERE Genre IN ('Horror', 'Documentary');
__________________________________________________________________________________________

     select MAX(IMDBScore), MIN(IMDBScore), AVG(IMDBScore) From movies;

      select MAX(IMDBScore), MIN(IMDBScore), AVG(IMDBScore), Rating
    -> from movies
    -> GROUP BY Rating
    -> HAVING COUNT(*) > 1;
____________________________________________________________________________________________


                     DELETE from movies WHERE Rating = 'R';
  ____________________________________________________________________________________________________
     
                         Final Result:
   
  +---------+-------------------------------+---------+-----------+-----------+--------+
  | movieID | Title                         | Runtime | Genre     | IMDBScore | Rating |
  +---------+-------------------------------+---------+-----------+-----------+--------+
  |       1 | Howard the Duck               |     110 | Sci-Fi    |       4.6 | PG     |
  |       2 | Lavalantula                   |      83 | Horror    |       4.7 | TV-14  |
  |       5 | Spaceballs                    |      96 | Comedy    |       7.1 | PG     |
  |       6 | Monsters inc.                 |      92 | Animation |       8.1 | G      |
  |       7 | Dragon Ball Super: Super Hero |     100 | Animation |       7.1 | PG-13  |
  |       8 | The Book of Life              |      95 | Animation |       7.2 | PG     |
  +---------+-------------------------------+---------+-----------+-----------+--------+

__________________________________________________________________________________________________
       
            drop table movies;
           drop database motionpictures
________________________________________________________________________________________________________
    show databases;
 +--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| products           |
| sakila             |
| sys                |
| world              |
+--------------------+


