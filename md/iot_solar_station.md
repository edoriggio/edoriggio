# IoT Solar Station

*Edge Computing in the IoT* project made by Alfio Vavassori, Cristiano Colangelo, Samuel Corecco, and Edoardo Riggio.
<br/> <br/>

![](https://github.com/edoriggio/iot-solar-station/raw/main/assets/png/solar-station-photo.jpg)
*Picture of the complete solar station*
<br/> <br/>

## Info about the Project

### Abstract

The IoT Solar Station is an advanced weather station with an integrated self-positioning solar panel.
The orthogonal 2-axis servo motors move the solar panel,
while the attached voltmeter constantly measures the current power production.
The solar panel moves at different angles and searches for the best one based on the voltmeter measurements.
The onboard sensors send the collected data to a private MQTT broker, which forwards the data to a Python backend.
The backend ingests the data into a DigitalOcean cloud instance hosting an ElasticSearch database via Docker containers.
Finally, a Kibana dashboard deployed alongside the database showcases the collected data in nice,
compact visualizations.
<br/> <br/>

### Hardware

The following is a list of components used in this project:

- (1x) Arduino Portenta H7
- (1x) Small Solar Panel
- (1x) M5-ADS1115 Voltmeter
- (1x) BME280 Ambient Sensor
- (1x) BH1750FVI-TR Ambient Light Sensor
- (1x) PCA9685 Servo Driver Shield
- (1x) Female DC Power Plug
- (2x) MG996R High Torque Servos
- (33x) Jumper Wires
<br/> <br/>

Schematics of the system can be found in the `assets/ckt/project-circuit.ckt` [cirkit](https://www.cirkitdesigner.com/) file.
<br/> <br/>

![](https://github.com/edoriggio/iot-solar-station/raw/main/assets/png/project-circuit.png)
*Schematics of the system*
<br/> <br/>

### Cloud Architecture

For our project, we decided to implement communication with an MQTT (MQ Telemetry Transport) broker,
which allows us to send lightweight, continuous messages to our cloud instance.
We used the service shiftr.io, a high-performance broker that easily connects devices to the same network.
To implement communication, we used a MQTT client library in both the Arduino Portenta and our Python backend.
The MQTT client on the Arduino board will send a message after every calibration phase.
The client emits a JSON message on a defined topic, and the Python backend will subscribe to that topic.
When a message is sent from the Arduino,
the Python server will receive the message which will then be sent to our ElasticSearch service,
and finally displayed in the Kibana dashboard.
<br/> <br/>

![](https://github.com/edoriggio/iot-solar-station/raw/main/assets/png/kibana-dashboard.png)
*Screenshot of the Kibana dashboard*
<br/> <br/>

The following are the cloud components used:

- Shitfr.io (MQTT Broker)
- DigitalOcean Droplet (MQTT Server)
- Python Server (MQTT Listener)
- ElasticSearch+Kibana (Database and Dashboard)
<br/> <br/>

![](https://github.com/edoriggio/iot-solar-station/raw/main/assets/png/cloud-architecture.png)
*Schematic of the cloud components*
