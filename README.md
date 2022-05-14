# About

This is an ESPHome firmware for the Localbytes smart plug, which is sold pre-loaded with tasmota. This firmware supports the original 10A plug and the upgraded 13A plug. <a href="https://www.mylocalbytes.com/products/smart-plug-pm?variant=41600621510847">You can buy these smart plugs here</a>.

# Installation

To flash the ESPHome firmware over tasmota, first flash the <a hrf="https://github.com/JamesSwift/localbytes-plug-pm/releases/latest/download/minimal.bin">minimal</a> firmware using the tasmota web interface (as the full firmware is too big to fit in the free space left by tasmota). Then, connect to the hotspot and enter your wifi details. 

At this point you can use the "dashboard import" feature of esphome to take ownership of the device. The next time you hit install/update via the dashboard, the full firmware will be uploaded to the plug. 

Alternatively, if you don't want to import the plug to your ESPHome dashboard, connect to the hotpsot the device creates and use the web UI to flash the <a href="https://github.com/JamesSwift/localbytes-plug-pm/releases/latest/download/loalbytes-plug-pm.bin">full firmware</a> from the latest release.

# Calibration

Once you have flashed the new firmware onto your smart plug and connected it to home assistant, you may wish to calibrate your plug to improve it's accuracy. To calibrate your plug, you need another "known-good" smart plug or a calibration device.

Plug your new smart plug into the known-good smart plug, then plug a kettle, toaster, or other high-power appliance into it. From home assistant, go to `Developer Tools` > `Services`. Use the services `calibrate_current`, `calibrate_power`, and `calibrate_voltage` to report the real readings as given from the "known-good" device. (Don't forget to turn on the kettle/toaster and leave it to stabilize it's power usage for a moment before starting to copy the readings).