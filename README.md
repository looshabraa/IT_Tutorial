# IT_Tutorial

Smart Parking Barrier System
A simulation project demonstrating automated access control, vehicle counting, and parking‑lot capacity management for a university environment.

Overview
The Smart Parking Barrier System is designed to manage vehicle entry at a university’s main gate. It automatically authenticates registered users, tracks the number of cars inside the parking lot, displays available spaces, and triggers alerts when the lot is full. The project follows the Integrated Problem‑Solving Process and includes optional enhancements supported by AI tools such as Copilot.

Features
Automated Access Control — The system opens the barrier for registered staff and students using an ID check.

Real‑Time Vehicle Counting — Entry and exit sensors update the number of cars in the lot.

Capacity Monitoring — The system calculates and displays available parking spaces.

Full‑Capacity Alerts — If the lot is full, the system denies entry and triggers an alert.

Scalable Logic — Can be adapted for real hardware such as Arduino or Raspberry%20Pi.

Problem‑Solving Approach
This project was developed using the Integrated Problem‑Solving Process:

1. Analyse
Defined the system requirements: authentication, counting, display, and alerting.

2. Organise Data
Key data includes:

Registered user list

Current vehicle count

Maximum capacity

Sensor states

Barrier and alert states

3. Design the Algorithm
A structured flow of: detect → authenticate → check capacity → open/deny → update count → display availability.

4. Implement (Word Code)
A Word Code version of the logic simulates the system’s behaviour in a loop.

5. Test and Refine
Test cases include:

Registered vs. unregistered users

Full‑capacity scenarios

Entry/exit sequences

Sensor failure handling

Example Logic (Word Code)
Code
START
SET capacity = 200
SET currentCount = 0

LOOP
  IF entrySensor = TRUE THEN
      READ vehicleID
      IF vehicleID NOT IN registeredList THEN
          DISPLAY "ACCESS DENIED"
      ELSE
          IF currentCount = capacity THEN
              DISPLAY "PARKING FULL"
              SET alert = ON
          ELSE
              OPEN barrier
              WAIT 5 seconds
              CLOSE barrier
              currentCount = currentCount + 1
          ENDIF
      ENDIF
  ENDIF

  IF exitSensor = TRUE THEN
      currentCount = currentCount - 1
  ENDIF

  available = capacity - currentCount
  DISPLAY available
ENDLOOP
END
AI Integration
AI tools such as Copilot were used to enhance the project in several ways:

Logic Refinement — Reviewed Word Code for clarity and edge‑case handling.

Alternative Solutions — Explored event‑driven and hardware‑based approaches.

Real‑World Implementation — Discussed how to build the system using microcontrollers and sensors.

Documentation Support — Assisted in producing this README.

Ethical Reflection — Considered privacy and reliability concerns in automated access systems.

Future Enhancements
Integration with RFID hardware

Mobile app for real‑time parking availability

License‑plate recognition

Data analytics for peak‑time prediction
