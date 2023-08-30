  ** 1. Function Refactoring:** Each traffic light state change (red, yellow, green, ready to move) has its own function.

  ** 2. Control Flow:** The loop() function is now divided into multiple stages, each representing a specific phase of the traffic light cycle.

  **3. Sensor Distance Calculation:** A new function calculateDistance() to calculate the distance using the ultrasonic sensor. This function calculates the distance based on the time it takes for 
    the ultrasonic pulse to bounce back.

  **Stages Explained:**

  _Stage 1:_ The traffic lights for lane 1 and lane 2 are green, and lane 3 is red. The loop runs for a specific time, checking if there's a car on lane 1 using the calculateDistance() function.

  _Stage 2:_ Lane 1 is switched to yellow while lanes 2 and 3 remain green. This stage represents the transition period between green and red.

  _Stage 3:_ The traffic light for lane 2 is green, and lanes 1 and 3 are red. Similar to Stage 1, the loop runs for a specific time, checking if there's a car on lane 2 using the calculateDistance() function.

  _Stage 4:_ Lane 2 is switched to yellow while lanes 1 and 3 are in the ready-to-move state. This stage represents the transition period between green and red.

  _Stage 5:_ The traffic light for lane 3 is green, and lanes 1 and 2 are red. Similar to Stage 1, the loop runs for a specific time, checking if there's a car on lane 3 using the calculateDistance() function.

  _Stage 6:_ Lanes 1 and 2 are in the ready-to-move state, and lane 3 is yellow. This stage represents the transition period between green and red.

Note: The calculateDistance() function is to determine if there's a car on the lane. If the distance is greater than 10 (indicating no car present), the loop moves to the next stage. If the distance is less than or equal to 10 (indicating a car present), the loop breaks and moves to the next stage.
