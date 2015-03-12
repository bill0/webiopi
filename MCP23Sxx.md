# MCP23Sxx series SPI GPIO Expander #

## Supported interfaces ##
  * [webiopi.devices.digital.GPIOPort](DIGITAL#GPIOPort.md)

## Python Constructor ##
Use following constructors if you want to create some MCP230xx from your Python scripts.
  * **MCP23S08(chip, slave)**
  * **MCP23S09(chip, slave)**
  * **MCP23S17(chip, slave)**
  * **MCP23S18(chip, slave)**

Parameters :
  * chip (optional, default=0): SPI Chip Enable number (0=CE0, 1=CE1)
  * slave (optional, default=0x20): MCP23Sxx slave address

```
from webiopi.devices.digital import MC23S17

# Setup a MC23S17 on SPI CE0 with slave address 0x20 (default)
mcp0 = MC23S17()
# or
mcp0 = MC23S17(chip=0, slave=0x20)

# Setup a MCP3008 on SPI CE0 with slave address 0x21
mcp1 = MC23S17(chip=0, slave=0x21)
```

## Configuration File syntax ##
Use following syntax to setup some MCP3000 in the webiopi service/command configuration file.
```
[DEVICES]
# Setup a MC23S17 on SPI CE0 with slave address 0x20 (default)
mcp0 = MC23S17
# or
mcp0 = MC23S17 chip:0 slave:0x20

# Setup a MCP3008 on SPI CE0 with slave address 0x21
mcp1 = MC23S17 chip:0 slave:0x21
```