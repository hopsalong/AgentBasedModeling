Your final project write up (for project 3) is due on Tuesday November 24th by 5PM. Please upload and provide a link from your GitHub index to a 3 to 4 page project report that analyzes migration and movement at your selected location. Include analysis that addresses the following.
Provide a written description of the analysis you conducted of the gravity model for London. Additionally, incorporate the Garcia et al. paper into your description while introducing your the migration data for your selected country. Supplement your introduction with spatial plots that describe in/out migration by adminsitrative subdivision.
Produce an origin-destination matrix and include a portion of it as an exhibit in your write-up. Be sure to identify the number of rows in your data frame while also including the following.
Names of origin and destination administrative subdivisions
Distances between all locations
Migration flows between all locations
An additional variable that describes all origin and destinations to be used for further specification of a gravity model (one option you could use is to select night-time lights from WorldPop)
Geometric description of all origin and destination center points
Describe your OD matrix and how it is used to model migration across the administrative subdivisions that comprise your selected location.
Produce an animation of migration and elaborate on how your OD matrix and gravity model could be integrated with your simulation.
How would you modify the number of points departing from each origin?
How would you modify the time variable? What scale is the temporal dimension at this level?
How would the gravity model update these attributes in order to produce a different simulation of migration that more closely approximates reality?
At the level of your selected, higher resolution administrative subdivision (where you produced defacto descriptions of settlements), use the center points of each settlement to produce a tesselation of voronoi polygons. Similar to your analysis of the higher level administrative subdivisions, address the following.
How would you produce an OD matrix of these higher resolution entities? Which variables would you include? Are you lacking any data that would improve upon your model results?
How would you modify the number of points departing from each origin? How would you determine each points destination?
How would you modify the time variable? What scale is the temporal dimension at this level?
How would the gravity model update these attributes in order to produce a different simulation of migration?
How would you go about integrating migration and transport activities at the differing geospatial and temporal scales of these hierarchical levels?


For the first part of this project, I created a gravity model for London using code by Dr Adam Dennett. I created an origin-destination matrix similar to the one that I ended up creating for Guinea later in this project, except based off of the different boroughs of London. I was then able to create a gravity model, as well as some graphs to examine the model more closely. Reading "Modeling interal Migration Flows in Sub-Saharan Africa using Census Microdata" by Garcia et al. also helped to inform my knowledge on migration modeling. They explain how gravity models can be an extremely powerful tool, especially in the realm of international development. I have included a picture of my London origin-destination matrix below:
![](londonmatrix.PNG)

For this project, I continued to examine at the Guinea, which is the country that I've been looking at for the duration of this class. I downloaded the 2010 migration flows for Guinea from World Pop, which are based on the ADM2 level. Using this data I created an origin destination matrix shown below:

![](odmp1.PNG)
![](odmp2.PNG)
My ODM has 34 rows, meaning that there are 34 districts withing Guinea that are measured for migration flow. Each number represents a ADM2 subdivision, so every box shows the flow of people from one subdivision to another. The empty boxes represent the flow within a single subdivision (so NA). 

I was able to use the migration flow data to make graphs showing where the majority of is coming from and going to. The first graph shows where people are migrating to, with the lighter blue areas having more migration to them. The second graph shows out migration, with lighter blue meaning that more people are leaving.

![](inmigration.PNG)
![](outmigration.PNG)

Next, I made an animation to represent the flows between subdivisions. The animation is essentially a visualization of the origin destinitation matrix, with every point representing a ADM2 level district, the lines representing the flows between them, and the dots representing the people migrating along the flows. 

![](output.gif)
