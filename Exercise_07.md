# Week 5
## Exercise 07
### 1. Vesa flies from his current location to the Nottingham Airport. At the same time, Vesa's carbon footprint increases by 500. Update the information to the database. <br>
UPDATE game 
SET location = (SELECT ident FROM airport WHERE name = "Nottingham Airport"),
co2_consumed = co2_consumed + 500
WHERE screen_name = "Vesa";
![1](https://github.com/user-attachments/assets/ac65ed75-82b7-4086-85e2-c17fcdb13e20)

### 2. Prepare your own database for the project by deleting all dummy data relating to the game state. To maintain referential integrity, you have to delete the data in a specific order. Do you have to delete data first from the game table or from the goal_reached table? <br>
a. goal_reached
![2](https://github.com/user-attachments/assets/7fc6b4bf-8ed3-4c08-8d5a-0c79dcbf90ee)

### 3. Delete the dummy data from the goal_reached table. <br>
DELETE FROM goal_reached;
![3](https://github.com/user-attachments/assets/eb00754d-19d1-4978-a265-b277690ac3df)

### 4. Delete the data from the game table. <br>
DELETE FROM game;
![4](https://github.com/user-attachments/assets/9781bf85-089b-48d1-81b3-cc29cb232e61)
