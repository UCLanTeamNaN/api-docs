# Create Game

This endpoint is used to create a new game.

**URL**: `/createGame`

**Method**: `GET`

**Session Required**: `No`

**Paramters**

```
playerName - Unique username for the player
mapName    - The selected map to use in this game
numRounds  - Number of rounds requested for this game/map
appID      - The name of your app, with team number.
```

## Success Response

**Status Code**: `200 OK`

**API Status Row**: `OK, Okay`

**Response:** Expect the following schema on the second row:

`SessionID, GameID`

### SessionID

This is the session token you should use when your user interacts with the game. It must be sent with any endpoints that require authentication.

> NOTE: It's recommended to store this ID in permanent storage, in case the app is relaunched.

### GameID

This ID is used to allow other players to join your game session. You should display this to the user.

## Failure Responses

Error responses have not yet been documented.

# Join Game

This endpoint allows your app to join an existing game, created with any other API-compliant client.

**URL**: `/joinGame`

**Method**: `GET`

**Session Required**: `No`

**Parameters**

```
playerName - Unique player username
appID      - Your app's name, including team number
gameID     - The ID of the game the user wishes to join
```

## Success Response
**Status Code**: `200 OK`

**API Status Row**: `OK, Okay`

**Response**: Expect a session ID on the second row of the response.


## Failure Responses

**API Status Row**: `"Choose another name","The player name is already taken, choose another name."`

Sent when a user tries to join a game with a username that's already in use.


# Start Game

This endpoint closes the lobby session and starts the game. 

**URL**: `/startGame`

**Method**: `GET`

**Session Required**: `YES!`

**Parameters**:

```
gameID - A valid game ID
```

## Success Response
**Status Code**: `200 OK`

**API Status Row**: `OK, Okay`

There is no response data, the game lobby should close & the game will begin.

## Failure Responses

**API Status Row**: `"Missing required parameter","One of the required parameters is missing."`

This response will be sent if you do not send the gameID parameter.

**API Status Row**: `"Cannot Join Game","That game does not have an open lobby"`

This response is sent if the gameID doesn't exist, or the game is not in the correct state for going into game mode (i.e, the game has already started).

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

# Get Game State

Get's the current status of the game, expected to be: `OPEN, FUGITIVE, DETECTIVE, OVER`, along with the current round number.

**URL**: `/getGameState`

**Method**: `GET`

**Session Required**: `YES!`

> NOTE: This endpoint doesn't require any parameters as the current game will be pulled from the user's session ID.

## Success Response
**Status Code**: `200 OK`

**API Status Row**: `OK, Okay`

**Response**: Expect the following schema on line 2:

```
Game_State*, Round*, Message*
```

> NOTE: The round number is not sent for some reason, expect an empty **STRING**

> NOTE: The message element is not always included in a response, I assume this is an API issue that needs resolving.

* - OPEN/FUGITIVE/DETECTIVE/OVER
* - The current round number, supposedly numeric but could be a string.
* - A possibly empty string (It is not currently documented what this will be used for.)

## Failure Responses

Error responses have not yet been documented.
