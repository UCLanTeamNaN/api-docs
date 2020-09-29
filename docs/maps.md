# Get all maps

This endpoint returns a list of maps that are currently available on the server.

> HINT: Expect this to be empty, Nick is sneaky!

**URL**: `/getMaps`

**Method**: `GET`

**Session Required**: `No`

## Success Response

**Status Code**: `200 OK`

**API Status Row**: `OK, Okay`

Expect the following schema:
`map_name, round_count, round_count*`

> Note: There may (will) be multiple maps available, interate every row (minus the status row)

### map_name

Expect map_name to be a friendly name for the map that can be displayed to the user.

### round_count

Various maps have different amounts of playable rounds. After the name, expect an unlimited
number of round options, i.e 

`test_map, 3, 4, 5, 6`
or 
`test_map, 2`

## Failure Response

There are no known failure responses minus those from Apache TomCat, which should only
appear during outages of the API.