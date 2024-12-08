# GeoGame - Neighbor City Game
https://gmt-458-web-gis.github.io/geogame-Egemen1945
Mehmet Egemen Ecevit 21833116
## Project Objective
This project is a geographical game where the player is given a city in Turkey and must select one of its neighboring cities.
The game continues until the player makes an incorrect choice.
The goal is to select as many correct neighboring cities as possible without making a mistake.

## Requirements
- **Random City Selection**: At the start of the game, a random city is selected and displayed to the player.
- **Neighbor Selection Mechanic**: The player is presented with a list of neighboring cities and must choose one of them.
- **Verification and Scoring**: If the player selects a correct neighboring city, the game continues with the chosen city as the new current city, and the score is incremented. If the player selects an incorrect city, the game ends, and the final score is displayed.
- **Result Feedback**: The game provides immediate feedback on whether the chosen city is correct and tracks the player’s score.

## Game Layout

- **Game Title**: Displayed at the top of the screen as "Neighbor City Game".
- **Current City**: The name of the current city is displayed for the player.
- **Neighbor Choices**: Below the current city, there is a list of buttons, each representing a neighboring city. The player selects one of these buttons as their choice.
- **Score Display**: The player’s current score is shown below the neighbor choices, updating with each correct selection.

## JavaScript Library Used

This game uses **plain JavaScript** to manage the game logic, UI updates, and scoring. 
Library Leaflet will be used to add more geographical data functionality.


<img width="924" alt="Screenshot 2024-11-05 at 23 18 08" src="https://github.com/user-attachments/assets/8877cf9f-3822-4dce-9538-820b724f14fd">
Prototype will be like this, the map, features and other will be added
