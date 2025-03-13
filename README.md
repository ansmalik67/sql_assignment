# Sports Performance Database - README

## Overview
This project consists of a **sports performance database** designed for analyzing player performance, match results, and sponsorships using SQL. The database is structured to store **players, tournaments, matches, player performance, and sponsorships** with realistic data.

## Database Schema
The database consists of the following **tables**:

1. **Players**: Stores player details such as name, age, nationality, ranking, gender, and experience level.
2. **Tournaments**: Stores tournament details including name, location, year, and category.
3. **Matches**: Stores match results, linking players and tournaments.
4. **Performance**: Stores player performance per match, including points scored, fouls, and ranking changes.
5. **Sponsorships**: Stores sponsorship details for players, including contract value and duration.

## Data Inserted
- **Players**: 1000+ records of professional athletes.
- **Tournaments**: Various international and regional tournaments.
- **Matches**: Game results with real-world-like scores.
- **Performance**: Player performance statistics.
- **Sponsorships**: Companies sponsoring players with financial contracts.

## Sample Queries
### 1. **Check Players Without Performance Records**
```sql
SELECT P.player_id, P.name
FROM Players P
LEFT JOIN Performance Pr ON P.player_id = Pr.player_id
WHERE Pr.player_id IS NULL;
```

### 2. **Get Top 5 Players by Total Points Scored**
```sql
SELECT P.name, SUM(Pr.points_scored) AS Total_Points
FROM Players P
JOIN Performance Pr ON P.player_id = Pr.player_id
GROUP BY P.player_id
ORDER BY Total_Points DESC
LIMIT 5;
```

### 3. **List Tournaments with the Most Matches Played**
```sql
SELECT T.tournament_name, COUNT(M.match_id) AS Matches_Played
FROM Tournaments T
JOIN Matches M ON T.tournament_id = M.tournament_id
GROUP BY T.tournament_name
ORDER BY Matches_Played DESC;
```

## How to Use
1. **Load the database** into SQLite using DBeaver or Colab.
2. **Run SQL queries** to explore player stats and match analytics.
3. **Modify or extend** the dataset for additional analysis.

## Requirements
- **SQLite** (or any SQL-supported tool like DBeaver or Google Colab)
- **Python (Optional)** for generating additional randomized data.

## Notes
- Data has been **manually structured** to reflect realistic player statistics.
- The database is optimized for **efficient querying and analytics**.

## License
This project is open-source and can be modified for educational or research purposes.

---
**Author:** Ans Riaz
**Date:** March 2025  
**Contact:** ans.malik67@gmail.com

