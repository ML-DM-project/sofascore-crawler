<kbd>:soccer: SofaScore crawler </kbd>

Bộ dữ liệu về các trận bóng đá thu thập từ trang web [sofascore](https://www.sofascore.com/), sử dụng để huấn luyện cho mô hình dự đoán kết quả [football-predict](https://github.com/ML-DM-project/football-predict).

Mỗi bộ dữ liệu về 1 trận đấu bao gồm:
+ Thống kê chỉ số của 2 đội trong trận (statistic)
+ Đội hình thi đấu 2 đội (lineup)
+ Thông số đối đầu của 2 đội - những lần gặp nhau trước (h2h)
+ Thông số của đội trước trận đấu (pregame_form)
  
Ngoài dữ liệu về từng trận đấu, bộ dữ liệu cung cấp thông số chung của từng đội, vị trí trên bảng xếp hạng,...


## Dữ liệu về trận đấu
### Statistic
Dữ liệu về thống kê các chỉ số của 2 đội trong trận, theo từng hiệp đấu và cả trận. Cụ thể các trường thông tin sử dụng như sau:

+ Expected goals
+ Expected assists
+ Ball possession
+ Total shots
+ Shots on target
+ Shots off target
+ Blocked shots
+ Corner kicks
+ Offsides
+ Fouls
+ Yellow cards
+ Free kicks
+ Throw-ins
+ Goal kicks
+ Big chances
+ Big chances missed
+ Hit woodwork
+ Shots inside box
+ Shots outside box
+ Goalkeeper saves
+ Goals prevented
+ Passes
+ Accurate passes
+ Long balls
+ Crosses
+ Dribbles
+ Possession lost
+ Tackles
+ Interceptions
+ Clearances

Ví dụ
```json
{
      "period": "1ST",
      "groups": [
        {
          "groupName": "Expected",
          "statisticsItems": [
            { "name": "Expected goals", "home": "0.32", "away": "0.56" }
          ]
        },
        {
          "groupName": "Possession",
          "statisticsItems": [
            { "name": "Ball possession", "home": "33%", "away": "67%" }
          ]
        },
    ]
}
```


### lineup

Dữ liệu về đội hình của 2 đội trước trận, bao gồm thông tin các cầu thủ chấn thương cũng như điểm trung bình các cầu thủ.
+ player
+ avgRating
+ substitute
+ position
+ statistics
  + totalPass
  + accuratePass
  + totalLongBalls
  + accurateLongBalls
  + saves
  + minutesPlayed
  + touches
  + rating
  + possessionLostCtrl
  + goalsPrevented
  + totalClearance
 
Ví dụ

```json
  "home": {
    "players": [
      {
        "player": {
          "name": "José Sá",
          "slug": "jose-sa",
          "position": "G",
        },
        "avgRating": 0,
        "position": "G",
        "substitute": false,
        "statistics": {
          "totalPass": 18,
          "accuratePass": 5,
          "totalLongBalls": 15,
          "accurateLongBalls": 3,
          "saves": 3,
          "minutesPlayed": 90,
          "touches": 33,
          "rating": 6.7,
          "possessionLostCtrl": 13,
          "goalsPrevented": -0.7045,
          "totalClearance": 1
        }
      },
```
### h2h
Dữ liệu về những lần gặp nhau trước đây của 2 đội và huấn luyện viên, bao gồm số trận thắng, hoà, thua.
+ homeWins
+ awayWins
+ draws

Ví dụ
```json
{
  "teamDuel": { "homeWins": 4, "awayWins": 14, "draws": 2 },
  "managerDuel": { "homeWins": 1, "awayWins": 1, "draws": 0 }
}
```

### pregame form
Dữ liệu về tình trạng của đội trước trận đấu, như vị trí trên bxh hay kết quả 5 trận gần nhất.

+ avgRating
+ position
+ value
+ form

Ví dụ
```json
"homeTeam": {
    "avgRating": "6.98",
    "position": 15,
    "value": "3",
    "form": ["L", "L", "W", "L"]
  },
```

## Dữ liệu về đội bóng
### Statistic
Các trường chỉ số của đội bóng
- goalsScored
- goalsConceded
- ownGoals
- assists
- shots
- penaltyGoals
- penaltiesTaken
- freeKickGoals
- freeKickShots
- goalsFromInsideTheBox
- goalsFromOutsideTheBox
- shotsFromInsideTheBox
- shotsFromOutsideTheBox
- headedGoals
- leftFootGoals
- rightFootGoals
- bigChances
- bigChancesCreated
- bigChancesMissed
- shotsOnTarget
- shotsOffTarget
- blockedScoringAttempt
- successfulDribbles
- dribbleAttempts
- corners
- hitWoodwork
- fastBreaks
- fastBreakGoals
- fastBreakShots
- averageBallPossession
- totalPasses
- accuratePasses
- accuratePassesPercentage
- totalOwnHalfPasses
- accurateOwnHalfPasses
- accurateOwnHalfPassesPercentage
- totalOppositionHalfPasses
- accurateOppositionHalfPasses
- accurateOppositionHalfPassesPercentage
- totalLongBalls
- accurateLongBalls
- accurateLongBallsPercentage
- totalCrosses
- accurateCrosses
- accurateCrossesPercentage
- cleanSheets
- tackles
- interceptions
- saves
- errorsLeadingToGoal
- errorsLeadingToShot
- penaltiesCommited
- penaltyGoalsConceded
- clearances
- clearancesOffLine
- lastManTackles
- totalDuels
- duelsWon
- duelsWonPercentage
- totalGroundDuels
- groundDuelsWon
- groundDuelsWonPercentage
- totalAerialDuels
- aerialDuelsWon
- aerialDuelsWonPercentage
- possessionLost
- offsides
- fouls
- yellowCards
- yellowRedCards
- redCards
- avgRating
- accurateFinalThirdPassesAgainst
- accurateOppositionHalfPassesAgainst
- accurateOwnHalfPassesAgainst
- accuratePassesAgainst
- bigChancesAgainst
- bigChancesCreatedAgainst
- bigChancesMissedAgainst
- clearancesAgainst
- cornersAgainst
- crossesSuccessfulAgainst
- crossesTotalAgainst
- dribbleAttemptsTotalAgainst
- dribbleAttemptsWonAgainst
- errorsLeadingToGoalAgainst
- errorsLeadingToShotAgainst
- hitWoodworkAgainst
- interceptionsAgainst
- keyPassesAgainst
- longBallsSuccessfulAgainst
- longBallsTotalAgainst
- offsidesAgainst
- redCardsAgainst
- shotsAgainst
- shotsBlockedAgainst
- shotsFromInsideTheBoxAgainst
- shotsFromOutsideTheBoxAgainst
- shotsOffTargetAgainst
- shotsOnTargetAgainst
- blockedScoringAttemptAgainst
- tacklesAgainst
- totalFinalThirdPassesAgainst
- oppositionHalfPassesTotalAgainst
- ownHalfPassesTotalAgainst
- totalPassesAgainst
- yellowCardsAgainst
- throwIns
- goalKicks
- ballRecovery
- freeKicks

Ví dụ
```json
"statistics": {
    "goalsScored": 32,
    "goalsConceded": 14,
    "ownGoals": 0,
    "assists": 21,
    "shots": 193,
}
```

## Run project
### Requirements
- Golang >= 1.17
  
### Instructions
```bash
$ go mod tidy
$ cp .env.example .env
$ go run .
```
Go to `output` folder to see the results.

### Notes

use `./delete_folders.sh` to delete folders with no matches
