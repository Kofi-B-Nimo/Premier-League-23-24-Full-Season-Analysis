# 🏆 Premier League 23/24 Full Season Analysis

Analyzing the **2023/24 Premier League** season to understand how **Manchester City** clinched the title over **Arsenal** by just **2 points**. This project explores:
- Match stats
- Player and team performance
- League-wide offensive and defensive trends

> (London is Blue!! 💙)

📊 **Dataset**:  
[Premier League 23/24 — Team and Player Insights](https://www.kaggle.com/datasets/whisperingkahuna/premier-league-2324-team-and-player-insights)

---

## Step 1: Framing the Question — *How Did Man City Win the League?*

Before diving into the data, the focus was on crafting key analytical questions.

### What I Wanted to Know:

#### ⚔️ Offensive Performance
- Who scored the most?
- What were the shot totals and conversion rates?
- How effective was chance creation?

#### 🛡️ Defensive Performance
- Who conceded the fewest goals?
- Which teams kept the most clean sheets?
- What do defensive metrics (tackles, structure) look like?

#### ⚖️ Arsenal vs Man City
- What separates them statistically?
- Was it consistency, depth, or tactical control?

---

## Step 2: Organizing the Data

Grouped raw datasets into three clear categories:

### Offensive
- `big_chance_team.csv`  
- `player_expected_assists.csv`  
- `player_expected_goals.csv`  
- `possession_percentage_team.csv`  
- `team_goals_per_match.csv`  
- `touches_in_opp_box_team.csv`  

### Defensive
- `clean_sheet_team.csv`  
- `goals_conceded_team_match.csv`  
- `saves_team.csv`  
- `won_tackle_team.csv`
- `possession_won_att_3rd_team`

### Disciplinary
- `player_fouls_committed.csv`  
- `player_yellow_cards.csv`  
- `total_yel_card_team.csv`  
*(Removed `total_red_card_team.csv` due to redundancy)*

### League Tables
- `pl_table_2023_24.csv`
- `pl_table_xg_2023_24.csv` *(xPoints and xG metrics)*

[CSV files](https://github.com/Kofi-B-Nimo/Premier-League-23-24-Full-Season-Analysis/tree/main/CSV%20files)

---

## Step 3: Cleaning the Data

### Process:
- Dropped irrelevant or duplicate columns
- Removed full tables that provided redundant info
- Focused only on columns that supported offensive, defensive, or comparative analysis

Examples:
- Cleaned `player_expected_assists.csv` and `player_expected_goals.csv`  
- Removed `total_red_card_team.csv` (identical to yellow card data)

---

## Step 4: Joining the Data

### Team Defensive Table:
Joined clean sheets, saves, tackles, and goals conceded, etc. into one:
`team_defensive_stats.csv`

### Team Offensive Table:
Joined goals per 90, possession, passes, big chances, etc. :
`team_offensive_stats.csv`

Note: Trimmed unnecessary columns **after** joining — more efficient.

[New CSV Files](https://github.com/Kofi-B-Nimo/Premier-League-23-24-Full-Season-Analysis/tree/main/New%20CSV%20Files)

---

## Step 5: Planning the Visual Story

Organized metrics into **offensive** and **defensive** categories

### ⚔️ Offensive Metrics

#### 1. Control of Possession
- Possession (%)
- Pass Success (%)
- Accurate Passes

#### 2. Box Presence
- Touches in Box per 90
- Shots on Target per Match
- Big Chances

#### 3. Finishing
- Goals per Match
- Shot Conversion Rate (%)

---

### 🛡️ Defensive Metrics

#### 1. Possession Recovery
- Possession Won (Final 3rd)
- Interceptions

#### 2. Defensive Disruption
- Successful Tackles
- Tackle Success (%)

#### 3. Goal Prevention
- Clean Sheets
- Saves
- Goals Conceded

---

## Step 6: Data Visualizations

Grouped teams into **Top 6**, **Mid-table**, and **Bottom-table** to highlight trends clearly.

### ⚔️ Offensive Visuals

- **Line Chart**: Touches in Box vs Shots on Target  
- **Scatter Plot**: Goals vs Shot Conversion %  
- **Clustered Bar Chart**: Possession % vs Pass Success %

[Offensive Visualizations (screenshots)](https://github.com/Kofi-B-Nimo/Premier-League-23-24-Full-Season-Analysis/tree/main/Offensive%20Visualizations%20(screenshots))

---

### 🛡️ Defensive Visuals

- **Stacked Column Chart**: Interceptions + Possession Won  
- **Scatter Plot**: Saves vs Goals Conceded (marker = clean sheets)  
- **Dual Axis Chart**: Tackles per Match vs Tackle Success %

[Defensive Visualizations (screenshots)](https://github.com/Kofi-B-Nimo/Premier-League-23-24-Full-Season-Analysis/tree/main/Defensive%20Visualizations%20(screenshots))

---

## Step 7: Arsenal vs Manchester City

### 🔵 Manchester City:
- Dominates in possession, passing, big chances
- Expanded radar shape in offensive stats
- Precise, positional defense

### 🔴 Arsenal:
- Higher box presence (Touches in Box)
- Best in goals conceded, clean sheets
- More active in tackling & intercepting

💡 **Insight**:  
- City’s **volume** and control gave them the edge — even if Arsenal were equally clinical.  
- Arsenal was more active in traditional defense.  
- City showed **positional discipline** — fewer actions(defensively), more control.

Offensive Radar Chart:
<img width="1438" height="640" alt="offense radar chart" src="https://github.com/user-attachments/assets/e48cc177-2a27-45bd-84e0-37c9db541920" />

Defensive Radar Chart:
<img width="1442" height="645" alt="defense radar chart" src="https://github.com/user-attachments/assets/7d7c9763-9b0f-44f4-a900-b309d0332278" />


---

## Conclusion

Manchester City outperformed Arsenal in 6 of 8 key offensive metrics, excelling in goals, possession, passing accuracy, and big chances created. Their control-based style — driven by 65.4% possession and 625 accurate passes per game — enabled them to dictate play and consistently generate high-quality opportunities.

Arsenal matched City in shot conversion (13.9%) and slightly edged them in touches in the opposition box. However, City's superior ball control and tempo ultimately led to more goals (96 vs 91) — decisive in a title race settled by just 2 points.

Defensively, both teams were elite. Arsenal led in clean sheets and goals conceded, while City had a higher tackle success rate. Despite low interception stats, both clubs ranked top 2 in possession won in the final third — showing their ability to recover the ball high up the pitch and sustain pressure.

‼️In the end, it was City’s ability to control matches and edge small margins that crowned them champions


