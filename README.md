# databases
This repository is for Metropolia's AMK IT Relational Database course.

## Week 3 Exercise 1: 
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

## Week 3 Exercise 2:
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