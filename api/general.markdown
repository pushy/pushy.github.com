---
layout: default
title: Tips and Tricks
---

The API is fairly simple to implement into your applications and internal servers. Everything is done via HTTP requests to our API endpoints. Read on to learn a few tips and tricks that will help you while developing applications that use our API service.

### RESTful API
Our API is RESTful, which means that you'll need to use different HTTP request types to get to different functions. Below is a table showing the relations between request types and their CRUD (Create, Read, Update, Delete) counterparts.

<table>
	<tr>
		<th>Request Type</th>
		<th>Action</th>
	</tr>
	
	<tr>
		<td>GET</td>
		<td>show</td>
	</tr>
	
	<tr>
		<td>POST</td>
		<td>create</td>
	</tr>
	
	<tr>
		<td>PUT</td>
		<td>update</td>
	</tr>
	
	<tr>
		<td>DELETE</td>
		<td>destroy</td>
	</tr>
</table>

For more information about REST, read the [Wikipedia Article](http://en.wikipedia.org/wiki/REST) about it.

### Authentication
Requests to the API must be authenticated using HTTP Basic authentication unless otherwise noted. The username is the application key that you are requesting on behalf of.

The password varies depending on which API you are using. If you are using the Notification API, use the Application Push Secret as the password. If you are using any other API endpoint, use the Application Secret.

The reasoning for this is security &mdash; you'll be using the Application Secret inside of your application and you'll be sending Push Notifications from our server. There is a different password so that if a user were to somehow get a hold of your Application Secret, they would not be able to start broadcasting notifications to all of your users. (If this were to ever happen, regenerate your API tokens from the control panel).

{note:title=Warning!}Regenerating your API tokens will replace your current set of tokens. Your old set will *no longer function* for authentication. This means, among other things, that you'll need to submit a new update of your application to Apple that uses the new keys.{note}

### Testing the API
`curl` is a great command line utility that you can use to test out different API features. If you're on Mac OS X, it's already installed, and if you're using Linux, you'll be able to find it in your package repository.

Below is an example command that you might use to send a push notification:

`curl -u yourapplicationkey:yourapplicationpushsecret -X POST -d devices[]=somedevicetoken -d alert="Hello, World" http://pushyapp.com/api/v1/notifications`

The first argument is to configure the username and password to use for HTTP Basic Authentication. The second is to choose the request type to be used. In this case, it's POST, which means that it will be creating a new notification. Finally, the last two arguments specify POST keys and values to be sent with the request. Be sure to backslash escape the \[\] if necessary in your shell (change "\[\]" to "\\[\\]").

All of those arguments and more are documented in-depth in the CURL manual page. View it in your terminal with `man curl` or [read it in your browser](http://curl.haxx.se/docs/manpage.html).
