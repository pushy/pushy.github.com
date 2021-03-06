---
layout: default
title: Device API
---

The Devices API is used to register devices (iPhones, iPod touches, etc) with our service. This step is optional, but registering devices will allow you to associate an alias with the device, which will make it easier for you to send a notification in the future.

### Register a Device

**URL:** `https://pushyapp.com/api/v1/devices`

**Formats:** `xml`, `json`

**HTTP Method(s):** `POST`

**Parameters:**
* `token`. Required. The Device Token of the device that you are registering.
* `alias`. Optional. An arbitrary alias to assign to the device that you are registering. If the alias has already been used by another device, an error will be returned.

