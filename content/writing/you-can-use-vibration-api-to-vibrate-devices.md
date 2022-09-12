---
comments: true
date: "2019-06-11T00:00:00Z"
description: Use Vibration API to vibrate devices
summary: Use Vibration API to vibrate devices
categories:
- article
tags:
- javascript
title: "You can use Vibration API to vibrate devices"
---

You can use Vibration API to vibrate devices. The `Navigator.vibrate()` method pulses the vibration hardware on the device, if such hardware exists.

```
navigator.vibrate(200); // vibrate for 200ms
navigator.vibrate([100,30,100,30,100,30,200,30,200,30,200,30,100,30,100,30,100]); // Vibrate 'SOS' in Morse.
```