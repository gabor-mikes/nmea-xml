# nmea-xml
The NMEA-XML Server is a simple infotainment solution for the digitalized yacht or leisure boat. It makes the boats navigational data (NMEA-0183 only) available on any device with a web browse (laptops, pads and smart-phones) that one might have on board. All available NMEA data can be displayed as text. A few virtual instruments can also display key-data. If Internet is available it can grab maps from a WMS-server and plot the boats position and heading on the map.

# Requirements

For its intended use the nmea-xml package needs to be installed on a computer with a serial port connected to the boats NMEA-0183 wires. The server can certainly be browsed on the same computer it is installed on. However, to browse it on other devices, the computer needs a LAN or WLAN connection. Furthermore, to fully utilize the server it needs Internet access, as maps are only available online, from public WMS-servers.

On Linux systems, if not already installed, Mono run-time also needs to be installed:

     sudo apt-get install update


     sudo apt-get install mono-runtime

# Installation

Create a directory and unpack the files into it.
# Usage

The  nmea-xml server is a simple command line application. It must be run with sufficient privileges to be able to open a serial port and socket. To start it, open a command prompt / console, navigate to the directory it is installed in and type:

     nmea-xml.exe

This will result in a list of options and a list of available serial ports, but it will not start the server. To start the server a nmea source must be specified. Normally a serial port, one of the ports just listed, something like this:

     nmea-xml.exe -i COM1 or nmea-xml.exe -i /dev/ttyS1

Alternatively, if nmea data is not available, the server can be test-run in demo mode, where nmea data is read repeatedly from a file instead. A few such files are provided, try:

    nmea-xml.exe -d raymarine_no.nmea

By default the server will listen on port 1671. But this can be changed with option -p [port number]. To access the server on the computer running the server type the following url in the address field of your favorite web browser:

      http://localhost:1671/

To access it from other computers or devices you must replace ‘localhost’ with your servers IP address or name, if you have a local DNS. The server will respond with the default welcome page (index.html) . This page gives a summary of the servers capabilities and a way to test all the nmea sentences. Worth noticing, is that the summary is dynamic, so if nmea sentence definitions or mime definitions are changed, the summary will reflect it — after a restart.
