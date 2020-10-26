  STILL NOT DONE
  
  
  For this project I continued my focus on Guniea. And because of challenges with available RAM on my computer, I decided to look specifically at the Boke region, which is where the Koundara prefecture (which I analyzed for the last project) is located. I downloaded my survey data from DHS and selected columns for education, age, gender, location, size and weights to be in my data frame. There are a total of 7912 household observations in guniea (1073 of which are in Boke), and 10874 persons observations. 
1. rpoint plot of households

First I used the rpoint function to plot the households in Boke. The percent error was .2536. I sadly wasn't able to spatially locate my households on the adm0 level, because I kept running into an error that told me that R didn't have enough memory to complete the function. I tried many things to fix this problem, like allocating more memory space to R and doing the project on a cloud computing platform, but I wasn't able to get anything to work. This was disapointing, because I believe I would have gotten better results if I had been able to look at all of Guniea instead of just the 1073 household observations in Boke.
![](rpoint_boke.PNG)



2. density/size plot

![](density1.PNG)
![](density2.PNG)

3. heatplots
![](scale.png)
![](raw.png)
![](normal.png)
![](percent.png)
4. ROC and GAIN graphs from models
![](multireg_gain.PNG)
![](multireg_roc.PNG)

![](rf_gain.PNG)
![](rf_roc.PNG)

5. prediction, truth confmat
