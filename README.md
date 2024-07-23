# Mouse Debouncer
A small performant Windows "tray application" which suppresses false double clicks under the assumption that:
`false double click = elapsed time between last mouseup and current mousedown event <= threshold`

## Usage
1. Download the latest [release](https://github.com/1aTa/Mouse-Debouncer/releases).
2. Preferably create a shortcut, batch script, task, etc to set command-line options and/or to put it into the autostart.
3. Run as admin if you would like Mouse Debouncer to work in elevated programs.
4. *Test and customize the thresholds for the best possible experience.*
5. Enjoy!

NOTE: When clicking and dragging, it's possible that the initial MouseDown will trigger an erroneous second click, thus cancelling the subsequent drag. Unfortunately there's no software solution for this. If you notice your drag events are stopping suddenly, it's definitely time for new switches.

## Command-Line Options

`threshold` : min delay between clicks in milliseconds to trigger a double click (**def**: 50  **min**: 1  **max**: 500)

| Option | Parameter | Description |
| --- | :---: | --- |
| **-t** or **--threshold** | *\<threshold\>* | Sets the general double click threshold. (overridable by button specific options) |
| **-l** or **--left** | *[threshold]* | Enables monitoring and/or sets the threshold of the left mouse button. |
| **-r** or **--right**| *[threshold]* | Enables monitoring and/or sets the threshold of the right mouse button. |
| **-m** or **--middle** | *[threshold]* | Enables monitoring and/or sets the threshold of the middle mouse button. |
| **-b** or **--four** | *[threshold]* | Enables monitoring and/or sets the threshold of the 4th "back" mouse button. |
| **-f** or **--five** | *[threshold]* | Enables monitoring and/or sets the threshold of the 5th "forward" mouse button. |
| **-q** or **--qpc** | | Enables high-resolution time stamps for interval measurements. (<1µs vs 15.6ms) |

#### Examples:

`MouseDebouncer32.exe -t100 --middle -r80` =\> middle button: 100ms; right button: 80ms

`MouseDebouncer64.exe -q --four=75` =\> high-resolution time stamps; fourth button: 75ms

\* *If no button is specified, the left button will be automatically set.*

Credits to **[skeeto](https://github.com/skeeto)** for **[Optparse](https://github.com/skeeto/Optparse)**!
