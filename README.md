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

## League Tables
Lastly, I’ve got two overview datasets:

- `pl_table_2023_24.csv`: Final standings from the Premier League season  
- `pl_table_xg_2023_24.csv`: xG and xPoints projections — helpful for comparing expected vs actual performance

---

This structure should make it easier to explore patterns and build visuals as I dig deeper into Step 3.


# Step 3: Reviewing and Cleaning the Data

With my questions laid out and the data organized, this step was all about reviewing each dataset to see what’s actually useful — and trimming anything that doesn’t help answer the questions.

---

## What I Looked For
- Do the columns in each table directly support offensive, defensive, or disciplinary analysis?
- Are there duplicate or irrelevant columns bloating the data?
- Can any entire tables be removed?

---

## Cleanup Process
A lot of the tables included extra columns that didn’t serve the purpose of this analysis, so I trimmed them out.  
Here’s a quick example of what I did:

- `player_expected_assists.csv` → dropped unrelated columns  
  
  ![player expected assists column drop](https://github.com/user-attachments/assets/51b8cc1e-982d-4e30-ae01-23cc790a183d)

output:

![player expected assists column drop output](https://github.com/user-attachments/assets/84ec1dd4-b1df-4935-91c6-1f98bd3db5d7)

- `player_expected_goals.csv` → same process  

![player expected goals column drop](https://github.com/user-attachments/assets/5d374dfb-6282-4f99-af5f-678eb752335b)

output:

![player expected goals column drop output](https://github.com/user-attachments/assets/c16773fd-cbcd-44f4-bdc5-43834503e947)

This same column-dropping method was applied across all the other relevant datasets.

---

## Removed Tables
- **`total_red_card_team.csv`** was removed entirely since it duplicated the data in `total_yel_card_team.csv`.

![yellow card team table](https://github.com/user-attachments/assets/56a6aff0-264b-4621-9c1e-6acbb9a9c4b8)

dropping `total_yellow_card_team.csv`:

<img width="306" height="98" alt="DROP yellow card team" src="https://github.com/user-attachments/assets/c05a0632-a876-420f-bc04-307818c694c3" />

---

The goal here was to keep only the data that actually supports my offensive, defensive, disciplinary, or team comparison analysis — everything else had to go.



# Step 4: Joining the Data


## Step 4 Goals

- Join related tables and save them as new combined tables  
- Remove any repetitive or unnecessary columns after the join  
- Separate and structure the data based on **team stats** vs **individual stats** — this helped guide how joins were handled  

---

### 🛡️ Defensive Table

My first move was joining all the defensive-related tables into a single `team_defensive_stats` table. This gave me one place to analyze clean sheets, tackles, saves, and goals conceded.

> During this process, I realized I didn’t really need to trim the columns beforehand — I could’ve just selected the ones I needed while joining. But hey, now I know for next time. 😅

**Join Query:**

![Join Query - Defensive Stats](https://github.com/user-attachments/assets/f2aa79f1-ac29-4cac-a113-e1d6f5ed9002)

**Resulting Table:**

![Defensive Stats Output](https://github.com/user-attachments/assets/bd3d3c75-f41e-41ef-b0bd-f9821e0e616b)

---

### ⚔️ Offensive Table

Next up: combining the offensive-related datasets into a single `team_offensive_stats` table. This one includes metrics like goals per match, xG, big chances created, possession %, and touches in the opposition box.

**Join Query:**

![Join Query - Offensive Stats](https://github.com/user-attachments/assets/e708a789-b11b-4c70-b604-343e5a4c077a)

**Resulting Table:**

![Offensive Stats Output](https://github.com/user-attachments/assets/7feac32d-40d5-4d66-9cf5-823196d48e3a)

---

## 🧠 Takeaway

At this point, I’ve got clean, joined team-level tables for both defensive and offensive stats. From here, I’ll start visualizing trends and digging into the comparison between Arsenal and Man City.



# Step 5: Planning the Visual Story

---

This step is about making sense of all the data I’ve pulled together and figuring out how to organize it for clear, effective visual storytelling.

---

## Key Questions

1. Can I use multiple visuals to show how teams performed offensively and defensively?
2. What’s the best way to show a team’s offensive output in a complete, yet digestible way?
3. What’s the best way to show a team’s defensive output comprehensively?

---

## What I Have So Far

### Current Tables:
- `Team Offensive Stats`
- `Team Defensive Stats`
- `Players Yellow Cards`
- `Players Fouls Committed`
- `Total Red Cards`
- `PL Table 23/24`
- `PL Table xG 23/24`

---

## ⚔️ Offensive Metrics — Organized by Category

To visualize offensive performance clearly, I broke the metrics down into three core categories that represent different styles of attacking play:

### **1. Control of Possession**
- ✅ `Possession (%)`
- ✅ `Pass Success (%)`
- Accurate Passes per Match

### **2. Box Presence**
- ✅ `Shots on Target per Match`
- ✅ `Touches in Box per 90`
- Big Chances

### **3. Finishing**
- ✅ `Shot Conversion Rate (%)`
- ✅ `Goals per Match`
- Goals

Each category will be visualized using a **radar chart** — comparing all 20 teams on two carefully selected metrics per category.

---

## 🛡️ Defensive Metrics — Organized by Category

Just like the offensive side, I wanted to break defense down into components that reflect a full view of how teams defend:

### **1. Possession Recovery**
- ✅ `Possession Won Final 3rd per Match`
- ✅ `Interceptions per Match`

### **2. Defensive Disruption**
- ✅ `Successful Tackles per Match`
- ✅ `Tackle Success (%)`

### **3. Goal Prevention**
- ✅ `Saves per Match`
- ✅ `Goals Conceded per Match`

Each of these categories will also be visualized using radar charts, highlighting how teams compare defensively in different areas.

---

## 📊 Visualization Tool Update

‼️ **Heads up**: I was planning to use **Power BI** for visuals, but Power BI Desktop doesn’t support **radar charts** unless you're signed in with a pro account — not ideal.

✅ Instead, I’ll be using **Microsoft Excel** to create radar charts for the offensive and defensive breakdowns.

---

## 🧭 What’s Next

This visual structure sets me up to dive deeper into the **big question**:  
> *How did Manchester City edge Arsenal in this season’s title race?*

Radar charts will help me **compare the two clubs directly** across offensive and defensive categories — highlighting where the gap may have emerged.

Up next: I’ll walk through how I built these visualizations and what patterns start to emerge.










