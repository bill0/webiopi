# WebIOPi Irrigation System #

## Requirements ##
  * Raspberry Pi with Raspbian installed on SD Card
  * PiFace, IO PI, or any GPIO expander chip supported by WebIOPi
  * Irrigation Main/Master valve/channel must be wired to expander channel 0


## Installation ##
  * If not already done, install WebIOPi
    * See https://code.google.com/p/webiopi/wiki/INSTALL
  * Download Irrigation package at https://code.google.com/p/webiopi/downloads/
  * Create a folder somewhere on your Pi eg. /home/pi/irrigation
  * Copy files from irrigation archive in the previously created folder
    * /home/pi/irrigation
      * script.py  : WebIOPi Python script
      * index.html : HTML file containing UI structure
      * script.js  : Javascript code, loaded and used by index.html
      * style.css  : CSS style sheet, loaded and used by index.html
  * By default, PiFace/MCP23S17 is used, you can change it by editing script.py
    * Change mcp definition
    * You can also change CHANNELS variable to limit channels used
```
    mcp = MCP23017() # For IO PI
    CHANNELS = 16
```
  * Edit /etc/webiopi/config
    * in [SCRIPTS](SCRIPTS.md) section, add following :
```
    irrigation = /home/pi/irrigation/script.py
```
    * in [HTTP](HTTP.md) section, add/change doc-root variable :
```
    doc-root = /home/pi/irrigation
```
  * Ensure you don't have webiopi running, then start webiopi foreground in debug mode
```
  $ sudo /etc/init.d/webiopi stop
  $ sudo webiopi -d -c /etc/webiopi/config
```
  * Open your browser to http://raspberrypi:8000/


## Usage ##
![http://trouch.com/wp-content/uploads/2014/01/webiopi-irrigation.png](http://trouch.com/wp-content/uploads/2014/01/webiopi-irrigation.png)

### Mode : auto/manual ###
  * auto : activate master channel and each stations in sequence at a given time and days
  * manual : channels are manually activated

### Master : ON/OFF ###
  * Shows the state of master/main valve
  * In manual mode, click on the master button to activate all channels in sequence

### Start time ###
  * Define system activation time in automatic mode

### Week schedule ###
  * Click on each day button to enable or disable the system on these days in auto mode

### Channels buttons ###
  * Display the current state of each valve
    * ON  : Open
    * OFF : Close
    * W   : Waiting for previous channels finish
  * In manual mode, click on each button to activate channels immediately

### Channels sliders ###
  * Setup opening duration of each valve

## Customization ##
Edit index.html and style.css to customize the UI. You may also need to edit script.js in order to change button texts. You can see the customization made by Benjamin, a WebIOPi fan and donator.
![http://trouch.com/wp-content/uploads/2014/01/webiopi-irrigation-ben.jpg](http://trouch.com/wp-content/uploads/2014/01/webiopi-irrigation-ben.jpg)
