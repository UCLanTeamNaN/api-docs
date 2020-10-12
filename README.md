# UCLan 4WC API Documentation
A simpler, markdown version of the 4WC API documentation

These docs are not made to replace the provided docs, instead to compliment them with an easier to search, less information dense copy of the basic endpoints, parameters and returned values.
It includes some notes on implementation, but doesn't have instructions on using App Inventor with this API.

## Links

- [API Overview](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/overview.md)
- [Game Session Interaction](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/game.md)
- [Player Status Information](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/players.md)
- [Map Information](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/maps.md)
- [Leaderboard](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/leaderboard.md)

## Endpoints

- Maps
    - [getMaps](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/maps.md#get-all-maps)
- Game Sessions
    - [createGame](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/game.md#create-game)
    - [joinGame](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/game.md#join-game)
    - [getPlayers](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/game.md#get-players-in-current-game)
    - [startGame](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/game.md#join-game)
    - [getGameState](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/game.md#get-game-state)
    - [getDrXLog](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/game.md#get-drx-history-log)
    - [getPlayerDetails](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/game.md#get-player-locations-and-ticket-counts)
- Player Controls/Data
    - [makeMove](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/players.md#make-move)
    - [getPosition](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/players.md#get-position)
- Leaderboard
    - [getLeaderboard](https://github.com/UCLanTeamNaN/api-docs/blob/master/docs/leaderboard.md#get-current-challenge-leaderboard)

## Overview

The API is a simple CSV plain text based API built on Tomcat.
This documentation assumes you already know the basic information about the API,
such as what it's for, the base URLs & how the game works.

These docs will (hopefully) be kept up-to-date during the challenge, providing more
standardised documentation, that is more concise & easier to read at a glance.

Written by Team Not a Name for All Teams.

## Attribution

This documentation exists to make development of the 4WC app easier for those familiar with standard API documentation. 

These docs have a lot less information than the official ones provided by UCLan, but can be used as a quick reference while creating your game.

This documentation is based on the UCLan provided documents.

Written by Cameron Fleming @ Team NaN for everyone.
