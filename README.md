In this repo, a simple breakout board is made to include an IMU and a barometer.

IMU = LSM6DSV16XTR -> https://www.mouser.it/it/ProductDetail/STMicroelectronics/LSM6DSV16XTR?qs=MyNHzdoqoQLCWe%2FE3pkKcA%3D%3D
Barometer = MS5611-01BA03 -> https://www.te.com/commerce/DocumentDelivery/DDEController?Action=showdoc&DocId=Data+Sheet%7FMS5611-01BA03%7FB3%7Fpdf%7FEnglish%7FENG_DS_MS5611-01BA03_B3.pdf%7FCAT-BLPS0036

The idea is simple : create a breakout board with two common and low cost sensors that can easily be interfaced with FPGAs, Arduino, STM32, etc.

Some tips for this board : 
- Connectors : simple pin header, every Arduino starter pack has compatible cables.
- User LED : two user controlled LED are put inside this board
- Power on LED : there's an LED connected to the power section of every IC. 
  If something goes wrong with power connections, the LED is a simple, but yet effective way to debug
- TVS Diode : those connectors can easily have transient current peaks. Burn the ICs in not something I want, so this kind of protection is needed.
  Every TVS diode eats some voltage, so keep this in mind when you design your protection module!
- 4 Layer : this can be overkill, but to have a solid ground plane is always a good idea when you use sensible sensors like IMU and barometers.
  In this project the maximum frequency of communication is 5 MHz, so there is no danger for high frequency.   
