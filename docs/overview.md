> Currently tracking: API 1.0 (29/09/2020)

# API Overview

While testing your app, you may wish to create/join the game with another client, for this we've released
[API-Tool](https://github.com/UCLanTeamNaN/api-tool) - a Python script for interacting with the API.

## Standardisation

This API always returns a **200 OK** response when operating normally (i.e, the server isn't broken)

The API returns a CSV plain-text response, that can be viewed in a web browser. While the output
of the API isn't always standard, the first row of the CSV table is.

The first row of the table represents the request's result in the following schema:

`[result, verbose_status]`

If the request is successful, expect to see `"OK", "Okay"`

An example failure message could be: `"Invalid player name","You are not recognised: Please create or join a game."`

> NOTE: All endpoints use the GET HTTP method, even when sending data to the game server. Expect to send all data over query parameters within the URL.

> NOTE: The server does not support HTTPs, be aware of this while hand-typing the URLs into your applications.

> NOTE: Modern browsers (i.e Chrome) attempt to redirect to HTTPS://challenge, you must use an older browser (iexplore) or an API dev tool

> NOTE: Be careful not to disturb other teams while testing.


## Sending Data

Data is sent in the parameters of a GET request to the API.

### Authentication
Any endpoints that require authentication will need to send the JSESSION token, that's sent after the endpoint name & before the queries start in the URI.

Example: `http://4wc.example.com/test/getMaps;jsessionid={YOUR_SESSION}?extraData={}`

> NOTE: Some browsers (iexplore) and dev tools may store the jsessionid in their cookies, so you can probably leave this out of your requests made within those. api-tool stores the jsession token in a file named .sessiontoken

## Standard Parameters

### appID

Some endpoints require an appID, this is a name used to identify your app. It should be the same everytime you send it and must start with your team number.

For example

`8A - HideNSeek Dev`

> NOTE: It's important you get your appID correct as it's used to award points.

### playerName

The joinGame and createGame endpoints require a playerName, this should be a non-empty string that identifies the player in the game.

# Foot notes

## Failure messages

We haven't added all error messages to our system, but we'll work on adding them as we descover them. Pull requests are open if any other teams
wish to contribute to this documentation.




We hope this documentation & api-tool are useful to other teams, Team NaN.