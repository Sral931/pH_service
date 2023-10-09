# pH_service
Raspbian service to read out the Robo-Tank pH sensor data without communication errors.

## Installation

 - in SSH command console type:
 - sudo wget -c https://github.com/Sral931/pH_service/releases/download/1.2/pH_service_1.2.zip
 - sudo unzip pH_service_1.2.zip
 - sudo bash install_pH.sh
 
 - the install script will copy all files, start the necessary service and clean up the install files afterwards
 
 - In Reef-Pi go to Configuration->Drivers
 - create 1 file driver in Reef-Pi:
	- Name appropriately (e.g. "pH_file")
	- Type: "file-analog"
	- Paths (for each filedriver respectively):
		- "/var/lib/reef-pi/pH/pH.dat"
		
 - go to Configuration->Admin and reload
 - go to Configuration->Connectors
	- create 1 Analog-Inputs:
		- Name appropriately (e.g. "pH_from_file")
		- Driver: the 1 file-drivers you have created before
		- Pin: 0
 - go to Configuration->Admin and reload
 - go to pH
 - add 1 "pH" values using the analog-inputs you have just created