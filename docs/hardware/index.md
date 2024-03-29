## Welcome to 4ZeroPlatform

4ZeroPlatform is a plug-and-play data gathering, processing, and reporting solution for small and large enterprises who need to achieve full visibility and optimization of Industrial Processes.

4zeroPlatform is composed of:

-   4ZeroBox, a versatile data acquisition unit, based on 32-bit microcontroller programmable in Python thanks to Zerynth; while allowing to acquire data from the PLC via digital ports, filtering the data onboard to avoid bandwidth overload and waste of cloud resources – it also enables the installation and management of external sensors, for a full Industrial IoT experience;
-   The 4ZeroManager is a Cloud or “on-premise” system for device and data management and integration with ERP, MES and BI tools; it allows to provision each device for a correct configuration, to send commands or firmware updates over the air (FOTA), to receive data for aggregation and subsequent analysis, and to foward data and events to third party services based on Azure, IBM cloud, Google IoT and others.

4ZeroPlatform is a tool designed for Industry 4.0 solution providers and thanks to its versatility it can be adapted to any industrial context. 4ZeroPlatform lets the user choose the best installation strategy, adapting it to the specific industrial environment.

### 4ZeroPlatform Configurator

The 4ZeroPlatform Configurator is the tool that guides you during the installation of all the required software, drivers, libraries and tools needed for programming the 4ZeroBox and using the 4ZeroManager.

Download the 4ZeroPlatform Configurator and start the setup procedure by visiting:  [getting-started](https://www.zerynth.com/blog/docs/4zeroplatform/getting-started/).

### 4ZeroBox

The 4ZeroBox is a modular hardware electronic unit that simplifies the development of Industrial IoT applications allowing rapid integration with sensors, actuators, and Cloud services.

4ZeroBox mounts a powerful ESP32 Microcontroller by Espressif Systems (240MHz, 4Mb Flash, 512KB SRAM) and provides many onboard features like: a DIN-rail mountable case with industrial grade sensor channels, support for Wi-fi, Bluetooth, Ethernet, LoRa, CAN, RS485, RS232, SD Card, JTAG, I2C, SPI; last but not least, there are 2 on-board MikroBUS sockets to extend the 4ZeroBox with hundreds of MikroElektronika click boards (see “MikroBus Slots” section).

You can find more info about 4ZeroBox [here](https://www.zerynth.com/blog/docs/4zeroplatform/4zerobox/).

### 4ZeroManager

The 4ZeroManager is a device management service for organizing, monitoring, and remotely updating connected devices at scale.

The 4ZeroManager includes a web interface for the control of connected devices and for the customization of data forwarding toward other services (e.i. MES, ERP, BI tools, etc.) via REST API or MQTT connection.

The 4ZeroManager can be also extended on request with dedicated data processing services and visualization dashboards. You can find more info about how to use 4ZeroManager [here](https://www.zerynth.com/blog/docs/4zeroplatform/4zeromanager/).

### Programming Suite

The 4ZeroBox official programming framework is  [Zerynth](https://www.zerynth.com/).

Zerynth allows programming the 4ZeroBox applications in Python (or hybrid C/Python). Zerynth includes a compiler, debugger, and an editor, alongside tutorials and example projects for an easy learning experience.

The 4ZeroBox includes a Zerynth® Virtual Machine Premium License, thus it is programmable in Zerynth free and without limitations. Zerynth® and all the required libraries will be installed by the 4ZeroPlatform Configurator during the setup phase.

### API

Our services expose some RESTful API for developing external tools and platforms and integrate them with the 4ZeroPlatform. The full documentation can be found [here](https://docs.4zeroplatform.com/api/).

