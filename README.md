# Universal LAN Board with WT32-ETH01 Module for Pylontech and more

This project introduces a universal board that can be used for various purposes. The heart of the board is a WT32-ETH01 module with an ESP32 and a LAN interface. Depending on the configuration and software, the board can fulfill different functions.

![3D Case Photo with PCB](https://github.com/ingmarsretro/pylontech_Lan_Interface/raw/main/3d_case_photo_with_pcb.jpg)

## Features

### Communication with Pylontech Solar Batteries

The board can communicate with Pylontech solar batteries (US2000, US3000c, ...) via the serial console interface. For this purpose, the software from the following repositories has been adapted from ESP8266 to ESP32:
- [Pylontech-Battery-Monitoring by irekzielinski](https://github.com/irekzielinski/Pylontech-Battery-Monitoring)
- [PylontechMonitoring by hidaba](https://github.com/hidaba/PylontechMonitoring)

Thus, the Pylontech batteries can communicate via LAN over MQTT with, for example, Homeassistant.

### Communication with Microinverters (e.g., Hoymiles)

The board can communicate with microinverters such as Hoymiles via OpenDTU software and the NRF24L01+ module:
- [OpenDTU by tbnobody](https://github.com/tbnobody/OpenDTU)

A configuration file for OpenDTU with WS32ETH 01 is included and can be adjusted if necessary. Further information for current software can be found on the OpenDTU GitHub.

### Communication via CAN or RS485

The board can communicate with various devices via CAN or RS485. Projects for this will be developed or published as needed.

## Installation

1. **Prepare Hardware:**
   - Assemble the board according to the desired functionality (e.g., NRF24L01+ module for OpenDTU or MAX3232 along with console connector for Pylontech).
   - Connect the WT32-ETH01 module to your network and the assembled function to your device (e.g., serial console interface for Pylontech batteries).

2. **Install Software:**
   - Download the appropriate software from the repositories mentioned above.
   - Adjust the configuration files to your needs.
   - Flash the software onto the WT32-ETH01 module. (In the Pylontech software script, IP addresses need to be adjusted. Use Arduino IDE for compiling.)
     To flash the software, a USB_RS232 interface is required. The "Prog" jumper must be set. The programmer is connected to the "TO-FTDI" pins.

3. **Configuration:**
   - When using with Pylontech, enter the address specified in the code in your web browser. If the connection is OK, the data of the Pylontech batteries will be displayed in the browser.
     If an MQTT server is present and correctly specified in the code, MQTT messages will be sent.
   - When using with OpenDTU, configure the network via the OpenDTU access point after flashing the firmware and load the wt32mapping.json file.
   - Ensure all connections are correct and start the system.

## Usage

Depending on configuration and software, you can use the board for various purposes:
- **Pylontech Batteries:** Monitor and control your Pylontech solar batteries via MQTT and integrate them into Homeassistant.
- **Microinverter:** Communicate with microinverters like Hoymiles via OpenDTU and monitor your solar system.
- **CAN/RS485:** Develop your own projects for communication via CAN or RS485 with various devices.

## License
free



# Universalboard mit WT32-ETH01 Modul

Dieses Projekt stellt ein Universalboard vor, das für verschiedene Zwecke verwendet werden kann. Das Herzstück des Boards ist ein WT32-ETH01 Modul mit einem ESP32 und einem LAN Interface. Je nach Bestückung und Software kann das Board verschiedene Funktionen erfüllen.

![3D Case Photo with PCB](https://github.com/ingmarsretro/pylontech_Lan_Interface/raw/main/3d_case_photo_with_pcb.jpg)

## Funktionen

### Kommunikation mit Pylontech Solarbatterien

Das Board kann mit den Solarbatterien von Pylontech (US2000, US3000c, ...) über die serielle Console-Schnittstelle kommunizieren. Dafür wurde die Software von folgenden Repositories vom ESP8266 auf den ESP32 angepasst:
- [Pylontech-Battery-Monitoring von irekzielinski](https://github.com/irekzielinski/Pylontech-Battery-Monitoring)
- [PylontechMonitoring von hidaba](https://github.com/hidaba/PylontechMonitoring)

So können die Pylontech Batterien per LAN über MQTT mit z.B. Homeassistant kommunizieren.

### Kommunikation mit Microinvertern (z.B. Hoymiles)

Das Board kann mit Microinvertern wie z.B. Hoymiles per OpenDTU Software und dem NRF24L01+ Modul kommunizieren:
- [OpenDTU von tbnobody](https://github.com/tbnobody/OpenDTU)

Ein Konfigurationsfile für openDTU mit WS32ETH 01 ist beigelegt und kann ggf angepasst werden. Weitere für aktuelle Software auf openDTU git

### Kommunikation über CAN oder RS485

Das Board kann über CAN bzw. RS485 mit beliebigen Geräten kommunizieren. Projekte dazu werden entwickelt bzw. veröffentlicht, sobald sie benötigt werden.

## Installation

1. **Hardware vorbereiten:**
   - Bestücke das Board je nach gewünschter Funktionalität (z.B. NRF24L01+ Modul für OpenDTU oder MAX3232 samt Console Conector für Pylontech)
   - Verbinde das WT32-ETH01 Modul mit deinem Netzwerk und die bestückte Funtkion mit deinem Gerät (z.B. serielle Console-Schnittstelle für Pylontech Batterien).

2. **Software installieren:**
   - Lade die entsprechende Software aus den oben genannten Repositories herunter. 
   - Passe die Konfigurationsdateien an deine Bedürfnisse an. 
   - Flashe die Software auf das WT32-ETH01 Modul. (im Pylontech Softwarescript müssen die IP Adressen angepasst werden. zum kompilieren z.b. Adruino IDE verwenden)
     Zum flashen der Software ist ein USB_RS232 Interface notwendig. Der Jumper "Prog" muss gesetzt sein. Der Programmer wird an den Pins "TO-FTDI" angeschlossen

3. **Konfiguration:**
   - bei Verwendung mit Pylontech im Webbrowser die im code eingegeben Adresse eingeben. Ist die Verbindung OK werden die Daten der Pylontech Batterien im Browser angezeigt.
     Ist der MQTT Server vorhanden und im code richtig angegeben dann werden die mqtt messages gesendet
   - bei Verwednung mit openDTU ist nach dem Flashen der Firmware über den openDTU accesspoint das Netzwerk zu konfigurieren und das wt32mapping.json file zu laden.
   - Stelle sicher, dass alle Verbindungen korrekt sind und starte das System.

## Nutzung

Je nach Bestückung und Software kannst du das Board für verschiedene Zwecke nutzen:
- **Pylontech Batterien:** Überwache und steuere deine Pylontech Solarbatterien über MQTT und integriere sie in Homeassistant.
- **Microinverter:** Kommuniziere mit Microinvertern wie Hoymiles über OpenDTU und überwache deine Solaranlage.
- **CAN/RS485:** Entwickle eigene Projekte zur Kommunikation über CAN oder RS485 mit verschiedenen Geräten.

## Lizenz
free
