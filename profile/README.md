<p float="left">
  <img alt="uhasselt-liggend" src="assets/uhasselt-liggend.png" width="650" />
  <img alt="solar-cooker" src="assets/solar-cooker.jpg" width="154" /> 
</p>

# Solar Cooker UHasselt

**Solar Cooker UHasselt** is part of the _Solar Cookers for All (SC4All)_ initiative, a collaboration between Hasselt University (Belgium) and the University of Lubumbashi (DRC), funded by VLIR-UOS.  
The project focuses on designing, prototyping, and locally manufacturing low-cost solar cookers for sustainable cooking solutions in resource-constrained communities.

This organization hosts the **source code and PCB designs for the solar cooker testing station in KiCad**, which measures cooking temperature (PT100), ambient conditions (temperature, humidity, wind), and solar irradiance. Key metrics are displayed on an LCD.

Supporting repositories for tools, experiments, and related hardware designs are also included, making this a central hub for the open-source development and testing of solar cooking technologies.

## Acknowledgments

This work would not have been possible without the contributions of **Ruben Godde, Kato Warson, and Jonas Meijerink**.

## Version 1 Testing Station

<p float="left">
  <img alt="Testing Station V1" src="assets/testing_station_v1.jpg" width="400" />
</p>

_Early prototype of the solar cooker testing station (Version 1), used for initial field experiments and validation of sensors and data acquisition._

## Version 2 Testing Station

<table>
  <tr>
    <td align="center">
      <img alt="Testing Station V2 Top Render" src="assets/testing_station_v2_render_edit.png" width="600" /><br>
      Top render with Arduino visible
    </td>
    <td align="center">
      <img alt="Testing Station V2 Bottom Render" src="assets/testing_station_v2_render_back_no_arduino_edit.png" width="600" /><br>
      Bottom render without Arduino for clarity
    </td>
  </tr>
</table>

_Version 2 prototype renders showing both top and bottom views of the solar cooker testing station._

## Repository Overview

### Main Repositories

- [**kicad-testing-station**](https://github.com/solar-cooker-UHasselt/kicad-testing-station): Complete testing station for measuring solar cooker performance.
- [**arduino-code**](https://github.com/solar-cooker-UHasselt/arduino-code): Arduino code for controlling and reading all components of the solar cooker testing station.

### Prototypes Used in the Main Project

- [**kicad-adafruit-bme680**](https://github.com/solar-cooker-UHasselt/kicad-adafruit-bme680): Environmental sensor breakout featuring temperature, humidity, barometric pressure, and VOC gas sensing.  
- [**kicad-adafruit-ds3231**](https://github.com/solar-cooker-UHasselt/kicad-adafruit-ds3231): Precision real-time clock (RTC) breakout.  
- [**kicad-adafruit-max31865**](https://github.com/solar-cooker-UHasselt/kicad-adafruit-max31865): Platinum RTD-to-digital converter breakout for precise temperature measurements.  
- [**kicad-adafruit-microsd**](https://github.com/solar-cooker-UHasselt/kicad-adafruit-microsd): MicroSD breakout for data logging and removable storage.

### Old or Supporting Repositories

- [**kicad-arduino-uno-r4-wifi**](https://github.com/solar-cooker-UHasselt/kicad-arduino-uno-r4-wifi): In-progress custom Arduino UNO R4 WiFi PCB to replace shield-based designs.  
- [**kicad-testing-station-old**](https://github.com/solar-cooker-UHasselt/kicad-testing-station-old): Legacy version of the testing station PCB.  
- [**python-bom-script**](https://github.com/solar-cooker-UHasselt/python-bom-script): Script to generate bills of materials and fetch real-time component pricing from Mouser and DigiKey.  
- [**shiny-data-analysis**](https://github.com/solar-cooker-UHasselt/shiny-data-analysis): R Shiny dashboard for visualizing experimental data from the solar cooker project.
