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
Location
```

## Failure Responses

Error responses have not yet been documented.

# Make Move

This endpoint is used to move either the student or Mr. X to a new position. Can only be called on the players turn. 

> NOTE: Validation checks should be made in the app, to avoid wasting calls to the API.

**URL**: `/makeMove`

**Method**: `GET`

**Session Required**: `YES!`

**Parameters**:

```
destination - Destination number
ticket      - Ticket type [yellow, green or red]
```

## Success Response
**Status Code**: `200 OK`

**API Status Row**: `OK, Okay`

## Failure Responses

**API Status Row**: `Finished, It is not your turn to move`

Sent if the user is not able to move at the moment (waiting for another player to move)

**API Status Row**: `Finished, You don't have a ticket to make that move`

Sent if the user doesn't have the required ticket to move to that position (only sent to students, Dr. X has unlimited tickets)