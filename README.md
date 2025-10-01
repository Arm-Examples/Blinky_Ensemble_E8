# Blinky Ensemble E8 Project

This **Blinky** project is a simple example that helps you checking basic tools and hardware setup.

## Project Structure

The project is generated using the [CMSIS-Toolbox](https://open-cmsis-pack.github.io/cmsis-toolbox/build-overview)
and is defined in [`csolution`](https://open-cmsis-pack.github.io/cmsis-toolbox/YML-Input-Format) format:

- [`M55_HE/M55_HE.cproject.yml`](./M55_HE/M55_HE.cproject.yml) defines the source files and the software components for
  the M55_HE core.

## Hardware Setup

For initial development, use the **PRG USB** port to power the board and to have access to the Secure Enclave using the
[SETOOLS](#programming-with-setools) and a user UART.

## J-Link

When using the J-Link debug adapter (connected to **PRG USB**), ensure that J-Link version 8.44 or higher is installed.

> Note:
> Currently, the J-Link drivers do not support the E8 family. For support, copy the files from
> [Alif's VS Code template](https://github.com/alifsemi/alif_vscode-template/tree/main/.alif) to the
> [JLinkDevices folder](https://kb.segger.com/J-Link_Device_Support_Kit#JLinkDevices_folder).

## Building the project

In the **CMSIS view**, use the build button (hammer icon) to build the project.

## Programming with SETOOLS

Go to the [Alif Software & Tools page](https://alifsemi.com/support/software-tools/ensemble/) and download the
appropriate SETOOLS V1.107.000 archive for your platform to a directory on your local machine.

To program the application on the DK-E8 board, run the **Program with Security Toolkit (select COM port)** VS Code
task: go to **Terminal - Run Task - Program with Security Toolkit (select COM port)**. Select the appropriate COM port.
This needs to be done only once. Subsequent times, you can run the **Program with Security Toolkit** VSCode task
instead.

## Debugging

In the **CMSIS view**, use the debug button to start a debug session.

## Operation

The M55 High Efficiency core toggles D4 and D6 RGB LEDs in a 500 ms interval (red/green/blue).

> Note:
> For STDOUT (printf output) set switch SW4 to position U4 (UART4). Use VS Code's **SERIAL MONITOR** to see the
> `printf` debug output (set ot 115200 baud).
