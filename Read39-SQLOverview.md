# SQL Overview 

## ATTRIBUTES OF PLAYER SQL TABLE
id: 1
player_api_id: 182477
player_name: Aaron Doyan
player_fifa_api_id: 192488
birthday: 12-06-1996
height: 182
weight: 187

## The SELECT Clause
``` sql
-- select every attribute from a player.
SELECT 
    * 
FROM 
    player

--this now returns every attribute from player table

-- Gives only player name and bday from select statement.
SELECT
    player_name, birthday
FROM
    player

```
## The WHERE Clause
``` sql

-- widdles down only the queries that have 
SELECT 
    *
FROM
    player
WHERE
    height=200
    AND
    weight>200
```

## The ORDER BY Clause
``` sql
SELECT 
    *
FROM
    player
    order by weight desc
    -- orders players by their weight, descending.
```

## The INNER JOIN Clause
``` sql
SELECT 
 -- first amount comes from player attributes sql table, second comes from player table.
    player_attributes.player_api_id, 
    player_attributes.date, 
    player_attributes.overall_rating

    player.player_name,
FROM
    Player_Attributes
    -- assign each player attribute id to equal the player's player api id.
    inner join player on Player_Attributes_id=player.player_api_id_
```
Video reference - https://www.youtube.com/watch?v=kbKty5ZVKMY

