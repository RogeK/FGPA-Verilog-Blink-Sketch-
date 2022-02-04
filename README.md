# First FPGA Program
## A LED BLinker

This repo contains Verilog code to blink an LED at a specified frequency.

## Project Requirements:
Design HDL code that will blink an LED at a specified frequency of 100 Hz, 50 Hz, 10 Hz, or 1 Hz. For each of the blink frequencies, the LED will be set to 50% duty cycle (it will be HIGH/ON for half the time). The LED frequency will be chosen via two switches which are inputs to the FPGA. There is an additional switch called LED_EN that needs to be ‘1’ to turn on the LED. The FPGA will be driven by a 25 MHz oscillator.

The frequency selector is as shown below:

If enable == 0:
  Led Drive Frequency = Disabled

### Switch 1 and Switch 2 Binary Combination

00 -> 100Hz

01 -> 50Hz

10 -> 10Hz

11 -> 1Hz

### Summary of Input and Output Pins

i_clock     ->  input ->  25MHz Clock


i_enable    ->  input ->  Enable Switch


i_switch_1  ->  input ->  Switch 1


i_switch_2  ->  input ->  Switch 2


o_led_drive ->  output->  Signal that drives the LED

There are 4 counter processes that run concurrently. This means that they are running at the exact same time. Their job is to keep track of the number of clock pulses seen for each of the different frequencies, even when the switches are selecting that particular frequency.

The switches serve to select the output to use. They create an asynchronous multiplexer. 
### Inputs of the Multiplexer
i)   100Hz Counter Process
ii)  50Hz Counter Process
iii) 10Hz Counter Process
iv)  1Hz Counter Process
v)   i_switch 1
vi)  i_switch 2


*Add the image of the frequency selection process, the multiplexer and the and gate


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
