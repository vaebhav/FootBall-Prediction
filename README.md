# FootBall-Prediction

As prediction is closely related to probability.

I have used Poisson distribution to estimate the probability of the goals being scored in a match.

As Poisson Distribution expresses the probability of a given number of events occurring in a fixed interval of time or space if these events occur with a known constant rate and independently of the time since the last event.

Known constant rate can be estimated as the average goals scored by each opponent team based on their home/away schedule and deducing their Attack and Defence Strength in comparison with the average League goals combined by all the teams.


Using the above Attack/Defence strength matrix we can estimate the probability of the team to score a specific number of goal(s).

By individually estimating the discrete prob using Poisson Distribution of the Home and Away team for different events (goals) , then further selecting the maximum Joint probability of the two independent events we can predict the final score/outcome.


Example-

Consider a following match between Real Madrid (Home) and Barcelona (Away).

Following Matrices can be used to estimate the final match score


Average Home Goals Scored (HAG) =        Goals Scored  / # Games played



Average Home Goals Conceded (HAC) =       Goals Conceded / # Games played
 


Average Away Goals Scored (AAG) =           Goals Scored / # Games played



Average Away Goals Scored (AAC) =           Goals Conceded / # Games played

 
Avg League Home Goals (LHG) =      Total Goals Scored / Total # Games


Avg League Away Goals (LAG) =       Total Goals Scored / Total # Games


Home Attack Strength (HAS) =            HAG / LHG


Home Defence Strength (HDS) =          HAC / LAG


Away Attack Strength (AAS) =         AAG / LAG

Away Defence Strength (ADS) =         AAC / LHG


Home Goal Prediction (HGP) =    HAG X ADS X LHG


Away Goal Prediction (AGP) =    AAS X HDS X LAG



Final Score = Poisson Dist ( Max (HGP,AGP) ) for events/goals 0 - 5


Home - Real Madrid (RM) | Away - Barcelona (BL)


HAGRM= 1.89 | AAGBL = 1.315

LHG = 1.492 | LAG = 1.20

HASRM = 1.842 | AASBL = 1.095

HGPRM = 1.235 | AGPBL= 0.881


Poisson Distribution (HGP,AGP) for events k—-> 1 to 5.


Goals
0
1
2
3
4
5
RM
19.73%
32.02%
25.99%
14.06%
5.07%
1.85%
BL
43.86%
36.14%
14.89%
4.09%
0.84%
0.14%


Max (HGP,AGP) = RM (1) * BL (0)
= 14.04 % or 0.1404

Hence the final score/outcome will be 

RM (1 - 0 ) BL

The same algorithm and matrices can be used to predict the Final score between a Home and Away fixture based on its historical data.
