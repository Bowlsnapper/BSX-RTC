# BSX-RTC
Install instructions for the BSX-RTC (Real Time Clock)

<img src="https://github.com/Bowlsnapper/BSX-RTC/blob/main/PXL_20250124_031137832.jpg" width=49% height=49%>


When the Xbox is unplugged for more than a few hours, it will lose its date and time. If you have removed your clock capacitor entirely, this happens immediately. This can get VERY annoying and this mod attempts to solve this problem. This mod is intended to be used with the BSX for easy installation, however, it can be used with any console if wired manually to SDA, SCL, and the standby power points.

The battery is only used when the console is unplugged and the DS3231 uses so little power that the CR2032 battery will probably decompose before it fully discharges. 

Cerbios 2.4.1 is needed for compatibilty and the mod can be configured using PrometheOS (or the PrometheOS XBE I have supplied if you do not have a chip capable of of running Prom) with its "RTC Expansion" feature. When the mod is programmed using the PrometheOS RTC Expansion manager, the "RUN" Led will illuminate, signalling that the mod is functioning correctly and that you are good to reassemble the console. 

# Installation
For 1.0 - 1.4 consoles, the 3.3V stanby power is tapped using this SMD capacitor.

<img src="https://github.com/Bowlsnapper/BSX-RTC/blob/main/1011Board.png" width=49% height=49%><img src="https://github.com/Bowlsnapper/BSX-RTC/blob/main/1214Board.png" width=51% height=51%>

For 1.6 Consoles, the 5V tap can be pulled from the LPC port.

<img src="https://github.com/Bowlsnapper/BSX-RTC/blob/main/1.6%20Install.png" width=49% height=49%>

Ground can be hooked up to any ground point you see fit, but theoretically, you could use the ground from the BSX I2C hookup and only have one power lead to either 3.3 or 5V.

You can connect the 3P "MB In" JST Connector on the RTC to the BSX Modchip's "MB I2C" connector and that is it for the I2C connection if you have a BSX modchip.

<img src="https://github.com/Bowlsnapper/BSX-RTC/blob/main/PXL_20250202_061327993.jpg" width=49% height=49%>

# Set-up (Without BSX or PrometheOS capable modchip)
Cerbios (2.4.1) Ini must be configured as so to take advantage of the mod:

> ; Enables Automatic Time Sync With Optional RTC Hardware Connected to SMBus
> 
> RtcEnable = True

Run the PrometheOS-BSX.xbe and set the time in the RTC Expansion section. LED will blink when time has been set.
