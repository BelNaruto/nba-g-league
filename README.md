# NBA G League API

The **NBA G League API** provides comprehensive access to data related to the NBA G League, offering developers and sports enthusiasts a powerful resource to integrate detailed information into their applications. With a wealth of statistics, player data, game results, and team information, this API is perfect for building sports-related applications and analytics tools. This API can be found on [RapidApi](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/nba-g-league-api).

## Getting Started

1. **Sign Up**: Create an account on RapidAPI.
2. **Subscribe**: Select a pricing plan that fits your needs.
3. **API Key**: Obtain your unique API key to start making requests.
4. **Documentation**: Visit the [NBA G League API Documentation](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/nba-g-league-api) for detailed instructions on how to use the API.


## Key Features

- **Player Statistics**: Access up-to-date stats for individual players, including points, assists, rebounds, and more.
- **Team Information**: Retrieve details about teams, including rosters, standings, and performance metrics.
- **Game Results**: Get information on past and upcoming games, including scores and highlights.
- **Season Data**: Access historical data for different seasons, allowing for in-depth analysis and comparisons.


## Team Roster Endpoint

### Description
This endpoint retrieves the roster of players for a specific NBA G League team during a given season. The roster includes information about each player on the team, such as player names, positions, and other relevant details.

### Endpoint
`GET /team-roster`

### Parameters
- `teamId` (required): The unique identifier of the NBA G League team for which the roster is requested.
- `season` (optional): The season for which the roster is requested. Default value is '2024'.

### Response
The response contains a JSON object with the roster of players for the specified NBA G League team during the specified season, including details such as player names, positions, and other relevant information.

### Error Handling
- If the `teamId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `teamId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /team-roster?teamId=16&season=2024

{
  "roster_data": {
    // Roster information for the specified NBA G League team during the specified season
  }
}
```


## News Endpoint

### Description
This endpoint retrieves the latest news articles related to the NBA G League. The news articles cover various topics such as game previews, player updates, team announcements, and league events.

### Endpoint
`GET /news`

### Parameters
- `limit` (optional): The maximum number of news articles to retrieve. Default value is 17.

### Response
The response contains a JSON object with a list of the latest news articles related to the NBA G League, including details such as article titles, summaries, publication dates, and links to the full articles.

### Error Handling
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /news?limit=10

{
  "newsData": [
    // List of the latest news articles related to the NBA G League
  ]
}
```

## Team Players Endpoint

### Description
This endpoint retrieves a list of players belonging to a specific NBA G League team, based on the team's unique identifier (teamId). The list includes information about each player, such as their names, positions, and other relevant details.

### Endpoint
`GET /teamplayers`

### Parameters
- `teamId` (required): The unique identifier of the NBA G League team for which player information is requested.

### Response
The response contains a JSON object with a list of players belonging to the specified NBA G League team, including details such as player names, positions, and other relevant information.

### Error Handling
- If the `teamId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `teamId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /teamplayers?teamId=4

{
  "teamPlayersData": [
    // List of players belonging to the specified NBA G League team
  ]
}
```
## Team Info Endpoint

### Description
This endpoint retrieves information about a specific NBA G League team based on its unique team identifier (teamId). The information includes details such as team name, abbreviation, location, and other relevant data.

### Endpoint
`GET /teaminfo`

### Parameters
- `teamId` (required): The unique identifier of the NBA G League team for which information is requested.

### Response
The response contains a JSON object with details about the specified NBA G League team, including team name, abbreviation, location, and other relevant information.

### Error Handling
- If the `teamId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `teamId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /teaminfo?teamId=4

{
  "teamInfoData": {
    // Information about the specified NBA G League team
  }
}
```
## Team List Endpoint

### Description
This endpoint retrieves a list of NBA G League teams. The list includes information about each team, such as team names, abbreviations, and other relevant details.

### Endpoint
`GET /teamlist`

### Parameters
- `limit` (optional): The maximum number of teams to include in the list. Default value is 400.

### Response
The response contains a JSON object with details about NBA G League teams, including team names, abbreviations, and other relevant information.

### Error Handling
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /teamlist?limit=50

{
  "teamListData": {
    // List of NBA G League teams
  }
}
```


## Standings Endpoint

### Description
This endpoint retrieves the standings of NBA G League teams for a specific season and level group. The standings include information about the rankings and performance of teams within the specified season and level group, such as conferences or divisions.

### Endpoint
`GET /standings`

### Parameters
- `season` (required): The season for which the standings are requested (in YYYY format).
- `seasontype` (optional): The type of season. Default value is 2 (Regular Season).
- `level` (optional): The level group for which the standings are requested. Default value is '2' (conference).

### Available Options
- **Season Type:** 
  - 2: Regular Season
  - 5: Showcase Cup

- **Level Group:**
  - 2: Conference
  - 3: Division

### Response
The response contains a JSON object with details about the standings of NBA G League teams for the specified season and level group, including team rankings and performance metrics.

### Error Handling
- If the `season` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `season`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /standings?season=2024&seasontype=2&level=2

{
  "standingsData": {
    // Standings information for the specified season and level group
  }
}
```

