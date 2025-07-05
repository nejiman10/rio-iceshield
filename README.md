# Hand Solderble rio-iceshield
Forked 6 Axis LinuxCNC-RIO Raspberry-PI FPGA-Hat - kicad project

[Origin](https://github.com/multigcs/rio-iceshield)

**experimental**

![rio-iceshield](./rio-iceshield.png)

![pcb](./pcb.png)

## software / gateware
https://github.com/multigcs/riocore



# to provide a clock signal for the FPGA:

```bash
gpio mode 7 clock
gpio clock 7 5000000
````

Note: Although 5 MHz is specified, this will actually generate an 18 MHz clock due to how the Raspberry Pi's hardware clock divider works.

Make sure `riocore/boards/IceShield/board.json` reflects this setting, for example:

```json
"clock": {
  "osc": "18000000",
  "speed": "29812000",
  "pin": "35"
}
```

WiringPi must be installed to use the `gpio` command.

You can download it from:
[https://github.com/WiringPi/WiringPi/releases/](https://github.com/WiringPi/WiringPi/releases/)
