# Week 03

## Exercise 02
### 1. Write a query that prints out all the columns in the goal table. The output should look as follows: <br>
SELECT * FROM goal;

![2-1](https://github.com/user-attachments/assets/aa0eaa24-873f-48b4-ab9b-5bbf9a4afea6)

### 2. Write a query that prints out the name and type of each airport in Finland. The country code for Finland is: FI. Expected output: <br>
SELECT name, type FROM airport WHERE iso_country = "FI";

![2-2](https://github.com/user-attachments/assets/2af79838-d47c-4cd3-845d-d514a31aa2e9)


### 3. Write a query that prints out the names of all Finnish airports in alphabetical order. The country code for Finland is: FI. The output should look as follows (Note that the image has been cropped to fit the screen): <br>
SELECT name FROM airport WHERE iso_country = 'FI' ORDER BY name ASC;

![2-3](https://github.com/user-attachments/assets/5c516cc9-de69-4fe0-8292-f6491828187a)


### 4. Write a query that prints out the name and type of each Finnish airport. Order the result first by type and secondly by name. The output should be as follows: <br>
SELECT name, type FROM airport WHERE iso_country = 'FI' ORDER BY type ASC, name ASC;

![2-4](https://github.com/user-attachments/assets/a08b0fbb-980f-4b63-ad85-190baec03627)


### 5. Write a query that prints out the names of all countries that start with the letter F from the country table. The output should look as follows: <br>
SELECT name FROM country WHERE name LIKE "F%";

![2-5](https://github.com/user-attachments/assets/b498cce8-443d-46c8-b7e6-af58ee299724)


### 6. Write a query that prints out all country names in the country table that include the letter F. The output should be as follows: <br>
SELECT name FROM country WHERE name LIKE "%F%";

![2-6](https://github.com/user-attachments/assets/c1b69b19-0cb6-44c7-99a1-0c4de395caf8)


### 7. What is Vesa's current location? The output should be as follows: <br>
SELECT location FROM game WHERE screen_name = "Vesa";

![2-7](https://github.com/user-attachments/assets/805ae053-e14e-49e3-8fea-23555d7be6b5)


### 8. How much of his CO2 budget has Ilkka consumed? The output should look as follows: <br>
SELECT co2_consumed FROM game WHERE screen_name = "Ilkka";

![2-8](https://github.com/user-attachments/assets/34f2e0cf-558d-4edd-b51b-46a50032e8bf)


### 9. What is the original CO2 budget? Print out the CO2 budget value only once. The output should be as follows: <br>
SELECT co2_budget FROM game LIMIT 1;

![2-9](https://github.com/user-attachments/assets/73444b57-1c4a-4e57-af0c-f1ba19df4b89)


### 10. How much of his CO2 budget does Ilkka have left? Complete the query so that the result includes the following fields: screen_name, co2_budget, co2_consumed and co2_left. <br>
SET @co2_consumed := (SELECT co2_consumed FROM game WHERE screen_name = "Ilkka"); SELECT screen_name, @co2_budget AS co2_budget, @co2_consumed AS co2_consumed, (@co2_budget - @co2_consumed) AS co2_left FROM game WHERE screen_name = "Ilkka";

![2-10](https://github.com/user-attachments/assets/3626f798-d6f6-4192-9c00-9cd8d84df2a3)








