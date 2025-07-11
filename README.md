# 4x4 RAM Design with Altera MAX+PLUS II

This repository contains the design files for a 4x4 (16-bit total, 4 words of 4 bits each) Static Random Access Memory (RAM) implemented using the Altera MAX+PLUS II development environment.

## Table of Contents

  * [Table of Contents](#table-of-contents)
  * [Introduction](#introduction)
  * [Features](#features)
  * [Design Files](#design-files)
  * [How to Open and Compile](#how-to-open-and-compile)
  * [Simulation and Verification](#simulation-and-verification)
  * [Block Diagram / Architecture](#block-diagram---architecture)
  * [Pinout](#pinout)
  * [Further Learning](#further-learning)
  * [Contribution](#contribution)
  * [License](#license)
  * [Contact](#contact)


## Introduction

This project demonstrates the fundamental design principles of a small-scale RAM using legacy Altera tools. The 4x4 RAM provides 4 memory locations, each capable of storing a 4-bit data word. It supports standard read and write operations.

## Features

  * **Memory Size:** 4 words x 4 bits (16 bits total)
  * **Addressing:** 2-bit address input for selecting one of the four words.
  * **Data Input/Output:** 4-bit data input and 4-bit data output.
  * **Control Signals:**
      * `CLK` (Clock): Synchronizes memory operations.
      * `WE` (Write Enable): Active high for write operations.
      * `OE` (Output Enable): Active high for read operations (controls tri-state buffer on output).
      * `RESET` (Optional): Global asynchronous reset to clear memory contents (if implemented).

## Design Files

The core design is implemented using [VHDL/AHDL/Graphical Design File (GDF)].

  * `Ram.vhd` (or `Ram.tdf` / `Ram.gdf`): The top-level design file for the 4x4 RAM.
  * `Ram.acf`: The Altera Configuration File, containing project settings, device assignments, and global compilation options for MAX+PLUS II.
  * `Ram.scf`: The Simulator Channel File, containing the waveform stimulus used for functional and timing simulation. This file allows you to re-run the exact simulations performed during development.


## How to Open and Compile

To open and compile this project, you will need the **Altera MAX+PLUS II** software.

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Roozbehsn/Ram-4-4.git
    cd Ram-4-4
    ```
2.  **Open MAX+PLUS II:** Launch the Altera MAX+PLUS II software.
3.  **Open the project:**
      * Go to `File` \> `Open Project`.
      * Navigate to the cloned `Ram-4-4` directory.
      * Select the `Ram-4-4.gdf` file and click `Open`.


## Simulation and Verification

The `Ram.scf` file is provided to verify the functionality of the RAM using the built-in simulator in MAX+PLUS II.

1.  **Open the project** as described above.
2.  **Open the Simulator:**
      * Go to `MAX+PLUS II` \> `Simulator`.
3.  **Load the waveform file:**
      * In the Simulator window, go to `File` \> `Open`.
      * Select the `Ram.scf` file and click `Open`.
4.  **Start the simulation:**
      * Click the `Start Simulation` button (green triangle).
      * The waveform viewer will display the input stimuli and the resulting output waveforms, demonstrating read and write operations.
      * Observe the `DATA_OUT` signal to confirm correct data storage and retrieval.

## Block Diagram / Architecture

*(Optional: Add a simple ASCII art block diagram or a link to an image of your RAM's internal structure here. For example:)*

```
+-------------------------------------------------+
|                    4x4 RAM                      |
|                                                 |
|  ADDR [1:0] --->|                               |<--- CLK
|                 |  Memory Core (4x 4-bit cells) |
| DATA_IN [3:0] ->|                               |
|                 |                               |---> DATA_OUT [3:0]
|           WE --->|                               |
|           OE --->|                               |
|       RESET --->|                               |
+-------------------------------------------------+
```

## Pinout

The following table summarizes the primary input and output pins of the 4x4 RAM. Pin assignments are managed within the `Ram.acf` file.

| Pin Name       | Direction | Description                                   |
| :------------- | :-------- | :-------------------------------------------- |
| `CLK`          | Input     | Clock signal                                  |
| `WE`           | Input     | Write Enable (active high)                    |
| `OE`           | Input     | Output Enable (active high)                   |
| `RESET`        | Input     | Asynchronous Reset (active high) - *if used* |
| `ADDR[1:0]`     | Input     | 2-bit Address Bus                             |
| `DATA_IN[3:0]` | Input     | 4-bit Data Input Bus                          |
| `DATA_OUT[3:0]`| Output    | 4-bit Data Output Bus                         |

## Further Learning

For a deeper theoretical understanding of RAM architectures, digital logic design, and memory concepts, you may find the following textbook helpful:

  * **"Digital Design" by M. Morris Mano and Michael D. Ciletti**
      * Look for chapters specifically discussing **Memory Units**, **Random Access Memory (RAM)**, and sequential circuits. This book provides excellent foundational knowledge on how memory works at a logic level.

## Contribution

Feel free to fork this repository, explore the design, and suggest improvements. If you find any issues or have enhancements, please open an issue or submit a pull request or you can contact me via rseyednozadi@gmail.com.

## License

This project is open-source and available under the [MIT License](https://www.google.com/search?q=LICENSE).
