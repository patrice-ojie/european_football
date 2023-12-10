--Team Performance at Home Games
SELECT Team.team_long_name, Team.team_short_name, Match.season, Match.stage, Match.home_team_goal, Match.away_team_goal
FROM Match
INNER JOIN TEAM
ON Match.home_team_api_id = Team.team_api_id
WHERE Match.season="2015/2016"
ORDER BY Match.home_team_goal DESC;

--Team Performance at Away Games
SELECT Team.team_long_name, Team.team_short_name, Match.season, Match.stage, Match.away_team_goal, Match.home_team_goal
FROM Match
INNER JOIN TEAM
ON Match.away_team_api_id = Team.team_api_id
WHERE Match.season="2015/2016"
ORDER BY Match.away_team_goal DESC;

--Goal Difference
SELECT Team.team_long_name, SUM(Match.home_team_goal - Match.away_team_goal) AS GoalDifference
FROM Match
INNER JOIN Team
ON Match.home_team_api_id = Team.team_api_id
GROUP BY Team.team_long_name
ORDER BY GoalDifference DESC;

--Average Goals per Match in each League
SELECT l.name, AVG(m.home_team_goal + m.away_team_goal) AS AvgGoalsPerMatch
FROM League AS l
JOIN Team AS t 
ON l.id = m.league_id
JOIN Match AS m 
ON t.team_api_id = m.home_team_api_id OR t.team_api_id = m.away_team_api_id
GROUP BY l.name;

--Average Player Rating
SELECT Player.player_name, AVG(Player_Attributes.overall_rating) AS AVGRating
FROM Player
JOIN Player_Attributes
ON Player.player_api_id = Player_Attributes.player_api_id
GROUP BY Player.player_name
ORDER BY AVGRating DESC;
