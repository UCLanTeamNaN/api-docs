# Get current challenge leaderboard

Get's the current list of teams & their scores.

**URL**: `/getLeaderboard`

**Method**: `GET`

**Session Required**: `No`

## Success Response
**Status Code**: `200 OK`

**API Status Row**: `OK, Okay`

**Response**: Expect the following schema

`team_name,team_points`

Expect team_points to be a float.

> NOTE: Some teams have been combined and or do not have their correct names in the database.
