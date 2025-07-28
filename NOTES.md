## Step 1

---

First step is to establish what questions I have or what I want to look into to fully understand  how it came to be that Man City won the premier League:

- How did teams fair offensively?
- How did teams fair defensively?
- Analyze disciplinary records for teams
- Compare Arsenal and Manchester city and use data to derive insights as to why Manchester City was able to edge Arsenal.

## Step 2

---

In this second step I'm thinking that I should organize the data into categories to to define the type of data they hold within them. The three main categories are as follows:

### Offensive
- big_chance_team.csv
- player_expected_assists.csv
- player_expected_goals.csv
- possession_percentage_team.csv
- team_goals_per_match.csv
- touches_in_opp_box_team.csv

### Defensive
- clean_sheet_team.csv
- goals_conceded_team_match.csv
- saves_team.csv
- won_tackle_team.csv

### Disciplinary
- player_fouls_committed.csv
- player_yellow_cards.csv
- total_red_card_team.csv 
- total_yel_card_team.csv ❌
     - (upon looking through the tables `total_yel_card_team.csv` and `total_red_card_team.csv` had the exact same data, makimg it redundant info, leading me to drop `total_red_card_team.csv`)
    

The remaining tables `pl_table_2023_24.csv` & `pl_table_xg_2023_24.csv` are  tables that show the final Premier League Table and the latter is a table holding predictive values for goals, points, and etc.

## Step 3

---

Third step in this process is to just see what data I have available to me, how it all relates to eachother or doesn't relate, if it helps me answer the questions i've posed and to essentially trim the fat if any tables dont aide me in this cause.

- my initial look through brought to my attnetion that majority of the tables had columns that really werent of any use when it came to my analysis so i started by trimming the fat there. Below are a couple screenshots of what I essentially did for all the tables:

dropping `player_expected_assists.csv` columns:

