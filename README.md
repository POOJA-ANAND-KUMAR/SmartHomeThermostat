# SmartHomeThermostat
A low budget home thermostat using arduino framework.
This thermostat checks the presence ,current temperature
of the house and then checks the desired house temperature to either switch on\off the ac or heater .
All nodes used in this project were ESP32.
Parts of project: 
1. Communication: The WSN network consists of base station and the endpoint nodes who communicate using LoRa and painless Mesh(Internode-communication). The endpoint nodes shared the temperature and the occupancy to the central node.
2. Checking the Desired Home Temperature : The central node takes the average of all
temperature recorded and analyses the desired temperature by switching on
ac or heater relays as required. We used hysteresis (temperature monitoring) for the
working of relays.
3. Presence Check: The relay switch will be on,  if motion is detected (presence check)
by the PIR sensors. The presence check is done  once in 15 mins (using time interrupt) and
only if the sensor returns true true then relay will be switched on else they will be switched off.
4.Display process:  Raspberry Pi to display the output. One node collects the various temperatures, calculates the average and sends it to the database (MySQL). This average temperature reading is displayed in a webpage on raspberry pi.

The data captured can further be interpreted to check the hours of ac or heater used and also the average temperature maintained in the house.
