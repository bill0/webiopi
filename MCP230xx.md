# MCP230xx series I2C GPIO expander #

## Supported interfaces ##
  * [webiopi.devices.digital.GPIOPort](DIGITAL#GPIOPort.md)

## Python Constructor ##
Use following constructors if you want to create some MCP230xx from your python scripts.
  * **MCP23008(slave)**
  * **MCP23009(slave)**
  * **MCP23017(slave)**
  * **MCP23018(slave)**

Parameters :
  * slave (optional, default=0x20): I2C slave address

```
from webiopi.devices.digital import MCP23017

# Setup a MCP23017 on I2C slave 0x20 (default)
mcp0 = MCP23017()
# or
mcp0 = MCP23017(slave=0x20)

# Setup a MCP23017 on I2C slave 0x21
mcp1 = MCP23017(slave=0x21)
```

## Configuration File syntax ##
Use following syntax to setup some MCP230xx in the webiopi service/command configuration file.
```
[DEVICES]
# Setup a MCP23017 on I2C slave 0x20 (default)
mcp0 = MCP23017
# or
mcp0 = MCP23017 slave:0x20

# Setup a MCP23017 on I2C slave 0x21
mcp1 = MCP23017 slave:0x21
```