![player expected assists column drop](https://github.com/user-attachments/assets/51b8cc1e-982d-4e30-ae01-23cc790a183d)


output:

![player expected assists column drop output](https://github.com/user-attachments/assets/84ec1dd4-b1df-4935-91c6-1f98bd3db5d7)

dropping `player_expected_goals.csv` columns:

![player expected goals column drop](https://github.com/user-attachments/assets/5d374dfb-6282-4f99-af5f-678eb752335b)

output:

![player expected goals column drop output](https://github.com/user-attachments/assets/c16773fd-cbcd-44f4-bdc5-43834503e947)

- ⬆️ This was repeated throughout the database on all the various tables.

- As mentioned above, I had to get rid of the `total_yel_card_team.csv` due to duplicate information shared with `total_red_card_team.csv`:

Information included in `total_yel_card_team.csv`:

![yellow card team table](https://github.com/user-attachments/assets/56a6aff0-264b-4621-9c1e-6acbb9a9c4b8)


dropping `total_yellow_card_team.csv`:

<img width="306" height="98" alt="DROP yellow card team" src="https://github.com/user-attachments/assets/c05a0632-a876-420f-bc04-307818c694c3" />




## Step 4

---

I'm thinking my next step in this process is to:
- Join tables and save the joins as new tables
- further trim off any repetitive information or non-essential information
- differentiate tables between individual stats and team stats ( the basis on how the joins will be executed)


HEY!!👋🏿 I'M BACK, and im happy to say I finished what I set out to accomplish in step 4!

- My first task was to join the various defensive and offensive tables respectively into a singular defensicve and offensive table with statistics that were relevant to my research and also would help me tell the story that needed to be told.
  - during this process I realized that the "trimming" of columns I did earlier wasn't really necessary, during the table joining process, i could've just selected the columns I wanted from each table, inputting only what I needed, but hey, now I know.😅

Below is the query for the CREATE TABLE / JOIN for the defensive stats:

<img width="357" height="350" alt="JOINS for team_defensive_stats" src="https://github.com/user-attachments/assets/f2aa79f1-ac29-4cac-a113-e1d6f5ed9002" />

Team defensive stats output:

<img width="1282" height="521" alt="team_defensive_stats" src="https://github.com/user-attachments/assets/bd3d3c75-f41e-41ef-b0bd-f9821e0e616b" />


Below is the query for the CREATE TABLE / JOIN for the offensive stats:

<img width="366" height="387" alt="JOINS for team_offensive_stats" src="https://github.com/user-attachments/assets/e708a789-b11b-4c70-b604-343e5a4c077a" />


Team offensive stats output:

<img width="1353" height="522" alt="team_offensive_stats" src="https://github.com/user-attachments/assets/7feac32d-40d5-4d66-9cf5-823196d48e3a" />

## Step 5

---

This step will consist of trying to sift through all the data I have and understanding the best way to organize the data for it to be effectively visualized

Questions:
1) Can I have multiple graphics that display how teams faired offensively/defensively?
2) How can I accurately display a comprehensive depiction of a teams offensive output?
3) How can I accurately display a comprehensive depiction of a teams defensive output?

### Step 5.1

---

first I'll list out what I have so far, in terms of tables:
- `Team Offensive Stats`
- `Team Defensive Stats`
- `Players yellow cards`
- `Players fouls committed`
- `Toal red cards`
- `PL table 23/24`
- `Pl table xg 23?24`

---
- ⚔️ Team Offensive Stats:
     - Team
     - Big Chances
     - Goals
     - Possession (%)
     - Accurate Passes per Match
     - Pass Success (%)
     - Goals per Match
     - Total Goals Scored
     - Touches in Opposition Box
     - Shots on Target per Match
     - Shot Conversion Rate (%)
     - Touches in box per 90
 
For the offensive side of things breaking it down into 3 categories seemed like the best course of action; Control of Possession, Box Presence, and Finishing. I took the different columns within the table and oragnized them under those three categories to help figure out what 2 metrics under each category can effectively represent what I'm looking for.

Each category represents a graph that i'll be using to visualize the data, so below are the categories and how each metric was organized under each category.
(the selected metrics will be used to in in each chart)

Control of Possession
          - `Possession (%)`
          - Accurate Passes per Match
          - `Pass Success (%)`

Box Pressence
          - `Shots on Target per Match`
          - `Touches in box per 90`
          - Big Chances

Finishing
          - `Shot Conversion Rate (%)`
          - Goals
          - `Goals per Match`



That's the offensive side of things and now its lets tackle the defensive side of things!


- 🛡️ Team Defensive Stats:
     - Team
     - Clean Sheets
     - Goals Conceded per Match
     - Total Goals Conceded
     - Saves per Match
     - Total Saves
     - Tackle Success (%)
     - Successful Tackles per Match
     - Total Interceptions
     - Interceptions per Match
     - Possession Won Final 3rd per Match
 
Now for the defensive side of things, again I wanted to break it down into 3 categories that portrayed defense in an all-encompassing way. Defense was broken up into; Possession Recovery, Defensive Disruption, Goal Preventation. again I'll take the columns above and seperate them into te 3 categories below.

Each category represents a graph that i'll be using to visualize the data, so below are the categories and how each metric was organized under each category.
(the selected metrics will be used to in in each chart)

Possession Recovery
     - `Possession Won Final 3rd` 
     - `Interceptions per Match`

Defensive Disruption
     - `Successful Tackles per Match`
     - `Tackle Success (%)`

Goal Preventation
     - `Saves per Match`
     - `Goals Conceded per Match`



‼️The above ideas for charts will be put visualized in Power BI, but I have bad news; Power BI desktop doesn't have radar charts without a account to sign into. I'll be using Microsft Excel for the ability to utilize  radar charts.

- Radar Charts are pivotal for Visualizing because it allows for teams to be compared in a easily comprehended manner. Just a little tease initially, I'll first explain how I went about Visualizing the offensive and defensive metrics for all 20 teams and eventually tackle the overarching question of the project: How Manchester City edged Arsenal in this Title race through comparative analysis utilizing radar charts!

## Step 6
- During this step I'l go through why I used each visualization for each graph
- Once I've had had all the graph ideas sorted out, I plan to also display  the graphs seperated into 3 groups; 
     - `top 6`
     - `mid-table`
     - `bottom-table`










     
     









  




