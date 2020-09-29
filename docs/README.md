> Currently tracking: API 1.0 (29/09/2020)

# 2020 4WC API

The API is a simple CSV plain text based API built on Tomcat.
This documentation assumes you already know the basic information about the API,
such as what it's for, the base URLs & how the game works.

These docs will (hopefully) be kept up-to-date during the challenge, providing more
standardised documentation, that is more concise & easier to read at a glance.

- Team Not a Name.

## Standardisation

This API always returns a 200 OK response when operating normally (i.e, the server isn't broken)

The API returns a CSV plain-text response, that can be viewed in a web browser. While the output
of the API isn't always standard, the first row of the CSV table is.

The first row of the table represents the request's result in the following schema:

[result, verbose_status]

If the request is successful, expect to see '"OK", "Okay"'

An example failure message could be: '"Invalid player name","You are not recognised: Please create or join a game."'

> NOTE: All endpoints use the GET HTTP method, even when sending data to the game server. Expect to send all data over query parameters within the URL.

> NOTE: The server does not support HTTPs, be aware of this while hand-typing the URLs into your applications.

> NOTE: There is no staging/testing/mock server available, so be careful when testing not to disturb other teams.

## Sending Data

As all requests are GET, there is no body to send with requests, instead, all data is sent in
the queries.

### Authentication
Any endpoints that require authentication will need to send the JSESSION token, that's sent after the endpoint name & before the queries start in the URI.

Example: `http://4wc.example.com/test/getMaps;jsessionid={YOUR_SESSION}?extraData={}`

## Standard Parameters

### AppID

Some endpoints require an AppID, this is a name used to identify your app. It should be the same everytime you send it and must start with your team number.

For example

`8A - HideNSeek Dev`

## Sections

This documentation is split up into multiple sections. These are different areas of the API.

### Maps

These endpoints are public access and don't require authentication. They give information about
the available maps on the game server. 

### Players

These endpoints get information about players in the game, be that the player of your game instance
or others players from other teams within the same lobby/game session. 

These endpoints require a session as they pull information about a specific game.

### Game

These endpoints are responsible for controlling the game session, such as creating, starting, seeing the status and stopping game sessions.
