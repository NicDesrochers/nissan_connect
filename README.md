# NissanConnect for Home Assistant

An unofficial integration for interacting with NissanConnect vehicles in Europe. Based on the work of [mitchellrj](https://github.com/mitchellrj/kamereon-python) and [tobiaswk](https://github.com/Tobiaswk/dartnissanconnect). I have no affiliation with Nissan besides owning one of their cars.

_Please note this integration is only for vehicles using the NissanConnect Services app, not NissanConnect EV or any other app._

If you find any bugs or would like to request a feature, please open an issue.

## Tested Vehicles
This integration has been tested with the following vehicles:
* Nissan Leaf (2022) [@dan-r]
* Nissan Qashqai (2021) 
* Nissan Ariya
* Nissan X-Trail (2024)
* Nissan Juke (2021)

## Supported Regions
* Europe
* Canada *** Work in progess @NicDesrochers

Currently only Nissan vehicles within Europe are supported.


## Update Time
Terminology used for this integration:
* Polling - the car is woken up and new status is reported. This is disabled by default, but can be enabled by setting the polling interval to a non-zero value
* Update - data is fetched from Nissan but the car is not woken up

Following the model of leaf2mqtt, this integration can be set to use a different polling time when plugged in. When HVAC is turned on the polling time always drops to once per minute.

To prevent excessive 12v battery drain when plugged in but not charging for extended periods of time, the polling interval reverts to the standard interval after 4 consecutive updates show the car as plugged in but not charging.
This logic was added to give the benefit of quicker response times on the charging status binary sensor, which can be especially useful when charging with load-balanced or 'smart' chargers.

## Translations
Translations are provided for the following languages. If you are a native speaker and spot any mistakes, please let me know.
* English
* Danish
* Dutch
* French
* German
* Italian
* Norwegian
* Polish
* Portuguese
* Russian
* Spanish

## Entities
This integration exposes the following entities. Please note that entities will only be shown if the functionality is supported by your car.

* Binary Sensors
    * Car Plugged In (EV Only)
    * Car Charging (EV Only)
    * Doors Locked
* Sensors
    * Battery Level
    * Charge Time
    * Internal Temperature
    * External Temperature
    * Range (EV Only)
    * Odometer
    * Daily Distance
    * Daily Trips
    * Daily Efficiency (EV Only)
    * Monthly Distance
    * Monthly Trips
    * Monthly Efficiency (EV Only)
* Climate
* Device Tracker
* Buttons
    * Update Data
    * Flash Lights
    * Honk Horn
    * Start Charge
