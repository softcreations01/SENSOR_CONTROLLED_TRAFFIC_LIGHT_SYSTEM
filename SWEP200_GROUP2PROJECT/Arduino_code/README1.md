  **1. LED and Sensor Pin Definitions:**
    The code starts by defining the pin numbers for the LEDs that represent the traffic signal lights (RED_PIN_1, YELLOW_PIN_1, etc.) and 
    the pins for the ultrasonic sensors (trigPin1, echoPin1, etc.).

  **2. Sensor Variables:**
        presentSensorId: Represents the currently active lane (0, 1, or 2).
        nextSensorId: Represents the next lane to be activated.
        sensorCount: Number of lanes (3 in this case).

   **3. Time Constants:**
        greenDelay: Delay duration for green signal (10 seconds).
        yellowDelay: Delay duration for yellow signal (4 seconds).

  **4.init_Light() Function:**
        Initializes the LED pins as outputs.
        Sets the initial state of all LEDs to red.

  **5. Switching Functions**:
        switchLane1ToRed(), switchLane1ToYellow(), switchLane1ToGreen(): Control LED states for lane 1.
        Similar functions for lanes 2 and 3.

  **6. sensorIdUpdate() Function:**
        Detects if a lane is busy (occupied by a vehicle) based on sensor readings.
        Scans through lanes to find the next available lane for traffic.

   **7. setup() Function:**
        Initializes serial communication for debugging.
        Sets LED pins as outputs.
        Sets initial LED states to red.
        Initializes ultrasonic sensor pins.

   **8. loop() Function:**
        The main loop of the program.
        Measures the distance using ultrasonic sensors for each lane.
        Determines the traffic signal pattern for each lane based on distance readings.
        If a lane is empty (distance > 100 cm), the signal is red.
        If a vehicle is at a mid-distance (10 cm to 50 cm), the signal turns yellow.
        If a vehicle is close (less than 10 cm), the signal turns green.
        Updates the present and next sensor IDs based on traffic conditions.

The code iterates through the loop repeatedly, measuring distances using ultrasonic sensors for each lane and controlling the traffic signal lights accordingly. The logic ensures that lanes with higher vehicle density receive a longer green signal duration.
