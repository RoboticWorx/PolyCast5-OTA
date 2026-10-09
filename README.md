<p align="center">
  <img
    src="https://raw.githubusercontent.com/RoboticWorx/PolyCast5/main/scripts/dev/pc5_wordmark.png"
    alt="PolyCast5"
    width="66%"
  />
</p>

# PolyCast5 OTA

Welcome to the official over-the-air (OTA) update channel for the PolyCast5!

This repository is where your PolyCast5 looks for new firmware. When a new release is published here, every device can download and install it over Wi-Fi with no cables or computer needed.

You can find some relevant links below:

* [**PolyCast5 firmware source.**](https://github.com/RoboticWorx/PolyCast5) The full open-source code these releases are built from.
* [**PolyCast5 official website.**](https://polycast5.com/) A graphical explanation of what you can do with it and how it works!
* [**PolyCast5 user documentation.**](https://polycast5.com/pages/docs) How to use it and unleash its full capabilities.
* [**PolyCast5 Firmware Updater.**](https://polycast5.com/pages/firmware-updater) Update or recover your device over USB, right from your browser.

# Updating Your PolyCast5

1. Connect to your Wi-Fi network at least once from the **Wi-Fi** menu.
2. Go to **Settings > Check for Updates**.
3. If a new version is available, press **RIGHT** to start the update (or **LEFT** to dismiss it).
4. Keep your device on while it downloads. It will restart into the new firmware automatically once it's done!

You can see which version you're running at any time under **Settings > System Info**.

_Note: If the progress gets stuck at 0%, reboot by pressing **HOME** and **RIGHT** together, then try again. If all else fails, you can always update over USB with the [Firmware Updater](https://polycast5.com/pages/firmware-updater)._

# Is It Safe?

Yes! Updates are designed so your PolyCast5 can't end up without working firmware.

* **Your data stays put.** Settings, saved networks, remotes, scripts, and everything else you've stored are untouched by an update.
* **Interrupted downloads are harmless.** The new firmware is written to a separate slot and is only switched to once the full image has downloaded and been verified. If anything fails along the way, your device simply restarts on the firmware it already had.
* **Automatic rollback.** If a new update crashes before it finishes starting up, your device automatically returns to the previous working version.
* **Secure downloads.** Everything is fetched over HTTPS with full certificate validation.

_Note: OTA updates replace the main firmware only. Occasional larger releases that change the flash layout or built-in assets (animations, images) require a one-time USB update through the [Firmware Updater](https://polycast5.com/pages/firmware-updater). You'll be told if this is needed._

# How It Works

Each time you check for updates, your PolyCast5 reads [`manifest.json`](manifest.json) from this repository:

```json
{
  "version": "1.0.0",
  "url": "https://github.com/RoboticWorx/PolyCast5-OTA/releases/download/latest/PolyCast5.bin",
  "size": 3092064,
  "info": "https://github.com/RoboticWorx/PolyCast5-OTA/releases/tag/latest"
}
```

* `version` - The firmware version of this release. An update is offered whenever it differs from the version your device is running.
* `url` - Where the firmware binary is downloaded from (the `PolyCast5.bin` asset on the [latest](https://github.com/RoboticWorx/PolyCast5-OTA/releases/tag/latest) release).
* `size` - The size of `PolyCast5.bin` in bytes, used for the on-screen progress bar.
* `info` - Text shown on your device's **Update Available!** screen.

# Licensing

_Code in this repository is licensed under [CC Attribution-NonCommercial-ShareAlike 4.0 International](https://github.com/RoboticWorx/PolyCast5/blob/main/LICENSE.md) ([canonical](https://creativecommons.org/licenses/by-nc-sa/4.0/))._

_Unless required by applicable law or agreed to in writing, this
software is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR
CONDITIONS OF ANY KIND, either express or implied._
