<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->


<!-- PROJECT LOGO -->
<br />
<div align="center">
  <h3 align="center">Waveshare with ESPHome tutorial</h3>
  <img alt="Static Badge" style="border-radius:16px" src="https://img.shields.io/badge/ESPHOME-000?style=for-the-badge&logo=esphome&logoColor=white">
  <img alt="Static Badge" style="border-radius:16px" src="https://img.shields.io/badge/HOME%20ASSISTANT-18BCF2?style=for-the-badge&logo=homeassistant&logoColor=white">
  <p align="center">
    A very simple and commented example of a waveshare e-ink three colors screen implemented with ESPHome.
  </p>
</div>

---

# Disclaimers:
## I don't cover the ESPHome initialization and usage. I suppose you already have ESPHome up and running on your device and server and know how to upload your binary.
## Red color needs another driver. ESPHome official ones don't cover it. Only black and white.

---

# What's your screen driver ?

Waveshare produced and still produces a lot of different screen. You need to know which one you have to make it work with ESPHome. **Here is a non-exhaustive list of screens**, taken from ESPHome website:
- 1.54in
- 1.54inv2
- 2.13in - not tested
- 2.13in-ttgo - T5_V2.3 tested. Also works for Wemos D1 Mini ePaper Shield 2.13 1.0.0 “LOLIN”
- 2.70in - currently not working with the HAT Rev 2.1 version
- ...
- 7.50in
- 7.50in-bV2 - also supports v3, B/W rendering only
- 7.50in-bV3 - display with the ‘(V3)’ sticker on the back, B/W rendering only
- 7.50in-bc - display with version sticker ‘(C)’ on the back, B/W rendering only
- 7.50inV2 - Can’t use with an ESP8266 as it runs out of RAM
- 7.50inV2alt (alternative version to the above 7.50inV2)
- 7.50in-hd-b

So how to know which screen you have ? Here is the semantic for the driver name you will need to use:

- **7.50in** is the size of the screen in inches. Then if you have a 4.2 inches, you will use a driver *starting* with `4.20in`
- **v2 or V2 or V3** is the version of the screen. Most of the time, you will find a sticker behind your screen with the version. Most of the time, versions are backward-compatible.
- **anything else (ttgo, b, bc, hd...)** is about specific models. `b` is the tricolors screens.

Let's take `7.50in-bV2`: it's the driver for the three colors, 7.5 inches, second version screen. This is the one I will use in this example as it's the one I have !

> **Go find your version on [ESPHome website](https://esphome.io/components/display/waveshare_epaper.html#configuration-variables)** (although it's not complete as of January 2024).

# Install the YAML

Copy the YAML file **and modify it** to suit your needs. You **need to modify it** as this example is made for a `7.50in-bV2` ! On smaller screen you will see nothing as elements would be out of the frame.

> Read carefully the comments in the YAML file. It's explaining everything you need to create a simple frame with icons, text and sensors from Home Assistant.

# Miscellaneous

- ESPHome driver works only for black and white. There is third-party drivers outthere that can work but I did not tried them.
- Three colours screens can take up to 30s to refresh. You will see it blink white and black a lot !

---

<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Some useful ressources to go further:

* [Weatherman from Madelena](https://github.com/Madelena/esphome-weatherman-dashboard/blob/main/weatherman.yaml)
* [Useful thread on Home Assistant](https://community.home-assistant.io/t/use-esphome-with-e-ink-displays-to-blend-in-with-your-home-decor/435428)

<p align="right">(<a href="#readme-top">back to top</a>)</p>