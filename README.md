# Open-House-RoboAC

- main file `src/main.cpp`
  ```cpp
  #include <Arduino.h>
  #include <AccelStepper.h>

  #define Mode 1
  #define PUL 13
  #define DIR 12

  // AccelStepper stepper; // Defaults to AccelStepper::FULL4WIRE (4 pins) on 2, 3, 4, 5
  AccelStepper stepper(Mode, PUL, DIR);

  void setup()
  {
    stepper.setMaxSpeed(1000);
    stepper.setAcceleration(1000);
    stepper.runToNewPosition(500);
  }

  void loop()
  {
    stepper.runToNewPosition(0); // Cause an overshoot then back to 0
  }
  ```

    - Using AccelStepper Libraries
    - stepper is AccelStepper object
    - MaxSpeed is 1000 steps per second
    - Acceleration is 1000 steps per second ^ 2