# Week 03

## Exercise 02
### 1. Write a query that prints out all the columns in the goal table. The output should look as follows: <br>
select*from goal; 
![1](https://github.com/user-attachments/assets/0ed8909a-164a-49b4-8d6a-35ca1257c7fd)


### 2. Write a query that prints out the name and type of each airport in Finland. The country code for Finland is: FI. Expected output: <br>
select name, type from airport where iso_country = "FI";
![2](https://github.com/user-attachments/assets/02d2bbf0-23b6-4dc7-9659-f1a4b9521c18)

### 3. Write a query that prints out the names of all Finnish airports in alphabetical order. The country code for Finland is: FI. The output should look as follows (Note that the image has been cropped to fit the screen): <br>
SELECT name FROM airport WHERE iso_country = 'FI' ORDER BY name ASC;
![3](https://github.com/user-attachments/assets/4e97e1b4-8344-474b-8e20-54df934d57e7)

### 4. Write a query that prints out the name and type of each Finnish airport. Order the result first by type and secondly by name. The output should be as follows: <br>
select name, type from airport where iso_country = 'FI' order by type, name;
![4](https://github.com/user-attachments/assets/f1f88231-2035-4d9b-a6fa-7cabd596f9de)

### 5. Write a query that prints out the names of all countries that start with the letter F from the country table. The output should look as follows: <br>
select name from country where name like 'F%';
![5](https://github.com/user-attachments/assets/a29c1b97-517f-45fc-b9f0-d0ba7a87a198)

### 6. Write a query that prints out all country names in the country table that include the letter F. The output should be as follows: <br>
select name from country where name like "%F%";
![6](https://github.com/user-attachments/assets/6e19c724-e307-4acf-95f8-15d8cdf3b8c6)

### 7. What is Vesa's current location? The output should be as follows: <br>
select location from game where screen_name = "Vesa";
![7](https://github.com/user-attachments/assets/7ef94884-9525-4446-b271-7a16fcdef026)

### 8. How much of his CO2 budget has Ilkka consumed? The output should look as follows: <br>
select co2_consumed from game where screen_name = "Ilkka";
![8](https://github.com/user-attachments/assets/cf6c82c3-e1ed-4f4a-9133-21504f1bfa59)

