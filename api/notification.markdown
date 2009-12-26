---
layout: default
title: Notification API
---

The Notification API is used to send notification to devices that have enabled push notifications in your application. You don't have to [register the device](/api/device.html) with our service before sending a notification to it, because the backend will automatically do so if it finds that you haven't registered it beforehand.

### Send Notifications

This API method is for sending a notification to one or more device token and/or one or more device alias. You can specify an alert, a sound and/or a badge for the notification that will be sent.

**URL:**
`https://pushyapp.com/api/v1/notifications`

**Formats:**
`xml`, `json`

**HTTP Method(s):**
`POST`

**Parameters:**
* `tokens`. Required if not using `aliases`. Array of device tokens in [Rails Array Format](/docs/rails-array.html) that the push notification will be sent to.
* `aliases`. Required if not using `devices`. Array of device aliases in [Rails Array Format](/docs/rails-array.html) that will automatically be mapped to a registered device token. The notification will be sent to those mapped device tokens.
* `alert`. Optional. String of the alert text to show on the device's screen as part of the Push Notification.
* `sound`. Optional. String of the name of the sound file to play as part of the Push Notification. Must be inside of the main bundle.
* `badge`. Optional. Number to show in a red badge next to your application's icon which will be changed or set as part of the Push Notification.

### Send a Broadcast Notification

This API method will send a notification to every single device that you have registered using the [Device API](/api/device.html). You can specify an alert, a sound and/or a badge for the notification that will be sent.

**URL:**
`https://pushyapp.com/api/v1/notifications/broadcast`

**Formats:**
`xml`, `json`

**HTTP Method(s):**
`POST`

**Parameters:**
* `alert`. Optional. String of the alert text to show on the device's screen as part of the Push Notification.
* `sound`. Optional. String of the name of the sound file to play as part of the Push Notification. Must be inside of the main bundle.
* `badge`. Optional. Number to show in a red badge next to your application's icon which will be changed or set as part of the Push Notification.
