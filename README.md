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