# Hacking on ESP32

## Setup

Ensure the [Arduino CLI](https://www.arduino.cc/pro/cli) is installed on your system and added to your `PATH`

Create a new configuration file `arduino-cli.yaml`:

```yaml

board_manager:
  additional_urls:
    - https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
    #- https://dl.espressif.com/dl/package_esp32_index.json

```

Update packages index:

```bash

> arduino-cli core update-index --config-file arduino-cli.yaml

```

Install Esp32 package:

```bash

> arduino-cli core install esp32:esp32

```

```bash

> arduino-cli board list

```

## Compile and Upload

List available boards:

```bash

> arduino-cli board list

```

Compile project:

```bash

> arduino-cli compile -b esp32:esp32:esp32-poe-iso -v .

```

Upload artifacts to board:

```bash

> arduino-cli upload -p /dev/cu.usbserial-144120 -b esp32:esp32:esp32-poe-iso .

```

## Debug and Inspect

Build and export to current project folder:

```bash

> arduino-cli compile -b esp32:esp32:esp32-poe-iso -v . -e

```

Inspect binaries in `build` folder:

```bash

> ll your-project-folder/build/esp32.esp32.esp32-poe-iso

> file your-project-folder/build/esp32.esp32.esp32-poe-iso/*

> nm -gU your-project-folder/build/esp32.esp32.esp32-poe-iso/your-project-folder.ino.elf

> nm -g your-project-folder/build/esp32.esp32.esp32-poe-iso/your-project-folder.ino.elf

> nm -a your-project-folder/build/esp32.esp32.esp32-poe-iso/your-project-folder.ino.elf

> objdump -TC your-project-folder/build/esp32.esp32.esp32-poe-iso/your-project-folder.ino.elf

> objdump -TC your-project-folder/build/esp32.esp32.esp32-poe-iso/your-project-folder.ino.elf

> objdump -a your-project-folder/build/esp32.esp32.esp32-poe-iso/your-project-folder.ino.elf

> nm -gU your-project-folder/build/esp32.esp32.esp32-poe-iso/your-project-folder.ino.elf

> nm -g your-project-folder/build/esp32.esp32.esp32-poe-iso/your-project-folder.ino.elf

> nm -a your-project-folder/build/esp32.esp32.esp32-poe-iso/your-project-folder.ino.elf

```

## Miscellaneous

* [TFT_eSPI -- An Arduino IDE compatible graphics and fonts library for 32 bit processors.](https://github.com/Bodmer/TFT_eSPI)
* [BlueCube is a open source project designed to allow remote control of a Freetronics 4x4x4 RGB LED Cube](https://neographophobic.github.io/BlueCube/download.html)
* [creatronic](https://www.creatroninc.com/)


