# CSS styling #
Once you wrote your HTML file with your Javascript code, you may want to add some CSS rules, in order change colors, size, positioning... It's very simple as you follow the naming convention to write your CSS file.

Pin **state buttons (LOW/HIGH)** are HTML `<button>`, and inherit the _button_ CSS style. Their **id are from _gpio0_ to _gpio53_**. There is also two classes for both low and high states, and also somes for non GPIO pins :
  * Default : Generic buttons
  * **LOW** : GPIO in low state
  * **HIGH** : GPIO in high state
  * GND : Ground
  * V33 : 3.3V
  * V50 : 5.0V
  * UART0
  * SPI0
  * I2C0
  * I2C1

With the included RPi header and expert webapps, you can also customize function button and descriptions :

Pin **function buttons (IN/OUT/...)** are also HTML `<button>`, with **id from _function0_ to _function53_**. Two classes are also used :
  * .FunctionBasic : Used when GPIO is Input or Output
  * .FunctionSpecial : Used when GPIO is in ALTx (default is hidden)

Pin **descriptions** are made of HTML div, with **id from _name0_ to _name53_**, with a single class :
  * .Description : Text on the left/right of each pin