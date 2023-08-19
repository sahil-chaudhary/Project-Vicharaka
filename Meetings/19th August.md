## August 18 2023

# Meeting with Prof CPR earlier in the day
Gupta: Every week meeting with Prof CPR with progress report.
- What did you do the previous week?
- What help do you need?
- What is your committment for the next week?
There will be a sheet with all this data, shared with the mentors.

<!-- # Primary contacts -->
<!-- - Biosciences -->
<!--     - Swaraj -->
<!-- - Mechanical -->
<!--     - Sidak -->
<!--     - Pranav -->

# Upcoming meetings
| With?             | When?     | Why?        | Who?                    |
| :---------------- | :-------- | :---------- | :---------------------- |
| Prof CPR          | Fri/Sat   | generic     | All                     |
| Abhra R Choudhary | Wed/Thu   | sensors     | Gupta, Suhas, etc       |
| Prof Koushik      | Tue 17:30 | robotic arm | Anushka, Indrayudh, etc |

# Mechanical
Sidak: By the end of the month, the rover will most likely be made and be
controllable. Made out of PVC.

Anushka: Not much progress on the robotic arm. Talked to Prof Koushik and got to know:
- Too costly: USD 35k average
- Too heavy
So we might have to make the arm ourselves.
Have a meeting with Prof. Koushik at 5:30 pm, Tuesday.

# Software
## Sensors
- Figure out what sensors we need and how they interact with the software.
    - IMU: Integrated sensor with gyroscope etc.
    - Differential GPS sensor.
    - Cameras: Single lens camera, stereo camera.
    - LIDAR: High precision.
        - A paper uploaded to Git by Gupta, comparing cameras and LIDAR and the
          pros and cons of each.

## Path navigation
Sahil: A* works well only for 2D terrains.
Based on sensor data we can assign weights to potholes, hills, plains etc.
Will need help from ROS experts.

Suhas: We'll anchor on the sensors, figure out what's best, and use that to
determine power requirements and algorithms.

Meeting with Prof CPR on Friday/Saturday.

# Biosciences
Swaraj:
- We need a professor mentor, specialising in geomicrobiology. Extremely niche field.
    - One expert in Pune. Trying to get in touch with him.
    - One expert in IIT Ropar. Works in environmental engineering among others.
      Didn't reply to mail, will get to him through Prof CPR.
    - No other feasible contacts.
      Will mail Prof CPR with necessary details.
      He will forward that to the alumni group.

# ECE
Two sets of communication:
- Base station to rover.
- NVIDIA to microcontroller.
  Microcontroller choices:
    - C2000
        - Nitin is proficient in this.
        - Prof Basu's entire team is proficient in this.
        - 2018 winning team used this.
    - ESP32
    - TEENSY 4.0
- Need specs from Mechanical. Prof Basu will do most of the rest when it comes
  to power distribution board.
