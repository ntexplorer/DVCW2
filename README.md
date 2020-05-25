# CMT218 Coursework 2

## Dota 2 The International 2019 Heroes Data Visualization

## c1912705

### 1. About Dota 2 and The International 2019 (TI9)

Dota 2 is a multiplayer online battle arena (MOBA) video game developed and published by Valve. The game is a sequel to Defense of the Ancients (DotA), which was a community-created mod for Blizzard Entertainment's Warcraft III: Reign of Chaos and its expansion pack, The Frozen Throne. Dota 2 is played in matches between two teams of five players, with each team occupying and defending their own separate base on the map. Each of the ten players independently controls a powerful character, known as a "hero", who all have unique abilities and differing styles of play. During a match, players collect experience points and items for their heroes to successfully defeat the opposing team's heroes in player versus player combat. A team wins by being the first to destroy the other team's "Ancient", a large structure located within their base.

The International 2019 (TI9) was the ninth iteration of The International, an annual Dota 2 world championship esports tournament. Hosted by Valve, the game's developer, the tournament followed a year-long series of awarding qualifying points, known as the Dota Pro Circuit (DPC), with the top 12 ranking teams being directly invited to the tournament, which took place in August 2019 at the Mercedes-Benz Arena in Shanghai. In addition, six more teams earned invites through regional qualifiers played in July 2019.

### 2. Data Resources

All the dataset used for the visualization is retrieved from OpenDota, a volunteer-developed, open source platform providing Dota 2 data. It provides a web interface for casual users to browse through the collected data, as well as an API to allow developers to build their own applications with it. Data is collected through the Steam WebAPI, as well as replay parsing of.

![image-20200524235409044](https://i.loli.net/2020/05/25/QTnONexvqowbXdG.png)

The analysis focuses on the performance of all the 117 heroes chosen during the TI9 gaming event. The dataset is selected according to the following aspects:

- The ban/pick decision of each game;
- The damage dealt/received by each hero;
- The experience points (XP) and gold gained by each hero (per minute);
- The kills, deaths and assists contributed by each hero;
- The win rate of each hero.

Additionally, two sets of data have been attached to discover more information about this event:

- The win rate for both side of the game (Radiant and Dire);
- The average game duration of each team.

### 3. Data Cleansing

All the data retrieved is in the .csv format. For this case, Pandas is introduced for data cleansing and sorting.

#### 3.1 Ban/Pick Decision

For the ban/pick decision, the dataset is indexed with the "hero_id" column, while the others are indexed with the name of heroes called "localized_name". So another data file "hero_id" is picked to merge with "hero_banpick.csv"  to build the connection between the id and the name of heroes.

#### 3.2 Kills, Deaths and Assists

Simply displaying the numbers of kills, deaths and assists won't be able to show the trends of hero performance. Therefore, these three figures are processed with the KDA concept: (Kills + Assists) / Death to show a general performance of a hero.

#### 3.3 Merging

All the hero data has been merged into a .csv file "hero_data" to maintain consistency.

### 4. Data Visualization

#### 4.1 Dashboard

![image-20200525084651090](https://i.loli.net/2020/05/25/Enba4yuxH2j7vlY.png)

The heroes statistics dashboard is established as above. It contains one bar chart to show the ban/pick decision for heroes and three scatter plots to show the performance of each hero. All the diagrams are bound so that if the user selected one or more specific data they will be highlighted in all the plots:

![image-20200525085158963](https://i.loli.net/2020/05/25/OwZD129yJdeARo4.png)

From the ban/pick chart we could learn that the hero "Chen"  has been banned most frequently (201 times), while the hero "Shadow Demon" had the highest pick rate (141 times).

![image-20200525093527611](https://i.loli.net/2020/05/25/aICKdBy1oXPnLce.png)

![image-20200525093429855](https://i.loli.net/2020/05/25/me4E9CLT8kUPSqg.png)

And in total, the most popular hero during the TI9 event would be "Ember Spirit", who was involved in both ban and pick for 323 times!

![image-20200525094059375](https://i.loli.net/2020/05/25/gRZDXUMdYE56qs8.png)

As for the damage report, the hero "Arc Warden" has created a record of both dealing the most damage and receiving hardest strike. In the meantime, the hero "Zeus" dealt huge amount of damage while only took little by others, for Zeus is a ranged intelligence hero with powerful abilities to hit the enemies from a long distance.

![image-20200525094816419](https://i.loli.net/2020/05/25/acdS4Kr9v1eW2LV.png)

The KDA - Win Rate scatter plot shows the performance of each hero and the average win rate they possess. It can be noticed that the heroes like "Chaos Knight" and "Sniper" have made a good performance in the matches, which means more kills and assists while less deaths. However, there are still some exceptions like the hero "Huskar", whose ability is to cause damage to enemies by hurting himself, resulting in a lower KDA. But still, the win rate of "Huskar" is higher than 50%, making it a good choice in the TI9 event.

![image-20200525095407665](https://i.loli.net/2020/05/25/LZmiCVyN3BU2FWK.png)

The Gold and Experience scatter plot shows the farming capability of heroes. According to the chart, heroes like "Broodmother", "Anti-mage" and "Alchemist" who usually play the "scaling champion" role of the team get more resources and space in the game while the "support" heroes like "Lich" have less gold and lower level.

![image-20200525101221561](https://i.loli.net/2020/05/25/YqhWpjvwa9t3rZR.png)

##### 4.2 Additional Information

![image-20200525090216757](https://i.loli.net/2020/05/25/ZcyXUwEvGkPz5bB.png)

Apart from the statistics of the heroes, another scatter plot is created to show the relative connection between the win rate and the game duration of each team. Wilson Score measurement is used to measure the population probability of each team as well, which means the bigger the scatter is, the better evaluation the team has possessed.

For instance, the champion team, OG, has a average match duration of 2,054 seconds (34 minutes), which indicates that it is a team that would rather not stall the game but put their effort on middle-late stage. 

![image-20200525101544150](https://i.loli.net/2020/05/25/nAH6BsS3xVYTp5Q.png)

Moreover, a simple bar chart has been created to show the discrepancy between both side of the game. Since the map of Dota 2 is not axisymmetric, this bar chart indicates that the players of the Radiant may have possessed a little advantage than those of the Dire camp.

![image-20200525090322315](https://i.loli.net/2020/05/25/c3oVqYbJNn8RI4Q.png)

