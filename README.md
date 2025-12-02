# MO-2 Gyroscope Verification Shield

<p align="justify">
The PCB is designed as a shield for the NUCLEO-F446RET6, mechanically capable of stacking directly on top of the development board. This configuration routes all power and communication signals from the microcontroller to the peripheral components without the need for external jumper wires.
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/206dffe4-860b-45ac-9ca2-0b5dbc8d0896" alt="Front Unsoldered" width="45%" />
  <img src="https://github.com/user-attachments/assets/91e1e1ca-c176-4a7b-9ecc-f973e7e51d45" alt="Back Unsoldered" width="45%" />
  <br>
  <img src="https://github.com/user-attachments/assets/232ae9b7-11c7-435b-97b0-31e3af91f822" alt="Soldered Standalone" width="45%" />
  <img src="https://github.com/user-attachments/assets/6c9c087a-cb1f-40df-8d60-bb1b3d2a744c" alt="Soldered with Nucleo" width="45%" />
  <br>
  <em>Figure 1: PCB manufacturing and integration stages.</em>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/5fd0175e-166a-4228-8b12-8d14c6789988" alt="View 1" width="45%" />
  <img src="https://github.com/user-attachments/assets/c3a78c7e-711f-45dd-91de-6f2588e79f35" alt="View 2" width="45%" />
  <br>
  <img src="https://github.com/user-attachments/assets/461d132b-61a8-4ba9-aab4-143c359c0987" alt="View 3" width="45%" />
  <img src="https://github.com/user-attachments/assets/2c1c8680-ee29-4e7d-b62d-2c696ca22794" alt="View 4" width="45%" />
  <br>
  <em>Figure 2: Lateral profiles of the soldered system.</em>
</p>

<p align="justify">
The communication architecture relies on two distinct protocols: I<sup>2</sup>C for the Pmod gyroscope interface and SPI for the flash memory. Table 1 details the point-to-point wiring between the Pmod J2 connector and the NUCLEO headers.
</p>

| Pmod Pin | Function | NUCLEO Pin |
| :--- | :--- | :--- |
| J2 Pin 5 | SCL | PB8 (I2C1_SCL) |
| J2 Pin 6 | SDA | PB9 (I2C1_SDA) |
| J2 Pin 7 | GND | GND |
| J2 Pin 8 | VCC | +3V3 |
<p align="justify"><em>Table 1: Pin mapping between Pmod Gyroscope (L3G4200D) and NUCLEO-F446RE.</em></p>

<p align="justify">
For the data logging subsystem, due to the complexity of the memory circuit, Table 2 lists only the utilized microcontroller pins. For complete electrical connections, refer to the schematic diagram in Figure 3.
</p>

| NUCLEO Pin (Function) |
| :--- |
| PB14 (SPI2_MISO) |
| PB15 (SPI2_MOSI) |
| PC7 (SPI2_SCLK) |
| PA4 (Chip Select) |
| GND |
| +3V3 (Flash Memory Power Supply) |
<p align="justify"><em>Table 2: NUCLEO-F446RE Pin assignment for SPI Flash Memory interface.</em></p>

<p align="justify">
The power subsystem is designed around an LM2596 step-down switching regulator. This component regulates the input voltage from a main battery pack—comprising two Lithium-Ion cells—to a stable 5V output required to power the NUCLEO board.
</p>

<p align="justify">
Additionally, the PCB integrates essential user interface components for operational control: a mechanical toggle switch for main power isolation, a status LED to provide visual feedback during algorithm execution, and a push-button connected via a long cable. The button serves as a manual logic input, facilitating control over the state of the system during the thermal chamber test setup.
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/22a3987d-3968-488e-9652-8988a2f942f0" alt="Electrical Schematic" width="100%" />
  <br>
  <em>Figure 3: Electrical Schematic of the MO-2 Gyroscope Verification Shield.</em>
</p>
