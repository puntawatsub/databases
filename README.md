# databases
This repository is for Metropolia's AMK IT Relational Database course.

## Week 3 Exercise 2: 
### Question 1
```
SELECT * FROM goal;
```
![screenshot](screenshots/week3-1)
### Question 2 ¹
```
SELECT name, type FROM airport WHERE iso_country="FI";
```
![screenshot](screenshots/week3-2)
### Question 3 ¹
```
SELECT name FROM airport WHERE iso_country="FI" ORDER BY name;
```
![screenshot](screenshots/week3-3)
### Question 4 ¹
```
SELECT name, type FROM airport WHERE iso_country="FI" ORDER BY type, name;
```
![screenshot](screenshots/week3-4)
### Question 5
```
SELECT name FROM country WHERE name LIKE "F%";
```
![screenshot](screenshots/week3-5)
### Question 6
```
SELECT name FROM country WHERE name LIKE "%F%";
```
![screenshot](screenshots/week3-6)
### Question 7
```
SELECT location FROM game WHERE screen_name="Vesa";
```
![screenshot](screenshots/week3-7)
### Question 8
```
SELECT co2_consumed FROM game WHERE screen_name="Ilkka";
```
![screenshot](screenshots/week3-8)
### Question 9
```
SELECT DISTINCT co2_budget FROM game;
```
![screenshot](screenshots/week3-9)
### Question 10
```
SELECT screen_name, co2_budget, co2_consumed, @co2_left:=co2_budget-co2_consumed as co2_left FROM game WHERE screen_name="Ilkka";
```
![screenshot](screenshots/week-3-10)

#### Notes: 
¹The results are too long to be displayed in one screenshot.

## Week 3 Exercise 3:
### Question 1 ¹
```
SELECT country.name AS "country name", airport.name AS "airport name" FROM country INNER JOIN airport on airport.iso_country=country.iso_country WHERE country.name="Iceland";
```
![screenshot](screenshots/week3-2-1)
### Question 2
```
SELECT name AS "airport name" FROM airport WHERE iso_country="FR" AND type="large_airport";
```
![screenshot](screenshots/week3-2-2)
### Question 3
```
SELECT country.name as country_name, airport.name as airport_name FROM country INNER JOIN airport ON airport.iso_country=country.iso_country WHERE airport.continent="an";
```
![screenshot](screenshots/week-3-2-3)
### Question 4
```
SELECT airport.elevation_ft FROM game INNER JOIN airport ON airport.ident=game.location WHERE game.screen_name="Heini";
```
![screenshot](screenshots/week3-2-4)
### Question 5
```
SELECT airport.elevation_ft*0.3048 as elevation_m FROM game INNER JOIN airport ON airport.ident=game.location WHERE game.screen_name="Heini";
```
![screenshot](screenshots/week3-2-5)
### Question 6
```
SELECT airport.name FROM game INNER JOIN airport ON airport.ident=game.location WHERE game.screen_name="Ilkka";
```
![screenshot](screenshots/week3-2-6)
### Question 7
```
SELECT country.name FROM game INNER JOIN airport ON airport.ident=game.location INNER JOIN country ON country.iso_country=airport.iso_country WHERE game.screen_name="Ilkka";
```
![screenshot](screenshots/week3-2-7)
### Question 8
```
SELECT goal.name FROM goal_reached INNER JOIN game ON game.id=goal_reached.game_id INNER JOIN goal ON goal_reached.goal_id=goal.id WHERE game.screen_name="Heini";
```
![screenshot](screenshots/week3-2-8)

### Question 9
```
SELECT name FROM airport WHERE ident="EGKK";
```
![screenshot](screenshots/week3-2-9)
### Question 10
```
SELECT country.name FROM airport INNER JOIN country ON airport.iso_country=country.iso_country WHERE airport.ident="EGKK";
```
![screenshot](screenshots/week3-2-10)

#### Notes: 
¹The results are too long to be displayed in one screenshot.

## Week 4 Exercise 4

### Question 1
```
SELECT country.name as "country name", airport.name as "airport name" FROM country INNER JOIN airport WHERE airport.iso_country=country.iso_country AND airport.scheduled_service="YES" AND country.name="Finland";
```
![screenshot](screenshots/week4-1)
### Question 2
```
SELECT screen_name, airport.name as name FROM game INNER JOIN airport ON game.location=airport.ident;
```
![screenshot](screenshots/week4-2)
### Question 3
```
SELECT screen_name, country.name as name FROM game INNER JOIN airport ON game.location=airport.ident, country WHERE country.iso_country=airport.iso_country;
```
![screenshot](screenshots/week4-3)
### Question 4
```
SELECT airport.name, game.screen_name FROM airport LEFT JOIN game ON game.location=airport.ident WHERE LOWER(airport.name) LIKE "%hels%";
```
![screenshot](screenshots/week4-4)
### Question 5
```
SELECT goal.name, game.screen_name FROM goal LEFT JOIN goal_reached ON goal.id=goal_reached.goal_id LEFT JOIN game ON game.id=goal_reached.game_id;
```
![screenshot](screenshots/week4-5)

## Week 4 Exercise 5

### Question 1
```
SELECT name FROM country WHERE iso_country IN (
    SELECT iso_country FROM airport WHERE name LIKE "Satsuma%"
);
```
![screenshot](screenshots/week4-2-1)
### Question 2
```
SELECT name FROM airport WHERE ident IN(
    SELECT airport.ident FROM airport, country WHERE airport.iso_country=country.iso_country AND country.name="Monaco"
);
```
![screenshot](screenshots/week4-2-2)
### Question 3
```
SELECT screen_name FROM game WHERE id IN (
    SELECT DISTINCT game_id AS id FROM goal_reached, goal WHERE goal.name="CLOUDS" AND goal.id=goal_reached.goal_id
);
```
![screenshot](screenshots/week4-2-3)
### Question 4
```
SELECT name FROM country WHERE iso_country NOT IN (
    SELECT DISTINCT iso_country FROM airport
);
```
![screenshot](screenshots/week4-2-4)
### Question 5
```
SELECT name FROM goal WHERE id NOT IN (
    SELECT goal_id FROM goal_reached, game WHERE goal_reached.game_id=game.id
);
```
![screenshot](screenshots/week4-2-5)