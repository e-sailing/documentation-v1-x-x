# How does it work?

OpenPlotter can manage NMEA 0183, NMEA 2000 and Signal K data.

All data entering in NMEA 0183 and 2000 format are translated into Signal K format. Some sensors generate data in Signal K format directly.

Once data is converted into Signal K, you can display it in the different apps for visualization or convert it back to NMEA 0183 and 2000 to send it to other devices or apps.

## Data flow

![](.gitbook/assets/nav_data3.png)

## NMEA 0183

OpenPlotter can get NMEA 0183 data from connected serial devices \(USB, UART...\) or connecting to a TCP or UDP network sources.

Define serial devices on _Serial_ tab and network connections on _Kplex_ tab:

{% page-ref page="serial/" %}

{% page-ref page="kplex.md" %}

Signal K server gets NMEA 0183 data, converts all the NMEA 0183 sentences that it can understand into Signal K format and relays the raw NMEA 0183 data to TCP 10110 port.

If you have devices that generate NMEA 2000 or Signal K data and you want to translate it to NMEA 0183 and send it to TCP 10110 port too, you will have to enable the NMEA 0183 sentences you need in the _Convert Signal K to NMEA 0183_ plugin when they exist:

{% page-ref page="signal-k-server/signal-k-to-nmea-0183.md" %}

## NMEA 2000

To get and send NMEA 2000 data you need to connect a serial converted like our CAN-USB Stick. The Actisense NGT-1 is also supported.

{% page-ref page="can/can-usb-stick.md" %}

You have to define the serial device in _Serial_ tab and configure it in _CAN_ tab. If you have devices that generate NMEA 0183 or Signal K data and you want to translate it to NMEA 2000 and send it by your NMEA 2000 serial device, you will have to allow the reception for those PGN on your device and select what Signal K keys you want to transmit:

{% page-ref page="can/" %}

## SIGNAL K

Data from NMEA 0183 and 2000 defined devices are translated into Signal K automatically.

Raw data from IMU - GPIO - I2C - 1W - SPI sensors, MQTT and some tools are converted into Signal K after we define these items in their corresponding tabs.

{% page-ref page="pypilot/compass-calibration.md" %}

{% page-ref page="gpio/" %}

{% page-ref page="i2c/" %}

{% page-ref page="1w/" %}

{% page-ref page="spi/" %}

{% page-ref page="mqtt.md" %}

{% page-ref page="tools/analog-ads1115.md" %}

{% page-ref page="tools/analog-firmata.md" %}

If you want to convert Signal K data from these sources to NMEA 0183 or 2000, you need to check before if NMEA 0183 sentences or PGN for these data exist. See the previous sections to know how to do it.

