WebIOPi can be used as a Python library. It offers both Server and GPIO class.

After unpacking WebIOPi, you'll find the following code in examples/basic/webiopi\_basic.py, you can execute from two ways :
  * Foreground (debugging):
```
$ sudo python webiopi_basic.py
```

  * Background (production)
```
$ sudo ./webiopi_basic.daemon start
```

```
# Imports
import webiopi

# Retrieve GPIO lib
GPIO = webiopi.GPIO

# -------------------------------------------------- #
# Initialization part                                #
# -------------------------------------------------- #

# Setup GPIOs
GPIO.setFunction(1, GPIO.IN)
GPIO.setFunction(7, GPIO.OUT)
GPIO.setFunction(8, GPIO.PWM)
GPIO.setFunction(9, GPIO.PWM)

GPIO.output(7, GPIO.HIGH)
GPIO.pulseRatio(8, 0.5) # init to 50% duty cycle ratio
GPIO.pulseAngle(9, 0)   # init to neutral

# -------------------------------------------------- #
# Main server part                                   #
# -------------------------------------------------- #

# Instantiate the server on the port 8000, it starts immediately in its own thread
server = webiopi.Server(port=8000, login="webiopi", password="raspberry")
# or     webiopi.Server(port=8000, passwdfile="/etc/webiopi/passwd")

# -------------------------------------------------- #
# Loop execution part                                #
# -------------------------------------------------- #

# Run our loop until CTRL-C is pressed or SIGTERM received
webiopi.runLoop()

# -------------------------------------------------- #
# Termination part                                   #
# -------------------------------------------------- #

# Cleanly stop the server
server.stop()

# Reset GPIO functions
GPIO.setFunction(1, GPIO.IN)
GPIO.setFunction(7, GPIO.IN)
GPIO.setFunction(8, GPIO.IN)
GPIO.setFunction(9, GPIO.IN)
```