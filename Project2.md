  STILL NOT DONE
  
  
  For this project I continued my focus on Guniea. And because of challenges with available RAM on my computer, I decided to look specifically at the Boke region, which is where the Koundara prefecture (which I analyzed for the last project) is located. I downloaded my survey data from DHS and selected columns for education, age, gender, location, size and weights to be in my data frame. There are a total of 7912 household observations in guniea (1073 of which are in Boke), and 10874 persons observations. 
1. rpoint plot of households

First I used the rpoint function to plot the households in Boke. The percent error was .2536. I sadly wasn't able to spatially locate my households on the adm0 level, because I kept running into an error that told me that R didn't have enough memory to complete the function. I tried many things to fix this problem, like allocating more memory space to R and doing the project on a cloud computing platform, but I wasn't able to get anything to work. This was disapointing, because I believe I would have gotten better results if I had been able to look at all of Guniea instead of just the 1073 household observations in Boke.
![](rpoint_boke.PNG)



2. density/size plot

weighted error = 0.0004734058
![](density1_2.PNG)
![](density2_2.PNG)

3. heatplots

Next I made heatplots to demonstrate the predictive power of the data. I selected the age, gender, education and size columns to focus on. I made heatmaps with raw data, scaled data, normalized data, and percentized data. 
![](raw2.png)
The raw data heatmap is mostly homogenous, the only variable that produces different combinations is age, which means that it could be a useful predictor. 
![](scale.png)
The scaled data heatmap is also fairly homogenous, but much less so than the raw data. This means that it has more predictive power.
![](normal2.png)
The normalized data is very interesting. There is some variability in size and a lot in age, but most notably there is a complete binary in gender. This is most likely because of the large gender gap in education in Guinea.
![](percent2.png)
The percentized data has the most variability, and the most predictive power out of all of the data processing techniques.


4. ROC and GAIN graphs from models
![](multireg_gain2.PNG)
![](multireg_roc2.PNG)

![](rf_gain2.PNG)
![](rf_roc2.PNG)

5. prediction, truth confmat

![](confmat.PNG)
![](nn_graph.PNG)
