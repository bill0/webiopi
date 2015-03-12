# MCP492x series SPI Digital-to-Analog Converter #

## Supported interfaces ##
  * [webiopi.devices.analog.DAC](ANALOG#DAC_(Digital-to-Analog_Converter).md)

## Python Constructor ##
Use following constructors if you want to create some MCP492x from your python scripts.
  * **MCP4921(chip)**
  * **MCP4922(chip)**

Parameters :
  * chip (optional, default=0): SPI Chip Enable number (0=CE0, 1=CE1)

```
from webiopi.devices.analog import MCP4921, MCP4922

# Setup a MCP4922 on SPI CE0
mcp0 = MCP4922()
# or
mcp0 = MCP4922(chip=0)

# Setup a MCP4922 on SPI CE1
mcp1 = MCP4922(chip=1)
```

## Configuration File syntax ##
Use following syntax to setup some MCP492x in the webiopi service/command configuration file.
```
[DEVICES]
# Setup a MCP4922 on SPI CE0
mcp0 = MCP4922
# or
mcp0 = MCP4922 chip:0

# Setup a MCP4922 on SPI CE1
mcp1 = MCP4922 chip:1
```