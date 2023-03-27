# ESP8266ZabbixSender
Library to realize the zabbix-sender on ESP8266-Arduino

# How to install this library to Arduino IDE
## Download zip file
## Use ZIP import function of the Arduino IDE
1. Import .zip file into arduino IDE using .zip library import function
2. Check the sketchbook directory (file > preferences). IDE will install the library to this location on /libraries subdirectory)
3. If the sketchbook directory is different of %USERPROFILE%\Documents\Arduino\, copy the ESP32ZabbixSender directory to
%USERPROFILE%\Documents\Arduino\libraries
4. Restart the IDE and try to compile.
more information about installing libraries here: https://docs.arduino.cc/software/ide-v1/tutorials/installing-libraries

# Usage
See `sample_ESP8266ZabbixSender/sample_ESP8266ZabbixSender.ino`

    ESP8266ZabbixSender zSender;
    zSender.Init(IPAddress(192, 168, 35, 14), 10051, "IOTBOARD_00"); // Init zabbix server address, port, and hostname of item
    zSender.ClearItem(); // clear item list
    zSender.AddItem("air.temp", 29.62); // add item such as air temperture
    zSender.AddItem("air.hum", 70.60); // add item such as air humidity
    if (zSender.Send() == EXIT_FAILURE){ // send packet
        // error handling
    }

Refer to the following repository for more information.  
  
# Based on:  
https://github.com/zaphodus/ESP8266ZabbixSender
