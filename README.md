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


<img src="https://github.com/qmaclean/PDX_Blazers_Cluster_Analysis/blob/main/viz_images/nba_pca.png" width="50%" />

The “Scree Plot” is a useful visualization to show how much variance is explained in each newly constructed “PCA” variables. We can see the 1st dimension combined 37% of the variables into 1 dimension, the 2nd dimension is comprised of the 21.8% of the variables and so on. For our analysis, we will be using the first 6 dimensions as that encompasses 83.1% of the original variables. This is a sufficiently high percentage for us.

<img src="https://github.com/qmaclean/PDX_Blazers_Cluster_Analysis/blob/main/viz_images/pca_scree.png" width="50%" />

The following 6 charts help to explain what each of those newly constructed PCA variables are comprised of from the original variables. Our first (37.3% variance explained) is made up of “Scoring” variables. The 2nd (21.8% variance explained) is made up of “Rebounding” variables. As we notice from the “Scree Plot” from here the variables start to drop off in secondary variables and loose formations from the original variables. Our 3rd variable is comprised of Effective Field Goal Percentage (EFG %) and True Shooting Pct % (TSPercent). Our 4th variable is made up of “Defensive” metrics of Defensive Box Plus/Minus (DBPM) and “Steal Percentage”. The 5th and 6th variables are very specific with the 5th only really accounting for Free Throw Rate and the 6th being just Turnover Over Percent (TOV%) or Ball Handling. The combined variables can be thought of a “skillset” comprised of each true position.

<img src="https://github.com/qmaclean/PDX_Blazers_Cluster_Analysis/blob/main/viz_images/pca_contributions.png" width="50%" />

With our variables cleaned up and combined, we will now perform a K-means cluster analysis, a form of Unsupervised Machine Learning to reduce the rows of data into grouped clusters. This will help us identify how many “true positions” exist amongst all the players statistics. Essentially, the K-means iterates through to figure out the average of all PCA variables and helps to assign a cluster variable to players with similar average values across all inputted variables. In order to determine how many clusters exist, we can several different methods. We will be using a Sum of Square method to identify appropriate number of clusters amongst the data points. The goal of this percentage is to to say how much total variance of the data set can be explained by clustering. The overall goal of K-means is to minimize the within group dispersion and maximize the between-group dispersion. More simply put, it’s better to find a few broad clusters that can encompass many players than very specific clusters that would over-generalize their group fit.

The table below shows that at 7 clusters, we can account for a majority of the variance at 52% of the dataset. This figure is without the inputted PCA variables. 52% is a low enough number to account for the generality. These numbers also tell us that there a lot of players with very specific player profiles.

<img src="https://github.com/qmaclean/PDX_Blazers_Cluster_Analysis/blob/main/viz_images/k_means_in_between_ss.png" width="50%" />

View of Blazer's Roster Construction over time

Playoffs & Salary data exported from Basketball Reference

Play-by-play data & Per Game data from HoopR and NBAStatR

Free Agency Salary data from Spotrac.com

Clusters were built using a PCA of 36 per game variables and those PCAs were inputted into a K-means model where 7 clusters were identified. 

Once the clusters were identified the remaining analysis was to look at Portland Trail Blazer performance. 
