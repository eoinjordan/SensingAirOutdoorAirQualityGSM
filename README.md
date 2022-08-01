# :Author: EoinJ

:Email:
:Date: 24/07/2022
:Revision: version#
:License: Apache 2.0

![image](https://user-images.githubusercontent.com/11853924/182228274-a2033d70-fdd6-4b30-b18e-9ea6b56a54a5.png)

= Project: SensingAirOutdoorAirQualityGSM

This simple outdoor air quality monitor relies on the arduino iot cloud as a backend. Here I am using GSM as it is for a local park or school. The aim is to help raise awareness to the air quality in local schools by monitoring some of the key pollutants that affect these environments.

I've built these using the Lora and helium network and also Wifi, wifi is by far the easiest way to make one, although for a school this could be potentially introducing a security vulnerability to a schools network so GSM was chosen.

- Carbon Monoxide CO - Barbecues and other outdoor heating equipment.
- Carbon Dioxide CO2 - As an indicator of general good indoor air quality, which also has a base outdoor level.
- Particulate PM2.5 - (particles with a diameter of 2.5 microns or less): these particles are so small they can get deep into the lungs and into the bloodstream. There is sufficient evidence that exposure to PM2.5 over long periods (years) can cause adverse health effects. Note that PM10 includes PM2.5.
- Nitrogen Dioxide NO2 - Nitrogen dioxide is a highly reactive gas formed by emissions from motor vehicles, industry, unflued gas-heaters and gas stove tops. High concentrations can be found especially near busy roads and indoors where unflued gas-heaters are in use.

Nitrogen Dioxide (NO2), Particulate Matter (PM), Ozone (O3) and Polycyclic Aromatic Hydrocarbons (PAHs)

See common pollutants and their health affects

- https://www.epa.ie/environment-and-you/air/#:~:text=In%20Ireland%2C%20the%20number%20of,single%20biggest%20environmental%20health%20risk'.
- https://www.health.nsw.gov.au/environment/air/Pages/common-air-pollutants.aspx

== Step 1: Installation
Create an arduino cloud account
== Step 2: Pairing
Pair the arduino with your account, use your sims credentials. I have used the arduino sim plan.
== Step 3: Create a dashboard

Create an iot dashboard with the values collected your board, I choose 20 seconds as an interval to conserve battery and allow the CO2 sensor time to warm up - https://create.arduino.cc/projecthub/amalbanyus/create-a-dashboard-with-the-arduino-iot-cloud-1a897b

- 1. Open arduino_secrets and fill in your sim and plan details
- 2. upload to the iot cloud
- 3. create your dashboard

== Circuit : Assemble the circuit

Pictures are to be added of my unit for reference...

=== Folder structure

....
SensingAirOutdoorAirQualityGSM => Arduino sketch folder
├── SensingAirOutdoorAirQualityGSM.ino => main Arduino file
├── arduino_secrets.h => An arduino cloud protected file to contain and protect your sim and plan details
├── thingProperties.h => variables from the iot cloud and the intervals they will be updated.
└── ReadMe.md => this file
....

=== License
This project is released under a Apache 2.0 License.

=== Contributing
To contribute to this project please feel free to fork.

=== BOM

- Arduino MKR GSM 1400 https://docs.arduino.cc/hardware/mkr-gsm-1400
- Seeed Grove-Dust Sensor V1.0 https://wiki.seeedstudio.com/Grove-Dust_Sensor/
- Arduino MKR Connector Carrier (Grove compatible) https://store.arduino.cc/products/arduino-mkr-connector-carrier-grove-compatible?selectedStore=eu
- DFRobot HQ CO2 sensor - MG-811 gas sensor https://wiki.dfrobot.com/CO2_Sensor_SKU_SEN0159
- VOC and LQ CO2 SGP30 https://www.adafruit.com/product/3709
- 12v industrial Battery
- Automotive wire (+)red and (-)black
- A waterproof case
- Solar panel and charging circuit for a camper (RV)

=== Future Work
Additonal Gases
Ozone (O3), and Polycyclic Aromatic Hydrocarbons (PAHs)
Welcoming suggestions on Radon, currently I'm investigating wether a geiger counter can detect Radon.
Communications
Lora and Wifi examples to follow.
