Usage
-----

Since we know the included 'main.c' blinker compiles successfully, we can test with <pre>./compile; ./erase; ./flash; ./clean</pre>

compile:
- Calls GCC directly on all .c files, including the necessary NRF SDK templates.
- Avoids 'make' complexity by forcing [tabula rasa](https://en.wikipedia.org/wiki/Tabula_rasa) builds.
- Links with the correct offsets for the S110 softdevice.

flash:
- The application is checked to see if it was linked against a SoftDevice.
- Both are then flashed to the chip.

erase:
- Erases both region0 and region1 areas, if defined.
- Erases the User Information Configuration Registers.

clean:
- Remove object files

Tests
-----
Using the [Nordic NRFGo Studio](http://www.nordicsemi.com/chi/node_176/2.4GHz-RF/nRFgo-Studio) both the SoftDevice and the application binaries were read from the flashed chip and successfully verified against the original hexfiles.

Requirements
------------

- [nRF51 SDK](https://www.nordicsemi.com/eng/Products/Bluetooth-R-low-energy/nRF51822)
- [An S110 SoftDevice, v6 preferred](https://www.nordicsemi.com/eng/Products/Bluetooth-R-low-energy/nRF51822)
- [SEGGER JLink](http://www.segger.com/jlink-software.html)
- [nRF51822 Evaluation Kit board PCA1001](http://www.nordicsemi.com/eng/Products/Bluetooth-R-low-energy/nRF51822-Evaluation-Kit)
- [GNU Tools for ARM](https://launchpad.net/gcc-arm-embedded)

In each case, there are multiple versions of these available. The code should be easily modifiable to support them.
