# StationeersScripts
Stationeers IC10 Codes

# Please Read!
If you have any issues with the scripts, please check their sections below before posting an issue.

# Filtration
  1. (Filtration w Gas Sensor & Vent) (IC10 Placed inside the Filtration Unit) Pins: d0 Gas Sensor, d1 Vent. This Script needs a Gas Sensor and an Active Vent. It will turn on the vent when it detects the outside temperature to be below 140c. Useful for Vulcan's night temp to collect CO2 & Volatiles.
     
  2. (Filtration w Ice Crusher Control) (IC10 Placed inside the Filtration Unit) Pins: None. This script is mostly used to manage the Ice Crushers to turn off if the pressure in the Filtration's Input is above 45MPa. I have two filtration units (only 1 has the script) with O2 Filters being fed by 2 ice crushers. Since Vulcan's Space Vapor only has Water, Oxygen, and CO2 the water goes directly through the liquid pipe, and all CO2 gets dumped in the Vulcan Atmosphere while Oxygen is captured.
     
  3. (Oxygen Filtration From Greenhouse) (IC10 Placed inside the Filtration Unit) Pins: None. This script manages the Filter to only run if the O2 % goes above 30% of the atmosphere and turns off when it hits 25%. This keeps the Greenhouse breathable while pulling the oxygen out. The filtration unit will turn off if the output pressure is above 45MPa.

# Rockets
Rockets will require at least 2 IC10 Chips and a housing for each.
  1. (Rocket Umbilical Control) First IC10 script is the umbilicals. Pins: d0 is power, d1 is gas, d2 is chutes, d3 is the rocket's Battery, d4 is a gas analyzer, d5 is the rocket's cargo storage).
     
For the gas analyzer, I placed it outside of the rocket, between a turbo pump (which I also have a script for) and the Launch Tower's umbilical.
  2. (Vulcan Rocket Control, either Metallic Field for Iron, Copper, Gold, & Silicon OR Space Vapors for Water & Oxygen). Second IC10 Script controls the rocket directly. Pins: d0 IC10 Housing the Rocket Umbilical Control script, d1 Rocket Engine, d2 Rocket Avionics, d3 Logic Dial. Set the dial to Max 10, and use 1-10 for the 9 "asteorids" inside of the Metallic Asteroid Field or the Space Vapors. You can manually change the dial at any time to change the rocket's destination but it will only change if it's surveying or mining an asteroid already.
  
  3. (TurboPump Control) Pins: d0 TurboPump, d1 Gas Analyzer on turbo pump's Output pipe, d2 Gas Analyzer on turbo pump's input pipe. This is not required but it's a script to manage any Turbo Pump (Only tested on gas!). The Pump Script uses the Ideal gas law to calculate how many moles are needed to fill the output pipe to 59.5 MPa. I use it in the rocket to manage the Pressure Fed Gas Engine and at the rocket Launch Tower to fill the pipe before the umbilical which fills the rocket.

General Scripts:
  1. (Arc Furnace Control) Pins: All Arc Furnaces. Controls up to 6 Arc Furnaces. Checks the input and if there's anything it'll turn on the furnace and activate it to smelt.
     
  2. (Centrifuge Control) Pins: All Combustion Centrifuges. Controls up to 6 Combustion Centrifuges. Checks for 1MPa of pressure at input, and if there's any item in the input it will spin up the Combustion Centrifuge. It can manage all 6 evenly by setting the throttle to 10 if rpm and stress is 0, and then cranking them up to 100 once the stress reaches 0 again. It will output reagents once it reaches 500 (the script has failed sometimes during output and reaching 100 stress. The script will turn off the combustion centrifuge and output all items then restart it.)

  3. (Fuel Mixer Control) Pins: d0 Gas Mixer, d1 Oxygen Gas Analyzer, d2 Volatiles Gas Analyzer, d3 Fuel mix Gas Analyzer (output of Gas Mixer). The script will turn on the Gas Mixer if: Temperatures of Oxygen and Volatiles are within 1 degree of eachother, and there's at least 500 kPa of Oxygen and 10MPa of Volatiles (I have a large tank for oxygen hence the lower pressure, and the volatiles higher pressure prevents rapid changes in temperature while the system pulls in fresh volatiles from Vulcan's atmosphere).

  4. (Greenhouse Grow Light & Water Valve) Pins: d0 Daylight Sensor, d1 Grow Light. Optional: d2 Liquid Analyzer, d3 Liquid Digital Valve. This script will turn on all grow lights on the network using the sensor's solar angle. Place the sensor horizontal (flat) facing up to the sun. Optionally, you can add a liquid analayzer and liquid digital valve which will turn on the digital valve as long as the temperature is between 20c and 30c. Great way to ensure the plants get access to water without shocking them with temperature.

  5. (Shutters w Switch & Motion and Occupancy Sensors) Pins: d0 Logic Switch, d1 Occupancy Sensor, d2 Shutter Controller, d3 Motion Sensor. If the switch is on and the player is in the room, the shutters will open. If either the player leaves the room, or the switch is off, the shutters will close (or remain closed). Sorry Juno is too beautiful not to see in the sky (except for the solar storms jesus it leaves me blind).

  6. (Vulcan Night Air Capture) Pins: d0 Gas Sensor, d1 Pipe Analyzer, d2 Active Vent. Optional: d3 Digital Valve. Captures the night air of Vulcan when below 140c, similar to the Filtration script but directly manages multiple Active Vents with batch writing. Optionally, add a Digital Valve and the script will open it to greatly speed up emptying the air in the pipes/tanks. Highly recommend using the new tanks for this! Be careful of where the digital valve leads as it will output A LOT of air!

# Water Production
I'm going to be honest, save yourself the O2 & Volatiles. Just send a rocket to get water. Trust me. (Posted it because it was a lot of work but I'm proud of my stupid little script!)
