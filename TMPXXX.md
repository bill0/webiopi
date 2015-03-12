# TMP102, TMP75, TMP275 I2C Temperature sensor #

## Supported interfaces ##
  * [webiopi.devices.sensor.Temperature](SENSOR#Temperature.md)

## Python Constructor ##
Use following constructors if you want to create a TMPXXX from your python scripts.
  * **TMP102(slave)**
  * **TMP75(slave, resolution)**
  * **TMP275(slave, resolution)**

Parameters:
  * slave (optional, default=0x48) : I2C slave address
  * resolution (optional, default=12) : Resolution of the sensor, from 10 to 12 bits.

```
from webiopi.devices.sensor import TMP102, TMP275

# Setup a TMP102 with I2C slave address 0x48 (default)
tmp0 = TMP102()
# or
tmp0 = TMP102(slave=0x48)

# Setup a TMP102 with I2C slave address 0x48 (default)
tmp1 = TMP102(slave=0x49)

# Setup a TMP275 with I2C slave address 0x4A and 11 bits resolution
tmp2 = TMP275(slave=0x4A, resolution=11)
```

## Configuration File syntax ##
Use following syntax to setup a TMP102 in the webiopi service/command configuration file.
```
[DEVICES]
# Setup a TMP102 with I2C slave address 0x48 (default)
tmp0 = TMP102
# or
tmp0 = TMP102 slave:0x48

# Setup a TMP102 with I2C slave address 0x49
tmp1 = TMP102 slave:0x49

# Setup a TMP275 with I2C slave address 0x4A and 11 bits resolution
tmp2 = TMP275 slave:0x4A resolution:11
```