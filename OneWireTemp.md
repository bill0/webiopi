# 1-Wire Temperature sensor #

## Supported interfaces ##
  * [webiopi.devices.sensor.Temperature](SENSOR#Temperature.md)

## Python Constructor ##
Use following constructors if you want to create a 1-Wire Temperature sensor from your python scripts.
  * **DS1822(slave)**
  * **DS1825(slave)**
  * **DS18B20(slave)**
  * **DS18S20(slave)**
  * **DS28EA00(slave)**

Parameters:
  * slave (optional) : 1-Wire slave address

```
from webiopi.devices.sensor import DS18B20

# Setup a DS18B20 with 1-Wire slave auto-detect
tmp0 = DS18B20()

# Setup a DS18B20 with 1-Wire slave 28-0000049bc218
tmp1 = DS18B20(slave="28-0000049bc218")
```

## Configuration File syntax ##
Use following syntax to setup a DS18B20 in the webiopi service/command configuration file.
```
[DEVICES]
# Setup a DS18B20 with 1-Wire slave auto-detect
tmp0 = DS18B20

# Setup a DS18B20 with 1-Wire slave 28-0000049bc218
tmp1 = DS18B20 slave:28-0000049bc218
```