## Scoreboard Endpoint

### Description
This endpoint retrieves the scoreboard of NBA G League events for a specific date. The scoreboard includes information about the games played on the specified year, month, and day, along with the scores of each game.

### Endpoint
`GET /scoreboard`

### Parameters
- `year` (required): The year for which the scoreboard is requested (in YYYY format).
- `month` (required): The month for which the scoreboard is requested (in MM format).
- `day` (required): The day for which the scoreboard is requested (in DD format).
- `limit` (optional): The maximum number of games to include in the scoreboard (default is 100).

### Response
The response contains a JSON object with details about the NBA G League games played on the specified date, including information about the teams playing and the scores of each game.

### Error Handling
- If any of the required parameters (`year`, `month`, `day`) are not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the missing parameters.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /scoreboard?year=2024&month=03&day=09&limit=10

{
  "scoreboardData": {
    // Scoreboard information for the specified date
  }
}
```

## Picks Endpoint

### Description
This endpoint retrieves information about picks made in a specific event of the NBA G League. Picks refer to selections made by teams during events such as drafts or trades. This endpoint provides details about which teams made which picks during the specified event.

### Endpoint
`GET /picks`

### Parameters
- `eventId` (required): The unique identifier of the event for which pick information is requested.

### Response
The response contains a JSON object with details about picks made during the specified event, including information about the teams involved and the players selected.

### Error Handling
- If the `eventId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `eventId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /picks?eventId=123456

{
  "picksData": {
    // Pick information for the specified event
  }
}
```

## Game Summary Endpoint

### Description
This endpoint retrieves the summary of a specific game in the NBA G League. The game summary provides a concise overview of key information such as the final score, leading scorers, team statistics, and notable events.

### Endpoint
`GET /summary`

### Parameters
- `eventId` (required): The unique identifier of the event for which the game summary is requested.

### Response
The response contains a JSON object with summarized information about the specified game, including the final score, leading scorers, team statistics, and notable events.

### Error Handling
- If the `eventId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `eventId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /summary?eventId=123456

{
  "gameSummaryData": {
    // Game summary data for the specified event
  }
}
```

## Box Score Endpoint

### Description
This endpoint retrieves the box score data for a specific event in the NBA G League. A box score provides a comprehensive summary of player and team statistics for a particular game, including points, rebounds, assists, turnovers, and other relevant metrics.

### Endpoint
`GET /boxscore`

### Parameters
- `eventId` (required): The unique identifier of the event for which the box score data is requested.

### Response
The response contains a JSON object with detailed box score information for the specified event, including player and team statistics.

### Error Handling
- If the `eventId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `eventId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /boxscore?eventId=123456

{
  "boxScoreData": {
    // Box score data for the specified event
  }
}
```
## Play-by-Play Endpoint

### Description
This endpoint retrieves play-by-play data for a specific event in the NBA G League. Play-by-play data provides detailed information about every play that occurs during a game, including scores, timeouts, fouls, substitutions, and other significant events.

### Endpoint
`GET /pbp`

### Parameters
- `eventId` (required): The unique identifier of the event for which play-by-play data is requested.

### Response
The response contains a JSON object with detailed play-by-play information for the specified event.

### Error Handling
- If the `eventId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `eventId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /pbp?eventId=123456

{
  "playByPlayData": {
    // Play-by-play data for the specified event
  }
}
```


## Player Information Endpoint

### Description
This endpoint retrieves detailed information about a specific NBA G League player, based on the player's unique identifier (playerId). The information includes player statistics, biographical details, career history, and other relevant data.

### Endpoint
`GET /player-info`

### Parameters
- `playerId` (required): The unique identifier of the NBA G League player for whom information is requested.

### Response
The response contains a JSON object with detailed information about the specified NBA G League player, including player statistics, biographical details, career history, and other relevant data.

### Error Handling
- If the `playerId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `playerId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /player-info?playerId=4576085

{
  "playerInfoData": {
    // Detailed information about the specified NBA G League player
  }
}
```

## Player Stats Endpoint

### Description
This endpoint retrieves statistical data for a specific NBA G League player, based on the player's unique identifier (playerId). The statistical data includes various metrics such as points, rebounds, assists, steals, blocks, and other performance indicators.

### Endpoint
`GET /player-stats`

### Parameters
- `playerId` (required): The unique identifier of the NBA G League player for whom statistical data is requested.

### Response
The response contains a JSON object with statistical data for the specified NBA G League player, including metrics such as points, rebounds, assists, steals, blocks, and other performance indicators.

### Error Handling
- If the `playerId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `playerId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /player-stats?playerId=123456

