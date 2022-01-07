Portland Trail Blazers Roster Construction Cluster Analysis
================


# Introduction

The objective of this analysis is to cluster players in the NBA by their “true position” rather than the traditional PG/SG/SF/PF/C. The modern NBA has become “positionless” and players have been designated specific “roles” on the squad based on their performance. For example, Some athletic centers can now play point guard or in some cases an offense is designed around a specific player. We will seek to find what those “true positions” or clusters are and do some learning as to how those positions look like on different rosters. The key questions we hope to answer are the following:

What player types or “true positions” exist in the NBA and skills do they encompass?
How are winning teams constructed with these “true positions”?
Where on the floor are these clusters more efficient in terms of shooting?
How do these players effect "Win Probability intra-game?
How do we value these “true positions” in the NBA?
All of these questions, we will be comparing the Portland Trail Blazers to other teams in the NBA. Portland has a long standing history of making the playoffs. Since the inception of the franchise in 1970, the organization has made the playoffs 37 times including a 21 straight appearance streak from 1983 to 2003. Since 2010-11 season, The Portland Trail Blazers only missed the playoffs during the 2011-12 & 2012-13 season. They currently only the league’s longest consecutive playoff streak. Given all of that, other teams have eclipsed the Blazers in terms of championship success. The Blazers only conference titles were in 1977, 1990, and 1992. We will be examining where some of the shortcomings may have come from as a way to compare the Blazers to other comparable teams.

To identify “true positions”, we will first do a Principle Components Analysis from 36 variables that encompass a lot of common player statistics such as shooting (FG %, 3P %, etc), Assists, Steals, Blocks, Rebounding, and a number of efficiency metrics (VORP, EFG %). All of these stats are per game statistics. In order to prep the statistics, we need to “scale” the variables as to transform the variables to be all on the same scale. This is important so that not one variable is weighted more than the other just given that it would have a higher overall number. A Principle Components Analysis looks for variables that are highly correlated with each other and combines them into a new variable. This analysis will reduce the 36 variables to a few, highly correlated variables. This is helpful to identify clusters of “skillsets”. We can see the PCA Plot below how some of the variables start to cluster together.


<img src="https://github.com/qmaclean/main/PDX_Blazers_Cluster_Analysis/viz_images/nba_pca.png" width="50%" />


View of Blazer's Roster Construction over time

Playoffs & Salary data exported from Basketball Reference

Play-by-play data & Per Game data from HoopR and NBAStatR

Free Agency Salary data from Spotrac.com

Clusters were built using a PCA of 36 per game variables and those PCAs were inputted into a K-means model where 7 clusters were identified. 

Once the clusters were identified the remaining analysis was to look at Portland Trail Blazer performance. 
