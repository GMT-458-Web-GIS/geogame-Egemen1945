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


## Interacting with the DOM

In this project, the DOM (Document Object Model) was used extensively to manage and update the game interface dynamically. The following key elements of the DOM were manipulated:

- **Neighbor Buttons**: Dynamic buttons were created and added to the neighbors-container element to display neighboring cities and one incorrect option for each question. These buttons allowed user interaction to proceed with the game.

- **Current City Display**: The current-city element was updated dynamically to reflect the name of the city currently being asked.

- **Score Display**: The score element was dynamically updated to show the current score whenever the user selected a correct answer.

- **Game Reset**: The neighbors-container element was cleared and repopulated with new options when the game was restarted via the "Restart Game" button. Additionally, the score and current city were reset to their initial states.

These DOM interactions ensured that the game interface remained responsive, interactive, and consistent with the current state of the game.



## Event Handlers in the Game

In this project, several event handlers are implemented to manage user interactions dynamically. Below are three key event handlers used in the game:

---

### 1. Neighbor Selection Button (Click Event)
 Each neighboring city is represented as a dynamically generated button.
 When the user clicks on a button, the event handler checks if the selected city is a correct neighbor of the current city:
  If the selection is correct**:
  The score increases by 1.
  A new random city is selected, and the game continues.
  If the selection is incorrect**:
  The game ends with a "Game Over" alert.
  Code example:
  button.addEventListener("click", () => handleNeighborClick(neighbor, true));

### 2. Incorrect City Button (Click Event)
An incorrect city button is also dynamically created in the game.
When the user clicks on this button, the event handler does the following:
Actions:
Ends the game immediately.
Resets the score to zero.
Displays a "Game Over" alert to the player.

Code example: 
incorrectButton.addEventListener("click", () => handleNeighborClick(incorrectCity, false));

### 3. Restart Game Button (Click Event)
The "Restart Game" button allows players to restart the game after a "Game Over."
When the user clicks this button, the event handler does the following:
Actions:
Resets the score to 0.
Randomly selects a new city as the starting point.
Resets the interface for a new game session.
Code example:
restartButton.addEventListener("click", resetGame);

## Using Closures in the Project

Closures are an essential part of this project, enabling the game to handle dynamic user interactions and maintain persistent data. Here is how closures were utilized and benefited the project:

---

### 1. **Encapsulation of Variables**
- Closures were used to encapsulate variables such as `score` and `currentCity`, ensuring that these variables are accessible only within the necessary scope and not exposed globally.
- This helped:
  - Maintain data integrity by avoiding accidental overwrites.
  - Ensure that `score` and `currentCity` values persist across different function calls without relying on global variables.

Example:


let score = 0;
let currentCity = getRandomCity();

function handleNeighborClick(selectedCity, isCorrect) {
  if (isCorrect) {
    score++;
    currentCity = getRandomCity();
    loadGame();
  } else {
    endGame();
  }
}

### 2. Dynamic Event Handling
Closures were used within addEventListener to dynamically bind values (like the name of a selected city) to event handlers without polluting the global scope.
Each button click handler retains its own reference to the neighbor or incorrectCity variable through closures.
Example:


neighbors.forEach(neighbor => {
  const button = document.createElement("button");
  button.innerText = neighbor;
  button.addEventListener("click", () => handleNeighborClick(neighbor, true));
});








