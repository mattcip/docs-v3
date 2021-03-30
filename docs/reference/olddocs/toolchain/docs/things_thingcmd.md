# Connected Devices

The Zerynth Advanced Device Manager (ADM) allows connections between the devices programmed with Zerynth and the ADM sandbox instance hosted on the Zerynth backend server.
The ADM adds to each connected device the following functionalities:


* executing functions triggered by a remote request (remote procedure call)


* performing over the air firmware update (FOTA)


* displaying and interacting with a graphical user interface both on a mobile app or desktop browser

Such functionalities can be configured and controlled through the following ZTC commands:


* Create a connected device


* Retrieve info on a connected device


* Set properties of a connected device


* Retrieve the list of connected devices


* Create groups of devices


* Add a connected device to a group


* List groups of devices


* Create a graphical template


* Update a graphical template


* List all graphical templates


* Prepare for a FOTA update


* Check for FOTA status


* Start a FOTA update


* Stop a FOTA update

Details about the ADM can be found here.

## Create a connected device

In order to connect a physical device to the ADM, a bit of device provisioning must be made. In particular, a new connected device
instance must be created on the ADM and the assigned credentials used in the script running on the physical device.

The command:

```py
ztc thing add name
```

creates a new connected device instance with name `name` in the ADM server. Such instance can have many different properties, but only a subset of them is mandatory and generated by the ADM:


* `uid`: the unique identifier of the connected device


* `token`: the security token used to authenticate the physical device to the ADM

Additional properties can be specified at the moment of creation by specifying the corresponding options:


* `--location loc` adds the description of the location the physical device is placed


* `--lat lat --lon lon` attaches coordinates to the device


* `--description desc` specifies the device description


* `--tag tag` attaches a set of tags to the device (the option can be given multiple times)

Each Zerynth user can create an unlimited number of connected devices instances, however only a subset of them is allowed to be connected to the ADM at the same moment.

## Retrieves device info

The command:

```py
ztc thing info uid
```

retrieves information about the connected device with unique identifier `uid`.

The information retrieved consists of:


* `token`, the security token for the device


* `name`, the device name


* `description`, the device description


* `location`, the description of the device location


* `geo`, the latitude and longitude of the device position


* `groups`, the list of groups the device belongs to


* `last_seen`, the time of the last detected presence of the connected device


* `online`, the status of the device connection


* `platform`, the type of the physical device using this connected device credentials


* `notifications`, a boolean determing if mobile notifications are enabled for this device

## Configure a device

The command:

```py
ztc thing config uid
```

sets the properties of the connected device with unique identifier `uid`.

The properties are specified with the following options:


* `--name name`, changes the device name


* :option: –description desc, changes the device description


* `--location loc`, changes the device location


* `--lat x / --lon y`, change the device coordinates


* `--token`, asks for a new security token


* `--template template_uid`, sets the device template

## Connected devices list

The command:

```py
ztc thing config list
```

retrieves the list of connected devices. Options can be specified to filter the results:


* `--from n`, skips the first `n` connected devices. Default `n` is zero.


* `--status online/offline`, filters connected devices based on online status. If not given, all devices are retrieved

## Create a group of devices

The command:

```py
ztc thing group add name
```

creates a group named `name`, initially empty.
Devices can be added to the group with the config command.

## Group configuration

The command:

```py
ztc thing group config uid --add dev0_uid --remove dev1_uid
```

can be used to add or remove devices (identified by their uids `dev0_uid` and `dev1_uid`) to the group identifiedby `uid`.

The options `--add` and `--remove` can be repeated multiple times in the same command.

## Group configuration

The command:

```py
ztc thing group list
```

retrieves the list of all groups. The option `--from n` can be used to skip the first `n` groups.

## Create a device template

The Zerynth ADM allows to remotely store a graphical interface for each connected device called device template.
A template is just a collection of HTML5, javascript, css and image files hosted on the ADM backend. The template is
able to receive and send messages to the connected device in response to user interactions with its graphical components.

The command:

```py
ztc thing template add name
```

creates a new empty template named `name`. A template is identified by a generated uid.

## Upload a template

A newly created template is empty. Files and subfolders can be added to the template with the following command:

```py
ztc thing template upload uid path
```

where `path` is the folder containing the template files and `uid` is the uid indentifying the template to update.

The files at `path` are compressed and transferred to the ADM backend. There are limitations on the size of a template and on the type of files
that can be uploaded. If the upload is successfull, the files previously associated with the template are erased permanently (no history is kept).

## Retrieve template list

The command:

```py
ztc thing template list
```

retrieves all the created templates. The option `--from n` skips the first `n` templates.

## Prepare a FOTA update

The command:

```py
ztc ota prepare device firmware
```

uploads to the ADM instance the correctly compiled and linked firmware update contained in the `firmware` file for device with uid `device`.
To correctly prepare a FOTA update refer to the link <ztc-cmd-link> command.

## Start a FOTA update

The command:

```py
ztc ota start device
```

signals the ADM to start the previously prepared FOTA update for device `device`.

## Stop a FOTA update

The command:

```py
ztc ota stop device
```

signals the ADM to stop the previously prepared or started FOTA update for device `device`.

## Check a FOTA update

The command:

```py
ztc ota check device
```

display the status of the FOTA process for `device`.
The displayed information is:


* `ota_support`, `True` if the connected device runs a FOTA enabled VM


* `bcslot`, the index of the slot the current bytecode is running on


* `vmslot`, the index of the slot the current VM is running on


* `vmuid`, the unique identifier of the running VM


* `ota_request`, a unique identifier specifying the ongoing FOTA update, empty if FOTA is not ongoing


* `ota_next_request`, a unique identifier specifying the FOTA update that will be started by the start command, empty if no FOTA has been prepared


* `ota_fail`, a message specifying the last failed FOTA update error message, empty if ok


* `last_ota`, the timestamp of last successful FOTA update
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjIyMjkwNzczLDExMDcyNjcwODldfQ==
-->