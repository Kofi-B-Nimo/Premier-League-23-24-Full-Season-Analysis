# Premier League 23/24 Full Season Analysis
Analyzing 2023/24 Premier League data across all 20 teams to understand how Man City clinched the title over Arsenal by just 2 points. Exploring match stats, player performance, and league-wide trends. (London is Blue!!)
Using the dataset below:

<a href = "https://www.kaggle.com/datasets/whisperingkahuna/premier-league-2324-team-and-player-insights"> Premier League Dataset</a>


# Step 1: Framing the Question — How Did Man City Win the Premier League?

This project is all about getting to the bottom of how Manchester City managed to win the Premier League over Arsenal. Before diving into any data, I’m starting by figuring out what questions I need to ask — the areas I want to explore to really understand what made the difference.

Here’s what I’m looking into for Step 1:

---

##  What I Want to Know

### 1. **Offensive Performance**
- How did each team perform going forward?
- Who scored the most?
- What were shot totals, chance creation, and conversion rates like?

### 2. **Defensive Performance**
- How solid were teams at the back?
- Who conceded the fewest goals?
- What do clean sheets, tackles, and defensive structure look like across the board?

### 3. **Arsenal vs Manchester City**
- Side-by-side comparison of both teams
- What differences show up in the numbers?
- Did consistency, depth, or decision-making set City apart?

---

From here, I’ll start gathering data and looking for patterns — but defining the right questions comes first.

# Step 2: Organizing the Data

Now that I’ve defined what I want to look into, the next step is getting the data into shape. I’ve grouped all the datasets into three main categories based on what they tell me:

---

## Offensive
These datasets cover attacking output — chance creation, goals, possession, and touches in the box.

- `big_chance_team.csv`  
- `player_expected_assists.csv`  
- `player_expected_goals.csv`  
- `possession_percentage_team.csv`  
- `team_goals_per_match.csv`  
- `touches_in_opp_box_team.csv`  

---

## Defensive
These give insight into how well teams protected their goal and disrupted attacks.

- `clean_sheet_team.csv`  
- `goals_conceded_team_match.csv`  
- `saves_team.csv`  
- `won_tackle_team.csv`  

---

## Disciplinary
Focused on fouls, cards, and whether discipline played a role in team performance.

- `player_fouls_committed.csv`  
- `player_yellow_cards.csv`  
- `total_yel_card_team.csv`  

‼️ **Note:** ‼️
I originally had both `total_yel_card_team.csv` and `total_red_card_team.csv`, but they were identical — so I dropped the red card file to avoid redundancy.

---

## 📊 League Tables
Lastly, I’ve got two overview datasets:

- `pl_table_2023_24.csv`: Final standings from the Premier League season  
- `pl_table_xg_2023_24.csv`: xG and xPoints projections — helpful for comparing expected vs actual performance

---

This structure should make it easier to explore patterns and build visuals as I dig deeper into Step 3.




