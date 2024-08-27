---
title: "ESP32 bootstrapping"
date: 2024-08-27T10:18:10+02:00
showAuthor: false
authors:
  - "marek-matej"
tags: ["ESP32", "ESP-IDF", "Zephyr"]
---

## 1. Introduction

Those acquainted with the ESP32 system-on-chip (SoC) family are well aware of the complexity involved in analyzing its booting process. From navigating the embedded ROM bootloader, facilitated by comprehensive tooling, to initiating the 2nd stage bootloader, which subsequently launches the user application, the procedure deviates significantly from that of more conventional microcontrollers, such as those employing ARM architecture.

In this article, I'll dive into the nitty-gritty of how the ESP32 SoC boots up. While booting up might sound straightforward, I'll be focusing on how it's done specifically within the popular Zephyr RTOS environment. Zephyr has become a go-to choice for many vendors, including Espressif, the brains behind the ESP32. So, let's roll up our sleeves and explore how these pieces fit together!

Main building blocks are:

- ROM code / loader
- esptool.py
- Bootloader



