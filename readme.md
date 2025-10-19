# TLP CPU Frequency Manager

Simple Python scripts to manage and apply `CPU_SCALING_MAX_FREQ_ON_BAT` and `CPU_BOOST_ON_BAT` options in TLP configuration file (`/etc/tlp.conf`) using simple commands.

# Setup

0. Install Python.
1. Place this project files inside the path `/usr/local/bin/tlp-zv`.
2. Create a file without extension in the path `/usr/local/bin/` with the name `tlpv` and add the following content:

```bash
#!/bin/bash
sudo python /usr/local/bin/tlp-zv/src/main.py "$@"
```

Now you can run the script using the command `tlpv` from any terminal.

# Usage

**Commands available**

| Command                 | Description                           |
| ----------------------- | ------------------------------------- |
| `bf <frequency as kHz>` | Set CPU maximum frequency on battery  |
| `af <frequency as kHz>` | Set CPU maximum frequency on AC       |
| `cf`                    | Display current running CPU frequency |

To set the CPU maximum frequency on battery (in kHz):

```bash
sudo tlp-zv bf <frequency_in_kHz>
```

Take into consideration that the value passed in `<frequency as kHz>` should be the value without five zeros. For example, to set the frequency to 1.6 GHz, you should pass `16`. The system adds the five zeros automatically.

# Design

- CPU: Intel i5-10210U
- OS: Linux Mint 21.2
- TLP version: 1.5.0

Scripts have not been tested on other hardware and software configurations.