{
  "player_stats": {
    // Statistical data for the specified NBA G League player
  }
}
```

## Player Game Log Endpoint

### Description
This endpoint retrieves the game log for a specific NBA G League player, based on the player's unique identifier (playerId). The game log provides a chronological record of the player's performance in individual games throughout a specified season.

### Endpoint
`GET /player-gamelog`

### Parameters
- `playerId` (required): The unique identifier of the NBA G League player for whom the game log is requested.
- `season` (optional): The season for which the game log is requested. Default value is '2024'.

### Response
The response contains a JSON object with the game log for the specified NBA G League player, detailing their performance in individual games throughout the specified season. The game log typically includes statistics such as points, rebounds, assists, steals, blocks, and other relevant metrics.

### Error Handling
- If the `playerId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `playerId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /player-gamelog?playerId=123456&season=2024

{
  "player_gamelog": {
    // Game log for the specified NBA G League player
  }
}
```

## Player Advanced Stats Endpoint

### Description
This endpoint retrieves advanced statistical data for a specific NBA G League player, based on the player's unique identifier (playerId). Advanced statistics offer insights beyond traditional box score metrics, providing a deeper analysis of player performance.

### Endpoint
`GET /player-advancedstats`

### Parameters
- `playerId` (required): The unique identifier of the NBA G League player for whom advanced statistical data is requested.

### Response
The response contains a JSON object with advanced statistical data for the specified NBA G League player, offering insights into various aspects of their performance beyond traditional box score metrics.

### Error Handling
- If the `playerId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `playerId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /player-advancedstats?playerId=123456

{
  "player_advanced_stats": {
    // Advanced statistical data for the specified NBA G League player
  }
}
```

## Player Splits Endpoint

### Description
This endpoint retrieves split statistics for a specific NBA G League player, based on the player's unique identifier (playerId). Split statistics provide detailed information about player performance categorized by different criteria, such as per game, total, or per 48 minutes.

### Endpoint
`GET /player-splits`

### Parameters
- `playerId` (required): The unique identifier of the NBA G League player for whom split statistics are requested.
- `season` (optional): The season for which split statistics are requested. Default value is '2024'.
- `category` (optional): The category of split statistics to retrieve. Default value is 'perGame'. Available categories include perGame, total, and per48.

### Response
The response contains a JSON object with split statistics for the specified NBA G League player, categorized according to the chosen criteria (per game, total, or per 48 minutes).

### Error Handling
- If the `playerId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `playerId`.
- If the provided `category` parameter is not one of the accepted values (perGame, total, or per48), the endpoint returns a 400 Bad Request error with a message indicating the valid options.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /player-splits?playerId=123456&season=2024&category=perGame

{
  "player_splits": {
    // Split statistics for the specified NBA G League player
  }
}
```



## Schedule Endpoint

### Description
This endpoint retrieves the schedule of NBA G League events for a specific date. The schedule includes information about the games scheduled to take place on the specified year, month, and day.

### Endpoint
`GET /schedule`

### Parameters
- `year` (required): The year for which the schedule is requested (in YYYY format).
- `month` (required): The month for which the schedule is requested (in MM format).
- `day` (required): The day for which the schedule is requested (in DD format).

### Response
The response contains a JSON object with details about the NBA G League events scheduled for the specified date, including information about the teams playing and the start times of the games.

### Error Handling
- If any of the required parameters (`year`, `month`, `day`) are not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the missing parameters.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /schedule?year=2024&month=04&day=16

{
  "scheduleData": {
    // Schedule information for the specified date
  }
}
```

## Schedule by Team Endpoint

### Description
This endpoint retrieves the schedule of NBA G League events for a specific team during a given season. The schedule includes information about the games in which the specified team is participating, including opponent teams and game dates.

### Endpoint
`GET /schedule-team`

### Parameters
- `season` (optional): The season for which the schedule is requested. Default value is '2024'.
- `teamId` (required): The unique identifier of the NBA G League team for which the schedule is requested.

### Response
The response contains a JSON object with the schedule of NBA G League events for the specified team during the specified season, including details about opponent teams and game dates.

### Error Handling
- If the `teamId` parameter is not provided, the endpoint returns a 400 Bad Request error with a message prompting the client to provide the `teamId`.
- If an internal server error occurs during the execution of the request, the endpoint returns a 500 Internal Server Error along with an error message specifying the cause of the error.

### Example
```json
GET /schedule-team?season=2024&teamId=123456

{
  "schedule_data": {
    // Schedule information for the specified team during the specified season
  }
}
```

## Commonly Asked Questions

### 1. What kind of data can I access through the NBA G League API?
You can access player statistics, team information, game results, and season data.

### 2. How do I authenticate my API requests?
You must include your API key in the headers of your requests as detailed in the API documentation.

### 3. Are there usage limits for the API?
Yes, usage limits vary based on your chosen subscription plan. Check the RapidAPI dashboard for specifics.

### 4. Can I filter data by team or player?
Absolutely! The API provides endpoints to filter data by specific teams or players.

### 5. Is historical data available for past seasons?
Yes, the NBA G League API includes historical data for previous seasons, enabling comparisons and trend analysis.

For more information and to start using the NBA G League API, visit [NBA G League API on RapidAPI](https://rapidapi.com/example/nba-g-league-api).

