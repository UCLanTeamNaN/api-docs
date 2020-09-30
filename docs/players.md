# Get players in current game

Get's a list of all players in the a specific game/lobby session with their assigned colours. 

This does not require a session token, so can be used to get the status of any in-progress games.

**URL**: `/getPlayers`

**Method**: `GET`

**Session Required**: `No`

**Parameters**:

```
gameID - A valid gameID
```


## Success Response
**Status Code**: `200 OK`

**API Status Row**: `OK, Okay`

**Response**: Expect a list of the following schema, after the status row;

`Player Name, Player Colour`

> NOTE: This response may be empty!

> **NOTE: Invalid game IDs return OK with no results!**

## Failure Responses

**API Status Row**: `"Missing required parameter","One of the required parameters is missing."`

This response will be sent if you do not send the gameID parameter.

# Get Position

Get the position of the current player in their current game.

> NOTE: This endpoint takes no parameters as the session ID will be used to get this user's position.

**URL**: `/getPosition`

**Method**: `GET`

**Session Required**: `YES!`

## Success Response
**Status Code**: `200 OK`

**API Status Row**: `OK, Okay`

**Response**: Expect the following schema on line 2 of the responseText

```
New Location, yellow*, green*, red*
```

* Number of [colour] tickets available to the player.

## Failure Responses

Error responses have not yet been documented.